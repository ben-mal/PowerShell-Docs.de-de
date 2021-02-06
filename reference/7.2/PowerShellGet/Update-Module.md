---
external help file: PSModule-help.xml
Locale: en-US
Module Name: PowerShellGet
ms.date: 07/16/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/update-module?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Update-Module
ms.openlocfilehash: f29c208805894634960085cd3816ce7780b7602f
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/19/2020
ms.locfileid: "99599206"
---
# <span data-ttu-id="641b8-102">Update-Module</span><span class="sxs-lookup"><span data-stu-id="641b8-102">Update-Module</span></span>

## <span data-ttu-id="641b8-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="641b8-103">SYNOPSIS</span></span>
<span data-ttu-id="641b8-104">Lädt die neueste Version der angegebenen Module aus einem Onlinekatalog auf den lokalen Computer herunter und installiert diese</span><span class="sxs-lookup"><span data-stu-id="641b8-104">Downloads and installs the newest version of specified modules from an online gallery to the local computer.</span></span>

## <span data-ttu-id="641b8-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="641b8-105">SYNTAX</span></span>

### <span data-ttu-id="641b8-106">Alle</span><span class="sxs-lookup"><span data-stu-id="641b8-106">All</span></span>

```
Update-Module [[-Name] <String[]>] [-RequiredVersion <String>] [-MaximumVersion <String>]
 [-Credential <PSCredential>] [-Scope <String>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-Force] [-AllowPrerelease] [-AcceptLicense] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="641b8-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="641b8-107">DESCRIPTION</span></span>

<span data-ttu-id="641b8-108">Mit dem `Update-Module` -Cmdlet wird die neueste Version eines Moduls aus einem Onlinekatalog installiert.</span><span class="sxs-lookup"><span data-stu-id="641b8-108">The `Update-Module` cmdlet installs a module's newest version from an online gallery.</span></span> <span data-ttu-id="641b8-109">Sie werden aufgefordert, das Update vor der Installation zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="641b8-109">You're prompted to confirm the update before it's installed.</span></span> <span data-ttu-id="641b8-110">Updates werden nur für Module installiert, die mit auf dem lokalen Computer installiert wurden `Install-Module` .</span><span class="sxs-lookup"><span data-stu-id="641b8-110">Updates are installed only for modules that were installed on the local computer with `Install-Module`.</span></span> <span data-ttu-id="641b8-111">`Update-Module` sucht `$env:PSModulePath` nach installierten Modulen.</span><span class="sxs-lookup"><span data-stu-id="641b8-111">`Update-Module` searches `$env:PSModulePath` for installed modules.</span></span>

<span data-ttu-id="641b8-112">`Update-Module` Wenn keine Parameter angegeben sind, werden alle installierten Module aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="641b8-112">`Update-Module` with no parameters specified updates all installed modules.</span></span> <span data-ttu-id="641b8-113">Verwenden Sie den **Name** -Parameter, um ein Modul anzugeben, das aktualisiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="641b8-113">To specify a module to update, use the **Name** parameter.</span></span> <span data-ttu-id="641b8-114">Mithilfe des Parameters "Requirements **dversion** " können Sie ein Update auf die spezifische Version eines Moduls durchsetzen.</span><span class="sxs-lookup"><span data-stu-id="641b8-114">You can update to a module's specific version by using the **RequiredVersion** parameter.</span></span>

<span data-ttu-id="641b8-115">Wenn ein installiertes Modul bereits die neueste Version ist, wird das Modul nicht aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="641b8-115">If an installed module is already the newest version, the module isn't updated.</span></span> <span data-ttu-id="641b8-116">Wenn das Modul in nicht gefunden wird `$env:PSModulePath` , wird ein Fehler angezeigt.</span><span class="sxs-lookup"><span data-stu-id="641b8-116">If the module isn't found in `$env:PSModulePath`, an error is displayed.</span></span>

<span data-ttu-id="641b8-117">Verwenden Sie, um die installierten Module anzuzeigen `Get-InstalledModule` .</span><span class="sxs-lookup"><span data-stu-id="641b8-117">To display the installed modules, use `Get-InstalledModule`.</span></span>

## <span data-ttu-id="641b8-118">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="641b8-118">EXAMPLES</span></span>

### <span data-ttu-id="641b8-119">Beispiel 1: Aktualisieren aller Module</span><span class="sxs-lookup"><span data-stu-id="641b8-119">Example 1: Update all modules</span></span>

<span data-ttu-id="641b8-120">In diesem Beispiel werden alle installierten Module auf die neueste Version in einem Onlinekatalog aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="641b8-120">This example updates all installed modules to the newest version in an online gallery.</span></span>

```powershell
Update-Module
```

### <span data-ttu-id="641b8-121">Beispiel 2: Aktualisieren eines Moduls nach Name</span><span class="sxs-lookup"><span data-stu-id="641b8-121">Example 2: Update a module by name</span></span>

<span data-ttu-id="641b8-122">In diesem Beispiel wird ein bestimmtes Modul auf die neueste Version in einem Onlinekatalog aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="641b8-122">This example updates a specific module to the newest version in an online gallery.</span></span>

```powershell
Update-Module -Name SpeculationControl
```

<span data-ttu-id="641b8-123">`Update-Module` verwendet den **Name** -Parameter, um ein bestimmtes Modul, " **speculationcontrol**", zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="641b8-123">`Update-Module` uses the **Name** parameter to update a specific module, **SpeculationControl**.</span></span>

### <span data-ttu-id="641b8-124">Beispiel 3: Anzeigen der was-wäre-wenn-Update-Module ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="641b8-124">Example 3: View what-if Update-Module runs</span></span>

<span data-ttu-id="641b8-125">In diesem Beispiel wird das was-wäre-wenn-Szenario veranschaulicht, um anzuzeigen, was geschieht, wenn `Update-Module` ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="641b8-125">This example does a what-if scenario to show what happens if `Update-Module` is run.</span></span> <span data-ttu-id="641b8-126">Der Befehl wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="641b8-126">The command isn't run.</span></span>

```powershell
Update-Module -WhatIf
```

```Output
What if: Performing the operation "Update-Module" on target "Version '2.8.0' of module
  'Carbon', updating to version '2.8.1'".
