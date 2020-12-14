---
external help file: PSModule-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PowerShellGet
ms.date: 06/05/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/find-rolecapability?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Find-RoleCapability
ms.openlocfilehash: ad3262cbe6e77ffbd638fd8ef77efeece63c3295
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/19/2020
ms.locfileid: "94892435"
---
# <span data-ttu-id="d6688-103">Find-RoleCapability</span><span class="sxs-lookup"><span data-stu-id="d6688-103">Find-RoleCapability</span></span>

## <span data-ttu-id="d6688-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="d6688-104">SYNOPSIS</span></span>
<span data-ttu-id="d6688-105">Sucht nach Rollenfunktionen in Modulen.</span><span class="sxs-lookup"><span data-stu-id="d6688-105">Finds role capabilities in modules.</span></span>

## <span data-ttu-id="d6688-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d6688-106">SYNTAX</span></span>

### <span data-ttu-id="d6688-107">Alle</span><span class="sxs-lookup"><span data-stu-id="d6688-107">All</span></span>

```
Find-RoleCapability [[-Name] <String[]>] [-ModuleName <String>] [-MinimumVersion <String>] 
[-MaximumVersion <String>] [-RequiredVersion <String>] [-AllVersions] [-AllowPrerelease] 
[-Tag <String[]>] [-Filter <String>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>] 
[-Repository <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="d6688-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d6688-108">DESCRIPTION</span></span>

<span data-ttu-id="d6688-109">Das `Find-RoleCapability` Cmdlet sucht registrierte Depots nach PowerShell-Rollen Funktionen und-Modulen.</span><span class="sxs-lookup"><span data-stu-id="d6688-109">The `Find-RoleCapability` cmdlet searches registered repositories to find PowerShell role capabilities and modules.</span></span>

<span data-ttu-id="d6688-110">Für jede Rollen Funktion, die von gefunden wird `Find-RoleCapability` , wird ein **psgetrolecapabilityinfo** -Objekt zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="d6688-110">For each role capability found by `Find-RoleCapability`, a **PSGetRoleCapabilityInfo** object is returned.</span></span> <span data-ttu-id="d6688-111">**Psgetrolecapabilityinfo** -Objekte können über die Pipeline an das- `Install-Module` `Save-Module` Cmdlet oder das-Cmdlet gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="d6688-111">**PSGetRoleCapabilityInfo** objects can be sent down the pipeline to the `Install-Module` or `Save-Module` cmdlets.</span></span>

<span data-ttu-id="d6688-112">PowerShell-Rollen Funktionen definieren, welche Befehle und Anwendungen für einen Benutzer am Just Enough Administration (Jea)-Endpunkt verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="d6688-112">PowerShell role capabilities define which commands and applications are available to a user at a Just Enough Administration (JEA) endpoint.</span></span> <span data-ttu-id="d6688-113">Rollen Funktionen werden durch Dateien mit einer `.psrc` Erweiterung definiert.</span><span class="sxs-lookup"><span data-stu-id="d6688-113">Role capabilities are defined by files with a `.psrc` extension.</span></span>

## <span data-ttu-id="d6688-114">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="d6688-114">EXAMPLES</span></span>

### <span data-ttu-id="d6688-115">Beispiel 1: Suchen von Rollen Funktionen</span><span class="sxs-lookup"><span data-stu-id="d6688-115">Example 1: Find role capabilities</span></span>

<span data-ttu-id="d6688-116">`Find-RoleCapability` findet Rollen Funktionen in jedem registrierten Repository.</span><span class="sxs-lookup"><span data-stu-id="d6688-116">`Find-RoleCapability` finds role capabilities in each registered repository.</span></span> <span data-ttu-id="d6688-117">Verwenden Sie den **Repository** -Parameter, um ein bestimmtes Repository zu durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="d6688-117">To search a specific repository, use the **Repository** parameter.</span></span>

```powershell
Find-RoleCapability
```

```output
Name             Version    ModuleName     Repository
----             -------    ----------     ----------
General-Lev1     1.0        JeaExamples    PSGallery
General-Lev2     1.0        JeaExamples    PSGallery
IIS-Lev1         1.0        JeaExamples    PSGallery
IIS-Lev2         1.0        JeaExamples    PSGallery
```

### <span data-ttu-id="d6688-118">Beispiel 2: Suchen von Rollen Funktionen nach Namen</span><span class="sxs-lookup"><span data-stu-id="d6688-118">Example 2: Find role capabilities by name</span></span>

<span data-ttu-id="d6688-119">`Find-RoleCapability` sucht Rollen Funktionen anhand des Namens.</span><span class="sxs-lookup"><span data-stu-id="d6688-119">`Find-RoleCapability` finds role capabilities by name.</span></span> <span data-ttu-id="d6688-120">Verwenden Sie Kommas, um ein Array von Namen voneinander zu trennen.</span><span class="sxs-lookup"><span data-stu-id="d6688-120">Use commas to separate an array of names.</span></span>

```powershell
Find-RoleCapability -Name General-Lev1, IIS-Lev2
```

```output
Name             Version    ModuleName     Repository
----             -------    ----------     ----------
General-Lev1     1.0        JeaExamples    PSGallery
IIS-Lev2         1.0        JeaExamples    PSGallery
```

### <span data-ttu-id="d6688-121">Beispiel 3: Suchen und Speichern des Moduls einer Rollen Funktion</span><span class="sxs-lookup"><span data-stu-id="d6688-121">Example 3: Find and save a role capability's module</span></span>

<span data-ttu-id="d6688-122">Das `Find-RoleCapability` Cmdlet sucht eine Rollen Funktion und sendet das Objekt über die Pipeline.</span><span class="sxs-lookup"><span data-stu-id="d6688-122">The `Find-RoleCapability` cmdlet finds a role capability and sends the object down the pipeline.</span></span>
<span data-ttu-id="d6688-123">`Save-Module` speichert das Modul der Rollen Funktion in einem Dateisystem.</span><span class="sxs-lookup"><span data-stu-id="d6688-123">`Save-Module` saves the role capability's module to a file system.</span></span> <span data-ttu-id="d6688-124">`Get-ChildItem` zeigt den Inhalt des Modul Verzeichnisses an.</span><span class="sxs-lookup"><span data-stu-id="d6688-124">`Get-ChildItem` displays the contents of the module's directory.</span></span>

```
PS> Find-RoleCapability -Name General-Lev1 | Save-Module -Path C:\Test\Modules

