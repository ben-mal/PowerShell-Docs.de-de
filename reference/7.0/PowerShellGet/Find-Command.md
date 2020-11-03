---
external help file: PSModule-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PowerShellGet
ms.date: 06/03/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/find-command?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Find-Command
ms.openlocfilehash: d872f53c504874f69f1e39c506a72bfefa072aa6
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2020
ms.locfileid: "93210135"
---
# <span data-ttu-id="fb951-103">Find-Command</span><span class="sxs-lookup"><span data-stu-id="fb951-103">Find-Command</span></span>

## <span data-ttu-id="fb951-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="fb951-104">SYNOPSIS</span></span>
<span data-ttu-id="fb951-105">Sucht PowerShell-Befehle in Modulen.</span><span class="sxs-lookup"><span data-stu-id="fb951-105">Finds PowerShell commands in modules.</span></span>

## <span data-ttu-id="fb951-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="fb951-106">SYNTAX</span></span>

### <span data-ttu-id="fb951-107">Alle</span><span class="sxs-lookup"><span data-stu-id="fb951-107">All</span></span>

```
Find-Command [[-Name] <String[]>] [-ModuleName <String>] [-MinimumVersion <String>]
 [-MaximumVersion <String>] [-RequiredVersion <String>] [-AllVersions] [-AllowPrerelease]
 [-Tag <String[]>] [-Filter <String>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-Repository <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="fb951-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="fb951-108">DESCRIPTION</span></span>

<span data-ttu-id="fb951-109">Das- `Find-Command` Cmdlet findet PowerShell-Befehle, z. b. Cmdlets, Aliase, Funktionen und Workflows.</span><span class="sxs-lookup"><span data-stu-id="fb951-109">The `Find-Command` cmdlet finds PowerShell commands such as cmdlets, aliases, functions, and workflows.</span></span> <span data-ttu-id="fb951-110">`Find-Command` durchsucht Module in registrierten Depots.</span><span class="sxs-lookup"><span data-stu-id="fb951-110">`Find-Command` searches modules in registered repositories.</span></span>

<span data-ttu-id="fb951-111">Für jeden von gefundenen Befehl `Find-Command` wird ein **psgetcommandinfo** -Objekt zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="fb951-111">For each command found by `Find-Command`, a **PSGetCommandInfo** object is returned.</span></span> <span data-ttu-id="fb951-112">Das **psgetcommandinfo** -Objekt kann über die Pipeline an das `Install-Module` Cmdlet gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="fb951-112">The **PSGetCommandInfo** object can be sent down the pipeline to the `Install-Module` cmdlet.</span></span>
<span data-ttu-id="fb951-113">`Install-Module` installiert das Modul, das den Befehl enthält.</span><span class="sxs-lookup"><span data-stu-id="fb951-113">`Install-Module` installs the module that contains the command.</span></span>

## <span data-ttu-id="fb951-114">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="fb951-114">EXAMPLES</span></span>

### <span data-ttu-id="fb951-115">Beispiel 1: Suchen aller Befehle in einem angegebenen Repository</span><span class="sxs-lookup"><span data-stu-id="fb951-115">Example 1: Find all commands in a specified repository</span></span>

<span data-ttu-id="fb951-116">Mit dem- `Find-Command` Cmdlet wird ein registriertes Repository nach Modulen durchsucht.</span><span class="sxs-lookup"><span data-stu-id="fb951-116">The `Find-Command` cmdlet searches a registered repository for modules.</span></span>

```powershell
Find-Command -Repository PSGallery | Select-Object -First 10
```

```output
Name                                Version    ModuleName          Repository
----                                -------    ----------          ----------
Disable-AzureRmDataCollection       5.8.3      AzureRM.profile     PSGallery
Disable-AzureRmContextAutosave      5.8.3      AzureRM.profile     PSGallery
Enable-AzureRmDataCollection        5.8.3      AzureRM.profile     PSGallery
Enable-AzureRmContextAutosave       5.8.3      AzureRM.profile     PSGallery
Remove-AzureRmEnvironment           5.8.3      AzureRM.profile     PSGallery
Get-AzureRmEnvironment              5.8.3      AzureRM.profile     PSGallery
Set-AzureRmEnvironment              5.8.3      AzureRM.profile     PSGallery
Add-AzureRmEnvironment              5.8.3      AzureRM.profile     PSGallery
Get-AzureRmSubscription             5.8.3      AzureRM.profile     PSGallery
Connect-AzureRmAccount              5.8.3      AzureRM.profile     PSGallery
```

<span data-ttu-id="fb951-117">`Find-Command` verwendet den **Repository** -Parameter, um den Namen eines registrierten Repository anzugeben.</span><span class="sxs-lookup"><span data-stu-id="fb951-117">`Find-Command` uses the **Repository** parameter to specify a registered repository's name.</span></span> <span data-ttu-id="fb951-118">Die Objekte werden über die Pipeline gesendet.</span><span class="sxs-lookup"><span data-stu-id="fb951-118">The objects are sent down the pipeline.</span></span> <span data-ttu-id="fb951-119">`Select-Object` empfängt die Objekte und verwendet den **ersten** Parameter, um die ersten 10 Ergebnisse anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="fb951-119">`Select-Object` receives the objects and uses the **First** parameter to display the first 10 results.</span></span>

### <span data-ttu-id="fb951-120">Beispiel 2: Suchen eines Befehls anhand des Namens</span><span class="sxs-lookup"><span data-stu-id="fb951-120">Example 2: Find a command by name</span></span>

<span data-ttu-id="fb951-121">`Find-Command` kann den Namen eines Befehls verwenden, um das Modul in einem Repository zu suchen.</span><span class="sxs-lookup"><span data-stu-id="fb951-121">`Find-Command` can use the name of a command to locate the module in a repository.</span></span> <span data-ttu-id="fb951-122">Es ist möglich, dass ein Befehls Name in mehreren **modulenames** vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="fb951-122">It's possible that a command name exists in multiple **ModuleNames**.</span></span>

```powershell
Find-Command -Repository PSGallery -Name Get-TargetResource
```

```Output
Name                  Version    ModuleName                      Repository
----                  -------    ----------                      ----------
Get-TargetResource    3.1.0.0    xPowerShellExecutionPolicy      PSGallery
Get-TargetResource    1.0.0      xInternetExplorerHomePage       PSGallery
Get-TargetResource    1.2.0.0    SystemLocaleDsc                 PSGallery
```

<span data-ttu-id="fb951-123">`Find-Command` verwendet den **Repository** -Parameter, um den **psgallery** zu durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="fb951-123">`Find-Command` uses the **Repository** parameter to search the **PSGallery**.</span></span> <span data-ttu-id="fb951-124">Der **Name** -Parameter gibt den Befehl **Get-targetresource** an.</span><span class="sxs-lookup"><span data-stu-id="fb951-124">The **Name** parameter specifies the command **Get-TargetResource**.</span></span>

### <span data-ttu-id="fb951-125">Beispiel 3: Suchen nach Befehlen nach Name und Installieren des Moduls</span><span class="sxs-lookup"><span data-stu-id="fb951-125">Example 3: Find commands by name and install the module</span></span>

<span data-ttu-id="fb951-126">`Find-Command` kann den Befehl und das Modul suchen und dann das Objekt an senden `Install-Module` .</span><span class="sxs-lookup"><span data-stu-id="fb951-126">`Find-Command` can locate the command and module, then send the object to `Install-Module`.</span></span> <span data-ttu-id="fb951-127">Wenn ein Befehl in mehreren Modulen enthalten ist, verwenden Sie den `Find-Command` **Module-Name-** Parameter des Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="fb951-127">If a command is included in multiple modules, use the `Find-Command` cmdlets **Module-Name** parameter.</span></span>
<span data-ttu-id="fb951-128">Andernfalls können Module installiert werden, die Sie nicht installieren möchten.</span><span class="sxs-lookup"><span data-stu-id="fb951-128">Otherwise, modules might be installed that you didn't want to install.</span></span>

```powershell
PS> Find-Command -Name Get-TargetResource -Repository PSGallery -ModuleName SystemLocaleDsc |
    Install-Module