What if: Performing the operation "Update-Module" on target "Version '1.0.10' of module
  'SpeculationControl', updating to version '1.0.14'".
```

<span data-ttu-id="641b8-127">`Update-Module` verwendet den **WhatIf** -Parameter zeigt an, was passieren würde, wenn `Update-Module` ausgeführt würde.</span><span class="sxs-lookup"><span data-stu-id="641b8-127">`Update-Module` uses the **WhatIf** parameter display what would happen if `Update-Module` were run.</span></span>

### <span data-ttu-id="641b8-128">Beispiel 4: Aktualisieren eines Moduls auf eine angegebene Version</span><span class="sxs-lookup"><span data-stu-id="641b8-128">Example 4: Update a module to a specified version</span></span>

<span data-ttu-id="641b8-129">In diesem Beispiel wird ein Modul auf eine bestimmte Version aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="641b8-129">In this example, a module is updated to a specific version.</span></span> <span data-ttu-id="641b8-130">Die Version muss im Onlinekatalog vorhanden sein, oder es wird ein Fehler angezeigt.</span><span class="sxs-lookup"><span data-stu-id="641b8-130">The version must exist in the online gallery or an error is displayed.</span></span>

```powershell
Update-Module -Name SpeculationControl -RequiredVersion 1.0.14
```

<span data-ttu-id="641b8-131">`Update-Module` verwendet den **Name** -Parameter, um das Modul " **speculationcontrol**" anzugeben.</span><span class="sxs-lookup"><span data-stu-id="641b8-131">`Update-Module` uses the **Name** parameter to specify the module, **SpeculationControl**.</span></span> <span data-ttu-id="641b8-132">Der Requirements **dversion** -Parameter gibt die Version an, **1.0.14**.</span><span class="sxs-lookup"><span data-stu-id="641b8-132">The **RequiredVersion** parameter specifies the version, **1.0.14**.</span></span>

### <span data-ttu-id="641b8-133">Beispiel 5: Aktualisieren eines Moduls ohne Bestätigung</span><span class="sxs-lookup"><span data-stu-id="641b8-133">Example 5: Update a module without confirmation</span></span>

<span data-ttu-id="641b8-134">Dieses Beispiel fordert keine Bestätigung zum Aktualisieren des Moduls auf die neueste Version aus einem Onlinekatalog an.</span><span class="sxs-lookup"><span data-stu-id="641b8-134">This example doesn't request confirmation to update the module to the newest version from an online gallery.</span></span> <span data-ttu-id="641b8-135">Wenn das Modul bereits installiert ist, wird das Modul durch den **Force** -Parameter neu installiert.</span><span class="sxs-lookup"><span data-stu-id="641b8-135">If the module is already installed, the **Force** parameter reinstalls the module.</span></span>

```powershell
Update-Module -Name SpeculationControl -Force
```

<span data-ttu-id="641b8-136">`Update-Module` verwendet den **Name** -Parameter, um das Modul " **speculationcontrol**" anzugeben.</span><span class="sxs-lookup"><span data-stu-id="641b8-136">`Update-Module` uses the **Name** parameter to specify the module, **SpeculationControl**.</span></span> <span data-ttu-id="641b8-137">Der **Force** -Parameter aktualisiert das Modul, ohne die Benutzer Bestätigung anzufordern.</span><span class="sxs-lookup"><span data-stu-id="641b8-137">The **Force** parameter updates the module without requesting user confirmation.</span></span>

## <span data-ttu-id="641b8-138">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="641b8-138">PARAMETERS</span></span>

### <span data-ttu-id="641b8-139">-AcceptLicense</span><span class="sxs-lookup"><span data-stu-id="641b8-139">-AcceptLicense</span></span>

<span data-ttu-id="641b8-140">Akzeptieren Sie den Lizenzvertrag während der Installation automatisch, wenn dies für das Paket erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="641b8-140">Automatically accept the license agreement during installation if the package requires it.</span></span>

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

### <span data-ttu-id="641b8-141">-Allowprerelease</span><span class="sxs-lookup"><span data-stu-id="641b8-141">-AllowPrerelease</span></span>

<span data-ttu-id="641b8-142">Ermöglicht es Ihnen, ein Modul mit dem neueren Modul zu aktualisieren, das als Vorabversion markiert ist.</span><span class="sxs-lookup"><span data-stu-id="641b8-142">Allows you to update a module with the newer module marked as a prerelease.</span></span>

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

### <span data-ttu-id="641b8-143">-Confirm</span><span class="sxs-lookup"><span data-stu-id="641b8-143">-Confirm</span></span>

<span data-ttu-id="641b8-144">Sie werden zur Bestätigung aufgefordert, bevor Sie ausgeführt werden `Update-Module` .</span><span class="sxs-lookup"><span data-stu-id="641b8-144">Prompts you for confirmation before running `Update-Module`.</span></span>

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

### <span data-ttu-id="641b8-145">-Credential</span><span class="sxs-lookup"><span data-stu-id="641b8-145">-Credential</span></span>

<span data-ttu-id="641b8-146">Gibt ein Benutzerkonto an, das über die Berechtigung zum Aktualisieren eines Moduls verfügt.</span><span class="sxs-lookup"><span data-stu-id="641b8-146">Specifies a user account that has permission to update a module.</span></span>

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

### <span data-ttu-id="641b8-147">-Force</span><span class="sxs-lookup"><span data-stu-id="641b8-147">-Force</span></span>

<span data-ttu-id="641b8-148">Erzwingt ein Update der einzelnen angegebenen Module, ohne dass eine Bestätigung angefordert werden muss.</span><span class="sxs-lookup"><span data-stu-id="641b8-148">Forces an update of each specified module without a prompt to request confirmation.</span></span> <span data-ttu-id="641b8-149">Wenn das Modul bereits installiert ist, wird das Modul von **Force** neu installiert.</span><span class="sxs-lookup"><span data-stu-id="641b8-149">If the module is already installed, **Force** reinstalls the module.</span></span>

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

### <span data-ttu-id="641b8-150">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="641b8-150">-MaximumVersion</span></span>

<span data-ttu-id="641b8-151">Gibt die maximale Version eines einzelnen zu aktualisierenden Moduls an.</span><span class="sxs-lookup"><span data-stu-id="641b8-151">Specifies the maximum version of a single module to update.</span></span> <span data-ttu-id="641b8-152">Dieser Parameter kann nicht hinzugefügt werden, wenn Sie versuchen, mehrere Module zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="641b8-152">You can't add this parameter if you're attempting to update multiple modules.</span></span> <span data-ttu-id="641b8-153">Die Parameter " **MaximumVersion** " und "Requirements **dversion** " können nicht im selben Befehl verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="641b8-153">The **MaximumVersion** and the **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="641b8-154">-Name</span><span class="sxs-lookup"><span data-stu-id="641b8-154">-Name</span></span>

<span data-ttu-id="641b8-155">Gibt die Namen von einem oder mehreren zu aktualisierenden Modulen an.</span><span class="sxs-lookup"><span data-stu-id="641b8-155">Specifies the names of one or more modules to update.</span></span> <span data-ttu-id="641b8-156">`Update-Module` sucht `$env:PSModulePath` nach den zu Aktualisier-Modulen.</span><span class="sxs-lookup"><span data-stu-id="641b8-156">`Update-Module` searches `$env:PSModulePath` for the modules to update.</span></span> <span data-ttu-id="641b8-157">Wenn `$env:PSModulePath` für den angegebenen Modulnamen keine Übereinstimmungen gefunden werden, tritt ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="641b8-157">If no matches are found in `$env:PSModulePath` for the specified module name, an error occurs.</span></span>

<span data-ttu-id="641b8-158">Platzhalter werden in Modulnamen akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="641b8-158">Wildcards are accepted in module names.</span></span> <span data-ttu-id="641b8-159">Wenn Sie dem angegebenen Namen Platzhalter Zeichen hinzufügen und keine Übereinstimmungen gefunden werden, tritt kein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="641b8-159">If you add wildcard characters to the specified name and no matches are found, no error occurs.</span></span>

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

### <span data-ttu-id="641b8-160">-PassThru</span><span class="sxs-lookup"><span data-stu-id="641b8-160">-PassThru</span></span>

<span data-ttu-id="641b8-161">Gibt ein Objekt zurück, das das Element darstellt, mit dem Sie arbeiten.</span><span class="sxs-lookup"><span data-stu-id="641b8-161">Returns an object representing the item with which you are working.</span></span> <span data-ttu-id="641b8-162">Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="641b8-162">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="641b8-163">-Proxy</span><span class="sxs-lookup"><span data-stu-id="641b8-163">-Proxy</span></span>

<span data-ttu-id="641b8-164">Gibt einen Proxy Server für die Anforderung an, anstatt eine direkte Verbindung mit einer Internet Ressource herzustellen.</span><span class="sxs-lookup"><span data-stu-id="641b8-164">Specifies a proxy server for the request, rather than connecting directly to an internet resource.</span></span>

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

### <span data-ttu-id="641b8-165">-Proxy Credential</span><span class="sxs-lookup"><span data-stu-id="641b8-165">-ProxyCredential</span></span>

<span data-ttu-id="641b8-166">Gibt ein Benutzerkonto an, das über die Berechtigung zum Verwenden des Proxy Servers verfügt, der durch den **Proxy** Parameter angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="641b8-166">Specifies a user account that has permission to use the proxy server specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="641b8-167">-Requirements dversion</span><span class="sxs-lookup"><span data-stu-id="641b8-167">-RequiredVersion</span></span>

<span data-ttu-id="641b8-168">Gibt die genaue Version an, auf die das vorhandene installierte Modul aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="641b8-168">Specifies the exact version to which the existing installed module will be updated.</span></span> <span data-ttu-id="641b8-169">Die Version, die von "Requirements **dversion** " angegeben wird, muss im Onlinekatalog vorhanden sein, oder es wird ein Fehler angezeigt.</span><span class="sxs-lookup"><span data-stu-id="641b8-169">The version specified by **RequiredVersion** must exist in the online gallery or an error is displayed.</span></span> <span data-ttu-id="641b8-170">Wenn mehr als ein Modul in einem einzigen Befehl aktualisiert wird, können Sie "Requirements **dversion**" nicht verwenden.</span><span class="sxs-lookup"><span data-stu-id="641b8-170">If more than one module is updated in a single command, you can't use **RequiredVersion**.</span></span>

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

### <span data-ttu-id="641b8-171">-Bereich</span><span class="sxs-lookup"><span data-stu-id="641b8-171">-Scope</span></span>

<span data-ttu-id="641b8-172">Gibt den Bereich der Installation des Moduls an.</span><span class="sxs-lookup"><span data-stu-id="641b8-172">Specifies the installation scope of the module.</span></span> <span data-ttu-id="641b8-173">Die zulässigen Werte für diesen Parameter sind **ALLUSERS** und **CurrentUser**.</span><span class="sxs-lookup"><span data-stu-id="641b8-173">The acceptable values for this parameter are **AllUsers** and **CurrentUser**.</span></span> <span data-ttu-id="641b8-174">Wenn der **Bereich** nicht angegeben wird, wird das Update im Bereich **CurrentUser** installiert.</span><span class="sxs-lookup"><span data-stu-id="641b8-174">If **Scope** isn't specified, the update is installed in the **CurrentUser** scope.</span></span>

<span data-ttu-id="641b8-175">Der Bereich " **ALLUSERS** " erfordert erhöhte Berechtigungen und installiert Module an einem Speicherort, auf den alle Benutzer des Computers zugreifen können:</span><span class="sxs-lookup"><span data-stu-id="641b8-175">The **AllUsers** scope requires elevated permissions and installs modules in a location that is accessible to all users of the computer:</span></span>

`$env:ProgramFiles\PowerShell\Modules`

<span data-ttu-id="641b8-176">**CurrentUser** benötigt keine erhöhten Berechtigungen und installiert Module an einem Speicherort, auf den nur der aktuelle Benutzer des Computers zugreifen kann:</span><span class="sxs-lookup"><span data-stu-id="641b8-176">The **CurrentUser** doesn't require elevated permissions and installs modules in a location that is accessible only to the current user of the computer:</span></span>

`$home\Documents\PowerShell\Modules`

<span data-ttu-id="641b8-177">Wenn kein **Bereich** definiert ist, wird der Standardwert basierend auf der PowerShellGet-Version festgelegt.</span><span class="sxs-lookup"><span data-stu-id="641b8-177">When no **Scope** is defined, the default is set based on the PowerShellGet version.</span></span>

- <span data-ttu-id="641b8-178">In PowerShellGet Version 2.0.0 und höher ist der Standardwert **CurrentUser**, der keine Erhöhung der Rechte für die Installation erfordert.</span><span class="sxs-lookup"><span data-stu-id="641b8-178">In PowerShellGet versions 2.0.0 and above, the default is **CurrentUser**, which does not require elevation for install.</span></span>
- <span data-ttu-id="641b8-179">In PowerShellGet 1. x-Versionen ist der Standardwert " **ALLUSERS**", für den eine Erhöhung der Installation erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="641b8-179">In PowerShellGet 1.x versions, the default is **AllUsers**, which requires elevation for install.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: CurrentUser, AllUsers

Required: False
Position: Named
Default value: CurrentUser
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="641b8-180">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="641b8-180">-WhatIf</span></span>

<span data-ttu-id="641b8-181">Zeigt, was geschieht, wenn ausgeführt wird `Update-Module` .</span><span class="sxs-lookup"><span data-stu-id="641b8-181">Shows what would happen if `Update-Module` runs.</span></span> <span data-ttu-id="641b8-182">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="641b8-182">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="641b8-183">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="641b8-183">CommonParameters</span></span>

<span data-ttu-id="641b8-184">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="641b8-184">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="641b8-185">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="641b8-185">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="641b8-186">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="641b8-186">INPUTS</span></span>

### <span data-ttu-id="641b8-187">System.String[]</span><span class="sxs-lookup"><span data-stu-id="641b8-187">System.String[]</span></span>

### <span data-ttu-id="641b8-188">System.String</span><span class="sxs-lookup"><span data-stu-id="641b8-188">System.String</span></span>

### <span data-ttu-id="641b8-189">System. Management. Automation. PSCredential</span><span class="sxs-lookup"><span data-stu-id="641b8-189">System.Management.Automation.PSCredential</span></span>

### <span data-ttu-id="641b8-190">System.Uri</span><span class="sxs-lookup"><span data-stu-id="641b8-190">System.Uri</span></span>

## <span data-ttu-id="641b8-191">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="641b8-191">OUTPUTS</span></span>

### <span data-ttu-id="641b8-192">System.Object</span><span class="sxs-lookup"><span data-stu-id="641b8-192">System.Object</span></span>

## <span data-ttu-id="641b8-193">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="641b8-193">NOTES</span></span>

<span data-ttu-id="641b8-194">Für PowerShell, Version 6,0 und höher, ist der Standard Installationsbereich immer **CurrentUser**.</span><span class="sxs-lookup"><span data-stu-id="641b8-194">For PowerShell version 6.0 and above, the default installation scope is always **CurrentUser**.</span></span>
<span data-ttu-id="641b8-195">Modulupdates für **CurrentUser**, `$home\Documents\PowerShell\Modules` , benötigen keine erhöhten Berechtigungen.</span><span class="sxs-lookup"><span data-stu-id="641b8-195">Module updates for **CurrentUser**, `$home\Documents\PowerShell\Modules`, don't need elevated permissions.</span></span> <span data-ttu-id="641b8-196">Modulupdates für **ALLUSERS**, `$env:ProgramFiles\PowerShell\Modules` , benötigen erhöhte Berechtigungen.</span><span class="sxs-lookup"><span data-stu-id="641b8-196">Module updates for **AllUsers**, `$env:ProgramFiles\PowerShell\Modules`, need elevated permissions.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="641b8-197">Ab April 2020 unterstützt der PowerShell-Katalog die TLS-Versionen (Transport Layer Security) 1.0 und 1.1 nicht mehr.</span><span class="sxs-lookup"><span data-stu-id="641b8-197">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="641b8-198">Wenn Sie nicht TLS 1.2 oder höher verwenden, erhalten Sie beim Versuch des Zugriffs auf den PowerShell-Katalog eine Fehlermeldung.</span><span class="sxs-lookup"><span data-stu-id="641b8-198">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="641b8-199">Mit dem folgenden Befehl können Sie sicherstellen, dass Sie TLS 1.2 verwenden:</span><span class="sxs-lookup"><span data-stu-id="641b8-199">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="641b8-200">Weitere Informationen finden Sie im PowerShell-Blog in der [Ankündigung](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/).</span><span class="sxs-lookup"><span data-stu-id="641b8-200">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

<span data-ttu-id="641b8-201">`Update-Module` wird in PowerShell 3,0 oder höheren Versionen von PowerShell unter Windows 7 oder Windows 2008 R2 und höheren Versionen von Windows ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="641b8-201">`Update-Module` runs on PowerShell 3.0 or later releases of PowerShell, on Windows 7 or Windows 2008 R2 and later releases of Windows.</span></span>

<span data-ttu-id="641b8-202">Wenn das Modul, das Sie mit dem **Name** -Parameter angeben, nicht mithilfe von installiert `Install-Module` wurde, tritt ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="641b8-202">If the module that you specify with the **Name** parameter wasn't installed by using `Install-Module`, an error occurs.</span></span>

<span data-ttu-id="641b8-203">Sie können nur `Update-Module` Module ausführen, die Sie aus dem Onlinekatalog installiert haben, indem Sie Ausführen `Install-Module` .</span><span class="sxs-lookup"><span data-stu-id="641b8-203">You can only run `Update-Module` on modules that you installed from the online gallery by running `Install-Module`.</span></span>

<span data-ttu-id="641b8-204">Wenn `Update-Module` versucht, Binärdateien zu aktualisieren, die verwendet werden, `Update-Module` gibt einen Fehler zurück, der die Problem Prozesse identifiziert.</span><span class="sxs-lookup"><span data-stu-id="641b8-204">If `Update-Module` attempts to update binaries that are in use, `Update-Module` returns an error that identifies the problem processes.</span></span> <span data-ttu-id="641b8-205">Der Benutzer wird informiert, dass er `Update-Module` nach dem Beenden der Prozesse wiederholt werden soll.</span><span class="sxs-lookup"><span data-stu-id="641b8-205">The user is informed to retry `Update-Module` after the processes are stopped.</span></span>

## <span data-ttu-id="641b8-206">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="641b8-206">RELATED LINKS</span></span>

[<span data-ttu-id="641b8-207">Find-Module</span><span class="sxs-lookup"><span data-stu-id="641b8-207">Find-Module</span></span>](Find-Module.md)

[<span data-ttu-id="641b8-208">Get-InstalledModule</span><span class="sxs-lookup"><span data-stu-id="641b8-208">Get-InstalledModule</span></span>](Get-InstalledModule.md)

[<span data-ttu-id="641b8-209">Install-Module</span><span class="sxs-lookup"><span data-stu-id="641b8-209">Install-Module</span></span>](Install-Module.md)

[<span data-ttu-id="641b8-210">Publish-Module</span><span class="sxs-lookup"><span data-stu-id="641b8-210">Publish-Module</span></span>](Publish-Module.md)

[<span data-ttu-id="641b8-211">Uninstall-Module</span><span class="sxs-lookup"><span data-stu-id="641b8-211">Uninstall-Module</span></span>](Uninstall-Module.md)