PS> Get-ChildItem -Path C:\Test\Modules\JeaExamples\1.0\

    Directory: C:\Test\Modules\JeaExamples\1.0

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----          6/4/2019    16:37                RoleCapabilities
-a----          2/5/2019    18:46           1702 CreateRegisterPSSC.ps1
-a----          2/5/2019    18:46           7656 JeaExamples.psd1
-a----         10/1/2018    08:16            595 JeaExamples.psm1
```

<span data-ttu-id="d6688-125">`Find-RoleCapability` verwendet den **Name** -Parameter, um die Rolle " **General-Lev1** Role" anzugeben.</span><span class="sxs-lookup"><span data-stu-id="d6688-125">`Find-RoleCapability` uses the **Name** parameter to specify the **General-Lev1** role capability.</span></span>
<span data-ttu-id="d6688-126">Das Objekt wird über die Pipeline gesendet.</span><span class="sxs-lookup"><span data-stu-id="d6688-126">The object is sent down the pipeline.</span></span> <span data-ttu-id="d6688-127">`Save-Module` verwendet den **path** -Parameter für den Speicherort des Dateisystems, um das Modul zu speichern.</span><span class="sxs-lookup"><span data-stu-id="d6688-127">`Save-Module` uses the **Path** parameter for the file system location to save the module.</span></span> <span data-ttu-id="d6688-128">Nachdem das Modul gespeichert wurde, `Get-ChildItem` gibt den **Pfad** des Moduls an und zeigt den Inhalt des Verzeichnisses des **jeaexamples** -Moduls an.</span><span class="sxs-lookup"><span data-stu-id="d6688-128">After the module is saved, `Get-ChildItem` specifies the module's **Path** and displays the contents of the **JeaExamples** module's directory.</span></span>

### <span data-ttu-id="d6688-129">Beispiel 4: Suchen und Installieren des Moduls einer Rollen Funktion</span><span class="sxs-lookup"><span data-stu-id="d6688-129">Example 4: Find and install a role capability's module</span></span>

<span data-ttu-id="d6688-130">`Find-RoleCapability` sucht das Modul und sendet das Objekt über die Pipeline.</span><span class="sxs-lookup"><span data-stu-id="d6688-130">`Find-RoleCapability` finds the module and sends the object down the pipeline.</span></span> <span data-ttu-id="d6688-131">`Install-Module` installiert das-Modul.</span><span class="sxs-lookup"><span data-stu-id="d6688-131">`Install-Module` installs the module.</span></span> <span data-ttu-id="d6688-132">Verwenden Sie nach der Installation, `Get-InstalledModule` um die Ergebnisse anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="d6688-132">After the installation, use `Get-InstalledModule` to see the results.</span></span>

```
PS> Find-RoleCapability -Name General-Lev1 | Install-Module -Verbose