PS> Get-InstalledModule

Version   Name               Repository   Description
-------   ----               ----------   -----------
1.2.0.0   SystemLocaleDsc    PSGallery    This DSC Resource allows configuration of the Windows...
```

<span data-ttu-id="fb951-129">`Find-Command` verwendet den **Name** -Parameter, um den Befehl " **Get-targetresource** " anzugeben.</span><span class="sxs-lookup"><span data-stu-id="fb951-129">`Find-Command` uses the **Name** parameter to specify the command **Get-TargetResource**.</span></span> <span data-ttu-id="fb951-130">Der **Repository** -Parameter durchsucht den **psgallery**.</span><span class="sxs-lookup"><span data-stu-id="fb951-130">The **Repository** parameter searches the **PSGallery**.</span></span> <span data-ttu-id="fb951-131">Der **ModuleName** -Parameter gibt das Modul an, das Sie installieren möchten, **systemlocaledsc**.</span><span class="sxs-lookup"><span data-stu-id="fb951-131">The **ModuleName** parameter specifies the module you want to install, **SystemLocaleDsc**.</span></span> <span data-ttu-id="fb951-132">Das-Objekt wird an die Pipeline gesendet, `Install-Module` und das-Modul wird installiert.</span><span class="sxs-lookup"><span data-stu-id="fb951-132">The object is sent down the pipeline to `Install-Module` and the module is installed.</span></span> <span data-ttu-id="fb951-133">Nachdem die Installation abgeschlossen ist, können Sie verwenden, `Get-InstalledModule` um die Ergebnisse anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="fb951-133">After the installation finishes, you can use `Get-InstalledModule` to display the results.</span></span>

### <span data-ttu-id="fb951-134">Beispiel 4: Suchen eines Befehls und Speichern des Moduls</span><span class="sxs-lookup"><span data-stu-id="fb951-134">Example 4: Find a command and save its module</span></span>

```
PS> Find-Command -Name Invoke-ScriptAnalyzer -Repository PSGallery | Save-Module -Path C:\Test\Modules -Verbose