VERBOSE: Downloading 'https://www.powershellgallery.com/api/v2/package/JeaExamples/1.0.0'.
VERBOSE: Completed downloading 'https://www.powershellgallery.com/api/v2/package/JeaExamples/1.0.0'.
VERBOSE: Completed downloading 'JeaExamples'.
VERBOSE: InstallPackageLocal' - name='JeaExamples', version='1.0',
VERBOSE: Validating the 'JeaExamples' module contents
VERBOSE: Test-ModuleManifest successfully validated the module manifest file
VERBOSE: Module 'JeaExamples' was installed successfully to path

PS> Get-InstalledModule

Version    Name            Repository     Description
-------    ----            ----------     -----------
1.0        JeaExamples     PSGallery      Some example Jea roles for general server maintenance...
```

<span data-ttu-id="d6688-133">`Find-RoleCapability` verwendet den **Name** -Parameter, um die Rolle " **General-Lev1** Role" anzugeben.</span><span class="sxs-lookup"><span data-stu-id="d6688-133">`Find-RoleCapability` uses the **Name** parameter to specify the **General-Lev1** role capability.</span></span>
<span data-ttu-id="d6688-134">Das Objekt wird über die Pipeline gesendet.</span><span class="sxs-lookup"><span data-stu-id="d6688-134">The object is sent down the pipeline.</span></span> <span data-ttu-id="d6688-135">`Install-Module` verwendet den **verbose** -Parameter, um Statusmeldungen während der Installation anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="d6688-135">`Install-Module` uses the **Verbose** parameter to display status messages during the installation.</span></span> <span data-ttu-id="d6688-136">Nachdem die Installation abgeschlossen ist, wird in der `Get-InstalledModule` Ausgabe bestätigt, dass das **jeaexamples** -Modul installiert wurde.</span><span class="sxs-lookup"><span data-stu-id="d6688-136">After the install is finished, the `Get-InstalledModule` output confirms that the **JeaExamples** module was installed.</span></span>

## <span data-ttu-id="d6688-137">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d6688-137">PARAMETERS</span></span>

### <span data-ttu-id="d6688-138">-Allowprerelease</span><span class="sxs-lookup"><span data-stu-id="d6688-138">-AllowPrerelease</span></span>

<span data-ttu-id="d6688-139">Schließt Ressourcen ein, die in den Ergebnissen als Vorabversion gekennzeichnet sind.</span><span class="sxs-lookup"><span data-stu-id="d6688-139">Includes resources marked as a prerelease in the results.</span></span>

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

### <span data-ttu-id="d6688-140">-Allversions</span><span class="sxs-lookup"><span data-stu-id="d6688-140">-AllVersions</span></span>

<span data-ttu-id="d6688-141">Gibt an, dass dieses Cmdlet alle Versionen eines Moduls abruft.</span><span class="sxs-lookup"><span data-stu-id="d6688-141">Indicates that this cmdlet gets all versions of a module.</span></span> <span data-ttu-id="d6688-142">Der **allversions** -Parameter zeigt alle verfügbaren Versionen eines Moduls an.</span><span class="sxs-lookup"><span data-stu-id="d6688-142">The **AllVersions** parameter displays each of a module's available versions.</span></span>

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

### <span data-ttu-id="d6688-143">-Filter</span><span class="sxs-lookup"><span data-stu-id="d6688-143">-Filter</span></span>

<span data-ttu-id="d6688-144">Sucht Ressourcen basierend auf der Such Syntax des **packagemanagement** -Anbieters.</span><span class="sxs-lookup"><span data-stu-id="d6688-144">Finds resources based on the **PackageManagement** provider's search syntax.</span></span> <span data-ttu-id="d6688-145">Geben Sie z. b. die Wörter an, nach denen in den Eigenschaften **ModuleName** und **Description** gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="d6688-145">For example, specify words to search for within the **ModuleName** and **Description** properties.</span></span>

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

### <span data-ttu-id="d6688-146">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="d6688-146">-MaximumVersion</span></span>

<span data-ttu-id="d6688-147">Gibt die maximale Version des Moduls an, das in die Ergebnisse aufgenommen werden soll.</span><span class="sxs-lookup"><span data-stu-id="d6688-147">Specifies the maximum version of the module to include in results.</span></span> <span data-ttu-id="d6688-148">Die Parameter " **MaximumVersion** " und "Requirements **dversion** " können nicht im selben Befehl verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d6688-148">The **MaximumVersion** and the **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="d6688-149">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="d6688-149">-MinimumVersion</span></span>

<span data-ttu-id="d6688-150">Gibt die Mindestversion des Moduls an, das in den Ergebnissen enthalten sein soll.</span><span class="sxs-lookup"><span data-stu-id="d6688-150">Specifies the minimum version of the module to include in results.</span></span> <span data-ttu-id="d6688-151">Der **MinimumVersion** -Parameter und der Requirements- **Version** -Parameter können nicht im selben Befehl verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d6688-151">The **MinimumVersion** and the **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="d6688-152">-ModuleName</span><span class="sxs-lookup"><span data-stu-id="d6688-152">-ModuleName</span></span>

<span data-ttu-id="d6688-153">Gibt den Namen des Moduls an, in dem nach Rollen Funktionen gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="d6688-153">Specifies the name of the module in which to search for role capabilities.</span></span> <span data-ttu-id="d6688-154">Der Standardwert ist alle Module.</span><span class="sxs-lookup"><span data-stu-id="d6688-154">The default is all modules.</span></span>

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

### <span data-ttu-id="d6688-155">-Name</span><span class="sxs-lookup"><span data-stu-id="d6688-155">-Name</span></span>

<span data-ttu-id="d6688-156">Gibt den Namen einer Rollen Funktion an.</span><span class="sxs-lookup"><span data-stu-id="d6688-156">Specifies the name of a role capability.</span></span> <span data-ttu-id="d6688-157">Der Standardwert ist alle Rollen Funktionen.</span><span class="sxs-lookup"><span data-stu-id="d6688-157">The default is all role capabilities.</span></span> <span data-ttu-id="d6688-158">Verwenden Sie Kommas, um ein Array von Ressourcennamen voneinander zu trennen.</span><span class="sxs-lookup"><span data-stu-id="d6688-158">Use commas to separate an array of resource names.</span></span>

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

### <span data-ttu-id="d6688-159">-Proxy</span><span class="sxs-lookup"><span data-stu-id="d6688-159">-Proxy</span></span>

<span data-ttu-id="d6688-160">Gibt einen Proxy Server für die Anforderung an, anstatt eine direkte Verbindung mit der Internet Ressource herzustellen.</span><span class="sxs-lookup"><span data-stu-id="d6688-160">Specifies a proxy server for the request, rather than a direct connection to the internet resource.</span></span>

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

### <span data-ttu-id="d6688-161">-Proxy Credential</span><span class="sxs-lookup"><span data-stu-id="d6688-161">-ProxyCredential</span></span>

<span data-ttu-id="d6688-162">Gibt ein Benutzerkonto mit der Berechtigung an, den im **Proxy** Parameter angegebenen Proxy Server zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="d6688-162">Specifies a user account with permission to use the proxy server specified in the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="d6688-163">-Repository</span><span class="sxs-lookup"><span data-stu-id="d6688-163">-Repository</span></span>

<span data-ttu-id="d6688-164">Gibt ein Repository an, in dem nach Rollen Funktionen gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="d6688-164">Specifies a repository to search for role capabilities.</span></span> <span data-ttu-id="d6688-165">Verwenden Sie Kommas, um ein Array von Repository-Namen zu trennen.</span><span class="sxs-lookup"><span data-stu-id="d6688-165">Use commas to separate an array of repository names.</span></span>

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

### <span data-ttu-id="d6688-166">-Requirements dversion</span><span class="sxs-lookup"><span data-stu-id="d6688-166">-RequiredVersion</span></span>

<span data-ttu-id="d6688-167">Gibt die genaue Versionsnummer des Moduls an, das in die Ergebnisse aufgenommen werden soll.</span><span class="sxs-lookup"><span data-stu-id="d6688-167">Specifies the module's exact version number to include in the results.</span></span> <span data-ttu-id="d6688-168">Die Parameter "Requirements **dversion** " und " **MinimumVersion** " können nicht im selben Befehl verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d6688-168">The **RequiredVersion** and the **MinimumVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="d6688-169">-Tag</span><span class="sxs-lookup"><span data-stu-id="d6688-169">-Tag</span></span>

<span data-ttu-id="d6688-170">Gibt Tags an, die Module in einem Repository kategorisieren.</span><span class="sxs-lookup"><span data-stu-id="d6688-170">Specifies tags that categorize modules in a repository.</span></span> <span data-ttu-id="d6688-171">Verwenden Sie Kommas, um ein Array von Tags voneinander zu trennen.</span><span class="sxs-lookup"><span data-stu-id="d6688-171">Use commas to separate an array of tags.</span></span>

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

### <span data-ttu-id="d6688-172">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="d6688-172">CommonParameters</span></span>

<span data-ttu-id="d6688-173">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="d6688-173">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="d6688-174">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="d6688-174">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="d6688-175">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="d6688-175">INPUTS</span></span>

### <span data-ttu-id="d6688-176">System.Uri</span><span class="sxs-lookup"><span data-stu-id="d6688-176">System.Uri</span></span>

### <span data-ttu-id="d6688-177">System. Management. Automation. PSCredential</span><span class="sxs-lookup"><span data-stu-id="d6688-177">System.Management.Automation.PSCredential</span></span>

## <span data-ttu-id="d6688-178">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="d6688-178">OUTPUTS</span></span>

### <span data-ttu-id="d6688-179">PSGetRoleCapabilityInfo</span><span class="sxs-lookup"><span data-stu-id="d6688-179">PSGetRoleCapabilityInfo</span></span>

<span data-ttu-id="d6688-180">Mit dem- `Find-RoleCapability` Cmdlet wird ein **psgetrolecapabilityinfo** -Objekt zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="d6688-180">The `Find-RoleCapability` cmdlet returns a **PSGetRoleCapabilityInfo** object.</span></span>

## <span data-ttu-id="d6688-181">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="d6688-181">NOTES</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d6688-182">Ab dem 2020 unterstützt die PowerShell-Katalog nicht mehr Transport Layer Security (TLS)-Versionen 1,0 und 1,1.</span><span class="sxs-lookup"><span data-stu-id="d6688-182">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="d6688-183">Wenn Sie TLS 1,2 oder höher nicht verwenden, erhalten Sie eine Fehlermeldung, wenn Sie versuchen, auf die PowerShell-Katalog zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="d6688-183">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="d6688-184">Verwenden Sie den folgenden Befehl, um sicherzustellen, dass Sie TLS 1,2 verwenden:</span><span class="sxs-lookup"><span data-stu-id="d6688-184">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="d6688-185">Weitere Informationen finden Sie in der [Ankündigung](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) im PowerShell-Blog.</span><span class="sxs-lookup"><span data-stu-id="d6688-185">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="d6688-186">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="d6688-186">RELATED LINKS</span></span>

[<span data-ttu-id="d6688-187">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="d6688-187">Get-ChildItem</span></span>](../Microsoft.PowerShell.Management/Get-ChildItem.md)

[<span data-ttu-id="d6688-188">Get-InstalledModule</span><span class="sxs-lookup"><span data-stu-id="d6688-188">Get-InstalledModule</span></span>](Get-InstalledModule.md)

[<span data-ttu-id="d6688-189">Install-Module</span><span class="sxs-lookup"><span data-stu-id="d6688-189">Install-Module</span></span>](Install-Module.md)

[<span data-ttu-id="d6688-190">New-PSRoleCapabilityFile</span><span class="sxs-lookup"><span data-stu-id="d6688-190">New-PSRoleCapabilityFile</span></span>](../Microsoft.PowerShell.Core/New-PSRoleCapabilityFile.md)

[<span data-ttu-id="d6688-191">Save-Module</span><span class="sxs-lookup"><span data-stu-id="d6688-191">Save-Module</span></span>](Save-Module.md)