VERBOSE: Downloading 'https://www.powershellgallery.com/api/v2/package/PSScriptAnalyzer/1.18.0'.
VERBOSE: Completed downloading 'https://www.powershellgallery.com/api/v2/package/PSScriptAnalyzer/1.18.0'.
VERBOSE: Completed downloading 'PSScriptAnalyzer'.
VERBOSE: Module 'PSScriptAnalyzer' was saved successfully to path 'C:\Test\Modules\PSScriptAnalyzer\1.18.0'.
```

<span data-ttu-id="fb951-135">`Find-Command`verwendet die Parameter **Name** und **Repository** , um im **psgallery** -Repository nach dem Befehl " **Aufruf-scriptanalyzer** " zu suchen.</span><span class="sxs-lookup"><span data-stu-id="fb951-135">`Find-Command` uses the **Name** and **Repository** parameters to search for the command **Invoke-ScriptAnalyzer** in the **PSGallery** repository.</span></span> <span data-ttu-id="fb951-136">Das Objekt wird über die Pipeline an gesendet `Save-Module` .</span><span class="sxs-lookup"><span data-stu-id="fb951-136">The object is sent down the pipeline to `Save-Module`.</span></span> <span data-ttu-id="fb951-137">Der **path** -Parameter bestimmt den Speicherort, an dem das Modul gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="fb951-137">The **Path** parameter determines the location to save the module.</span></span> <span data-ttu-id="fb951-138">**Verbose** ist ein optionaler Parameter, zeigt jedoch die Status Ausgabe in der PowerShell-Konsole an.</span><span class="sxs-lookup"><span data-stu-id="fb951-138">**Verbose** is an optional parameter, but displays status output in the PowerShell console.</span></span> <span data-ttu-id="fb951-139">Die ausführliche Ausgabe ist von Vorteil bei der Problembehandlung.</span><span class="sxs-lookup"><span data-stu-id="fb951-139">The verbose output is beneficial for troubleshooting.</span></span>

## <span data-ttu-id="fb951-140">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="fb951-140">PARAMETERS</span></span>

### <span data-ttu-id="fb951-141">-Allowprerelease</span><span class="sxs-lookup"><span data-stu-id="fb951-141">-AllowPrerelease</span></span>

<span data-ttu-id="fb951-142">Schließt Module ein, die in den Ergebnissen als Vorabversion gekennzeichnet sind.</span><span class="sxs-lookup"><span data-stu-id="fb951-142">Includes modules marked as a prerelease in the results.</span></span>

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

### <span data-ttu-id="fb951-143">-Allversions</span><span class="sxs-lookup"><span data-stu-id="fb951-143">-AllVersions</span></span>

<span data-ttu-id="fb951-144">Gibt an, dass dieses Cmdlet alle Versionen eines Moduls abruft.</span><span class="sxs-lookup"><span data-stu-id="fb951-144">Indicates that this cmdlet gets all versions of a module.</span></span>

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

### <span data-ttu-id="fb951-145">-Filter</span><span class="sxs-lookup"><span data-stu-id="fb951-145">-Filter</span></span>

<span data-ttu-id="fb951-146">Sucht Module basierend auf der Such Syntax des **packagemanagement** -Anbieters.</span><span class="sxs-lookup"><span data-stu-id="fb951-146">Finds modules based on the **PackageManagement** provider's search syntax.</span></span> <span data-ttu-id="fb951-147">Geben Sie z. b. die Wörter an, nach denen in den Eigenschaften **ModuleName** und **Description** gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="fb951-147">For example, specify words to search for within the **ModuleName** and **Description** properties.</span></span>

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

### <span data-ttu-id="fb951-148">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="fb951-148">-MaximumVersion</span></span>

<span data-ttu-id="fb951-149">Gibt die maximale Version des Moduls an, das in die Ergebnisse aufgenommen werden soll.</span><span class="sxs-lookup"><span data-stu-id="fb951-149">Specifies the maximum version of the module to include in results.</span></span> <span data-ttu-id="fb951-150">Die Parameter " **MaximumVersion** " und "Requirements **dversion** " können nicht im selben Befehl verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fb951-150">The **MaximumVersion** and the **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="fb951-151">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="fb951-151">-MinimumVersion</span></span>

<span data-ttu-id="fb951-152">Gibt die Mindestversion des Moduls an, das in den Ergebnissen enthalten sein soll.</span><span class="sxs-lookup"><span data-stu-id="fb951-152">Specifies the minimum version of the module to include in results.</span></span> <span data-ttu-id="fb951-153">Der **MinimumVersion** -Parameter und der Requirements- **Version** -Parameter können nicht im selben Befehl verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fb951-153">The **MinimumVersion** and the **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="fb951-154">-ModuleName</span><span class="sxs-lookup"><span data-stu-id="fb951-154">-ModuleName</span></span>

<span data-ttu-id="fb951-155">Gibt den Namen eines Moduls an, in dem nach Befehlen gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="fb951-155">Specifies the name of a module to search for commands.</span></span> <span data-ttu-id="fb951-156">Der Standardwert ist alle Module.</span><span class="sxs-lookup"><span data-stu-id="fb951-156">The default is all modules.</span></span>

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

### <span data-ttu-id="fb951-157">-Name</span><span class="sxs-lookup"><span data-stu-id="fb951-157">-Name</span></span>

<span data-ttu-id="fb951-158">Gibt den Namen des Befehls an, nach dem in einem Repository gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="fb951-158">Specifies the command name to search for in a repository.</span></span> <span data-ttu-id="fb951-159">Verwenden Sie Kommas, um ein Array von Befehlsnamen zu trennen.</span><span class="sxs-lookup"><span data-stu-id="fb951-159">Use commas to separate an array of command names.</span></span>

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

### <span data-ttu-id="fb951-160">-Proxy</span><span class="sxs-lookup"><span data-stu-id="fb951-160">-Proxy</span></span>

<span data-ttu-id="fb951-161">Gibt einen Proxy Server für die Anforderung an, anstatt eine direkte Verbindung mit der Internet Ressource herzustellen.</span><span class="sxs-lookup"><span data-stu-id="fb951-161">Specifies a proxy server for the request, rather than a direct connection to the internet resource.</span></span>

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

### <span data-ttu-id="fb951-162">-Proxy Credential</span><span class="sxs-lookup"><span data-stu-id="fb951-162">-ProxyCredential</span></span>

<span data-ttu-id="fb951-163">Gibt ein Benutzerkonto an, das über die Berechtigung zur Verwendung des Proxyservers verfügt, der durch den **Proxy** -Parameter angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="fb951-163">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="fb951-164">-Repository</span><span class="sxs-lookup"><span data-stu-id="fb951-164">-Repository</span></span>

<span data-ttu-id="fb951-165">Gibt das Repository für die Suche nach Befehlen an.</span><span class="sxs-lookup"><span data-stu-id="fb951-165">Specifies the repository to search for commands.</span></span> <span data-ttu-id="fb951-166">Verwenden Sie Kommas, um ein Array von Repository-Namen zu trennen.</span><span class="sxs-lookup"><span data-stu-id="fb951-166">Use commas to separate an array of repository names.</span></span> <span data-ttu-id="fb951-167">Der Standardwert ist alle Depots.</span><span class="sxs-lookup"><span data-stu-id="fb951-167">The default is all repositories.</span></span>

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

### <span data-ttu-id="fb951-168">-Requirements dversion</span><span class="sxs-lookup"><span data-stu-id="fb951-168">-RequiredVersion</span></span>

<span data-ttu-id="fb951-169">Gibt die Version des Moduls an, das in die Ergebnisse aufgenommen werden soll.</span><span class="sxs-lookup"><span data-stu-id="fb951-169">Specifies the version of the module to include in the results.</span></span>

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

### <span data-ttu-id="fb951-170">-Tag</span><span class="sxs-lookup"><span data-stu-id="fb951-170">-Tag</span></span>

<span data-ttu-id="fb951-171">Gibt Tags an, die Module in einem Repository kategorisieren.</span><span class="sxs-lookup"><span data-stu-id="fb951-171">Specifies tags that categorize modules in a repository.</span></span> <span data-ttu-id="fb951-172">Verwenden Sie Kommas, um ein Array von Tags voneinander zu trennen.</span><span class="sxs-lookup"><span data-stu-id="fb951-172">Use commas to separate an array of tags.</span></span>

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

### <span data-ttu-id="fb951-173">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="fb951-173">CommonParameters</span></span>

<span data-ttu-id="fb951-174">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="fb951-174">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="fb951-175">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="fb951-175">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="fb951-176">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="fb951-176">INPUTS</span></span>

## <span data-ttu-id="fb951-177">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="fb951-177">OUTPUTS</span></span>

### <span data-ttu-id="fb951-178">PSGetCommandInfo</span><span class="sxs-lookup"><span data-stu-id="fb951-178">PSGetCommandInfo</span></span>

<span data-ttu-id="fb951-179">`Find-Command` Gibt ein **psgetcommandinfo** -Objekt aus.</span><span class="sxs-lookup"><span data-stu-id="fb951-179">`Find-Command` outputs a **PSGetCommandInfo** object.</span></span>

## <span data-ttu-id="fb951-180">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="fb951-180">NOTES</span></span>

## <span data-ttu-id="fb951-181">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="fb951-181">RELATED LINKS</span></span>

[<span data-ttu-id="fb951-182">Get-InstalledModule</span><span class="sxs-lookup"><span data-stu-id="fb951-182">Get-InstalledModule</span></span>](Get-InstalledModule.md)

[<span data-ttu-id="fb951-183">Install-Module</span><span class="sxs-lookup"><span data-stu-id="fb951-183">Install-Module</span></span>](Install-Module.md)

[<span data-ttu-id="fb951-184">Save-Module</span><span class="sxs-lookup"><span data-stu-id="fb951-184">Save-Module</span></span>](Save-Module.md)

[<span data-ttu-id="fb951-185">Select-Object</span><span class="sxs-lookup"><span data-stu-id="fb951-185">Select-Object</span></span>](../Microsoft.PowerShell.Utility/Select-Object.md)

[<span data-ttu-id="fb951-186">Uninstall-Module</span><span class="sxs-lookup"><span data-stu-id="fb951-186">Uninstall-Module</span></span>](Uninstall-Module.md)
