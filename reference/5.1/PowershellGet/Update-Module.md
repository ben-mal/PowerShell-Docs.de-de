---
external help file: PSModule-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PowerShellGet
ms.date: 07/16/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/update-module?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Update-Module
ms.openlocfilehash: 719eaa019dd721b156b26d2e38e8790e6b9af584
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215167"
---
# <span data-ttu-id="f9c74-103">Update-Module</span><span class="sxs-lookup"><span data-stu-id="f9c74-103">Update-Module</span></span>

## <span data-ttu-id="f9c74-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="f9c74-104">SYNOPSIS</span></span>
<span data-ttu-id="f9c74-105">Lädt die neueste Version der angegebenen Module aus einem Onlinekatalog auf den lokalen Computer herunter und installiert diese</span><span class="sxs-lookup"><span data-stu-id="f9c74-105">Downloads and installs the newest version of specified modules from an online gallery to the local computer.</span></span>

## <span data-ttu-id="f9c74-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="f9c74-106">SYNTAX</span></span>

### <span data-ttu-id="f9c74-107">Alle</span><span class="sxs-lookup"><span data-stu-id="f9c74-107">All</span></span>

```
Update-Module [[-Name] <String[]>] [-RequiredVersion <String>] [-MaximumVersion <String>]
 [-Credential <PSCredential>] [-Scope <String>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-Force] [-AllowPrerelease] [-AcceptLicense] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="f9c74-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="f9c74-108">DESCRIPTION</span></span>

<span data-ttu-id="f9c74-109">Mit dem `Update-Module` -Cmdlet wird die neueste Version eines Moduls aus einem Onlinekatalog installiert.</span><span class="sxs-lookup"><span data-stu-id="f9c74-109">The `Update-Module` cmdlet installs a module's newest version from an online gallery.</span></span> <span data-ttu-id="f9c74-110">Sie werden aufgefordert, das Update vor der Installation zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="f9c74-110">You're prompted to confirm the update before it's installed.</span></span> <span data-ttu-id="f9c74-111">Updates werden nur für Module installiert, die mit auf dem lokalen Computer installiert wurden `Install-Module` .</span><span class="sxs-lookup"><span data-stu-id="f9c74-111">Updates are installed only for modules that were installed on the local computer with `Install-Module`.</span></span> <span data-ttu-id="f9c74-112">`Update-Module` sucht `$env:PSModulePath` nach installierten Modulen.</span><span class="sxs-lookup"><span data-stu-id="f9c74-112">`Update-Module` searches `$env:PSModulePath` for installed modules.</span></span>

<span data-ttu-id="f9c74-113">`Update-Module` Wenn keine Parameter angegeben sind, werden alle installierten Module aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="f9c74-113">`Update-Module` with no parameters specified updates all installed modules.</span></span> <span data-ttu-id="f9c74-114">Verwenden Sie den **Name** -Parameter, um ein Modul anzugeben, das aktualisiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="f9c74-114">To specify a module to update, use the **Name** parameter.</span></span> <span data-ttu-id="f9c74-115">Mithilfe des Parameters "Requirements **dversion** " können Sie ein Update auf die spezifische Version eines Moduls durchsetzen.</span><span class="sxs-lookup"><span data-stu-id="f9c74-115">You can update to a module's specific version by using the **RequiredVersion** parameter.</span></span>

<span data-ttu-id="f9c74-116">Wenn ein installiertes Modul bereits die neueste Version ist, wird das Modul nicht aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="f9c74-116">If an installed module is already the newest version, the module isn't updated.</span></span> <span data-ttu-id="f9c74-117">Wenn das Modul in nicht gefunden wird `$env:PSModulePath` , wird ein Fehler angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f9c74-117">If the module isn't found in `$env:PSModulePath`, an error is displayed.</span></span>

<span data-ttu-id="f9c74-118">Verwenden Sie, um die installierten Module anzuzeigen `Get-InstalledModule` .</span><span class="sxs-lookup"><span data-stu-id="f9c74-118">To display the installed modules, use `Get-InstalledModule`.</span></span>

## <span data-ttu-id="f9c74-119">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="f9c74-119">EXAMPLES</span></span>

### <span data-ttu-id="f9c74-120">Beispiel 1: Aktualisieren aller Module</span><span class="sxs-lookup"><span data-stu-id="f9c74-120">Example 1: Update all modules</span></span>

<span data-ttu-id="f9c74-121">In diesem Beispiel werden alle installierten Module auf die neueste Version in einem Onlinekatalog aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="f9c74-121">This example updates all installed modules to the newest version in an online gallery.</span></span>

```powershell
Update-Module
```

### <span data-ttu-id="f9c74-122">Beispiel 2: Aktualisieren eines Moduls nach Name</span><span class="sxs-lookup"><span data-stu-id="f9c74-122">Example 2: Update a module by name</span></span>

<span data-ttu-id="f9c74-123">In diesem Beispiel wird ein bestimmtes Modul auf die neueste Version in einem Onlinekatalog aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="f9c74-123">This example updates a specific module to the newest version in an online gallery.</span></span>

```powershell
Update-Module -Name SpeculationControl
```

<span data-ttu-id="f9c74-124">`Update-Module` verwendet den **Name** -Parameter, um ein bestimmtes Modul, " **speculationcontrol** ", zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="f9c74-124">`Update-Module` uses the **Name** parameter to update a specific module, **SpeculationControl** .</span></span>

### <span data-ttu-id="f9c74-125">Beispiel 3: Anzeigen der was-wäre-wenn-Update-Module ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="f9c74-125">Example 3: View what-if Update-Module runs</span></span>

<span data-ttu-id="f9c74-126">In diesem Beispiel wird das was-wäre-wenn-Szenario veranschaulicht, um anzuzeigen, was geschieht, wenn `Update-Module` ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="f9c74-126">This example does a what-if scenario to show what happens if `Update-Module` is run.</span></span> <span data-ttu-id="f9c74-127">Der Befehl wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="f9c74-127">The command isn't run.</span></span>

```powershell
Update-Module -WhatIf
```

```Output
What if: Performing the operation "Update-Module" on target "Version '2.8.0' of module
  'Carbon', updating to version '2.8.1'".
What if: Performing the operation "Update-Module" on target "Version '1.0.10' of module
  'SpeculationControl', updating to version '1.0.14'".
```

<span data-ttu-id="f9c74-128">`Update-Module` verwendet den **WhatIf** -Parameter zeigt an, was passieren würde, wenn `Update-Module` ausgeführt würde.</span><span class="sxs-lookup"><span data-stu-id="f9c74-128">`Update-Module` uses the **WhatIf** parameter display what would happen if `Update-Module` were run.</span></span>

### <span data-ttu-id="f9c74-129">Beispiel 4: Aktualisieren eines Moduls auf eine angegebene Version</span><span class="sxs-lookup"><span data-stu-id="f9c74-129">Example 4: Update a module to a specified version</span></span>

<span data-ttu-id="f9c74-130">In diesem Beispiel wird ein Modul auf eine bestimmte Version aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="f9c74-130">In this example, a module is updated to a specific version.</span></span> <span data-ttu-id="f9c74-131">Die Version muss im Onlinekatalog vorhanden sein, oder es wird ein Fehler angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f9c74-131">The version must exist in the online gallery or an error is displayed.</span></span>

```powershell
Update-Module -Name SpeculationControl -RequiredVersion 1.0.14
```

<span data-ttu-id="f9c74-132">`Update-Module` verwendet den **Name** -Parameter, um das Modul " **speculationcontrol** " anzugeben.</span><span class="sxs-lookup"><span data-stu-id="f9c74-132">`Update-Module` uses the **Name** parameter to specify the module, **SpeculationControl** .</span></span> <span data-ttu-id="f9c74-133">Der Requirements **dversion** -Parameter gibt die Version an, **1.0.14** .</span><span class="sxs-lookup"><span data-stu-id="f9c74-133">The **RequiredVersion** parameter specifies the version, **1.0.14** .</span></span>

### <span data-ttu-id="f9c74-134">Beispiel 5: Aktualisieren eines Moduls ohne Bestätigung</span><span class="sxs-lookup"><span data-stu-id="f9c74-134">Example 5: Update a module without confirmation</span></span>

<span data-ttu-id="f9c74-135">Dieses Beispiel fordert keine Bestätigung zum Aktualisieren des Moduls auf die neueste Version aus einem Onlinekatalog an.</span><span class="sxs-lookup"><span data-stu-id="f9c74-135">This example doesn't request confirmation to update the module to the newest version from an online gallery.</span></span> <span data-ttu-id="f9c74-136">Wenn das Modul bereits installiert ist, wird das Modul durch den **Force** -Parameter neu installiert.</span><span class="sxs-lookup"><span data-stu-id="f9c74-136">If the module is already installed, the **Force** parameter reinstalls the module.</span></span>

```powershell
Update-Module -Name SpeculationControl -Force
```

<span data-ttu-id="f9c74-137">`Update-Module` verwendet den **Name** -Parameter, um das Modul " **speculationcontrol** " anzugeben.</span><span class="sxs-lookup"><span data-stu-id="f9c74-137">`Update-Module` uses the **Name** parameter to specify the module, **SpeculationControl** .</span></span> <span data-ttu-id="f9c74-138">Der **Force** -Parameter aktualisiert das Modul, ohne die Benutzer Bestätigung anzufordern.</span><span class="sxs-lookup"><span data-stu-id="f9c74-138">The **Force** parameter updates the module without requesting user confirmation.</span></span>

## <span data-ttu-id="f9c74-139">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="f9c74-139">PARAMETERS</span></span>

### <span data-ttu-id="f9c74-140">-AcceptLicense</span><span class="sxs-lookup"><span data-stu-id="f9c74-140">-AcceptLicense</span></span>

<span data-ttu-id="f9c74-141">Akzeptieren Sie den Lizenzvertrag während der Installation automatisch, wenn dies für das Paket erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="f9c74-141">Automatically accept the license agreement during installation if the package requires it.</span></span>

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

### <span data-ttu-id="f9c74-142">-Allowprerelease</span><span class="sxs-lookup"><span data-stu-id="f9c74-142">-AllowPrerelease</span></span>

<span data-ttu-id="f9c74-143">Ermöglicht es Ihnen, ein Modul mit dem neueren Modul zu aktualisieren, das als Vorabversion markiert ist.</span><span class="sxs-lookup"><span data-stu-id="f9c74-143">Allows you to update a module with the newer module marked as a prerelease.</span></span>

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

### <span data-ttu-id="f9c74-144">-Confirm</span><span class="sxs-lookup"><span data-stu-id="f9c74-144">-Confirm</span></span>

<span data-ttu-id="f9c74-145">Sie werden zur Bestätigung aufgefordert, bevor Sie ausgeführt werden `Update-Module` .</span><span class="sxs-lookup"><span data-stu-id="f9c74-145">Prompts you for confirmation before running `Update-Module`.</span></span>

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

### <span data-ttu-id="f9c74-146">-Credential</span><span class="sxs-lookup"><span data-stu-id="f9c74-146">-Credential</span></span>

<span data-ttu-id="f9c74-147">Gibt ein Benutzerkonto an, das über die Berechtigung zum Aktualisieren eines Moduls verfügt.</span><span class="sxs-lookup"><span data-stu-id="f9c74-147">Specifies a user account that has permission to update a module.</span></span>

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

### <span data-ttu-id="f9c74-148">-Force</span><span class="sxs-lookup"><span data-stu-id="f9c74-148">-Force</span></span>

<span data-ttu-id="f9c74-149">Erzwingt ein Update der einzelnen angegebenen Module, ohne dass eine Bestätigung angefordert werden muss.</span><span class="sxs-lookup"><span data-stu-id="f9c74-149">Forces an update of each specified module without a prompt to request confirmation.</span></span> <span data-ttu-id="f9c74-150">Wenn das Modul bereits installiert ist, wird das Modul von **Force** neu installiert.</span><span class="sxs-lookup"><span data-stu-id="f9c74-150">If the module is already installed, **Force** reinstalls the module.</span></span>

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

### <span data-ttu-id="f9c74-151">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="f9c74-151">-MaximumVersion</span></span>

<span data-ttu-id="f9c74-152">Gibt die maximale Version eines einzelnen zu aktualisierenden Moduls an.</span><span class="sxs-lookup"><span data-stu-id="f9c74-152">Specifies the maximum version of a single module to update.</span></span> <span data-ttu-id="f9c74-153">Dieser Parameter kann nicht hinzugefügt werden, wenn Sie versuchen, mehrere Module zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="f9c74-153">You can't add this parameter if you're attempting to update multiple modules.</span></span> <span data-ttu-id="f9c74-154">Die Parameter " **MaximumVersion** " und "Requirements **dversion** " können nicht im selben Befehl verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f9c74-154">The **MaximumVersion** and the **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="f9c74-155">-Name</span><span class="sxs-lookup"><span data-stu-id="f9c74-155">-Name</span></span>

<span data-ttu-id="f9c74-156">Gibt die Namen von einem oder mehreren zu aktualisierenden Modulen an.</span><span class="sxs-lookup"><span data-stu-id="f9c74-156">Specifies the names of one or more modules to update.</span></span> <span data-ttu-id="f9c74-157">`Update-Module` sucht `$env:PSModulePath` nach den zu Aktualisier-Modulen.</span><span class="sxs-lookup"><span data-stu-id="f9c74-157">`Update-Module` searches `$env:PSModulePath` for the modules to update.</span></span> <span data-ttu-id="f9c74-158">Wenn `$env:PSModulePath` für den angegebenen Modulnamen keine Übereinstimmungen gefunden werden, tritt ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="f9c74-158">If no matches are found in `$env:PSModulePath` for the specified module name, an error occurs.</span></span>

<span data-ttu-id="f9c74-159">Platzhalter werden in Modulnamen akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="f9c74-159">Wildcards are accepted in module names.</span></span> <span data-ttu-id="f9c74-160">Wenn Sie dem angegebenen Namen Platzhalter Zeichen hinzufügen und keine Übereinstimmungen gefunden werden, tritt kein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="f9c74-160">If you add wildcard characters to the specified name and no matches are found, no error occurs.</span></span>

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

### <span data-ttu-id="f9c74-161">-PassThru</span><span class="sxs-lookup"><span data-stu-id="f9c74-161">-PassThru</span></span>

<span data-ttu-id="f9c74-162">Gibt ein Objekt zurück, das das Element darstellt, mit dem Sie arbeiten.</span><span class="sxs-lookup"><span data-stu-id="f9c74-162">Returns an object representing the item with which you are working.</span></span> <span data-ttu-id="f9c74-163">Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="f9c74-163">By default, this cmdlet does not generate any output.</span></span> <span data-ttu-id="f9c74-164">Die Unterstützung für **passthru** -Parameter wurde in **PowerShellGet** 2.0.0 hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="f9c74-164">The **PassThru** parameter support was added in **PowerShellGet** 2.0.0</span></span>

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

### <span data-ttu-id="f9c74-165">-Proxy</span><span class="sxs-lookup"><span data-stu-id="f9c74-165">-Proxy</span></span>

<span data-ttu-id="f9c74-166">Gibt einen Proxy Server für die Anforderung an, anstatt eine direkte Verbindung mit einer Internet Ressource herzustellen.</span><span class="sxs-lookup"><span data-stu-id="f9c74-166">Specifies a proxy server for the request, rather than connecting directly to an internet resource.</span></span>

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

### <span data-ttu-id="f9c74-167">-Proxy Credential</span><span class="sxs-lookup"><span data-stu-id="f9c74-167">-ProxyCredential</span></span>

<span data-ttu-id="f9c74-168">Gibt ein Benutzerkonto an, das über die Berechtigung zum Verwenden des Proxy Servers verfügt, der durch den **Proxy** Parameter angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="f9c74-168">Specifies a user account that has permission to use the proxy server specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="f9c74-169">-Requirements dversion</span><span class="sxs-lookup"><span data-stu-id="f9c74-169">-RequiredVersion</span></span>

<span data-ttu-id="f9c74-170">Gibt die genaue Version an, auf die das vorhandene installierte Modul aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="f9c74-170">Specifies the exact version to which the existing installed module will be updated.</span></span> <span data-ttu-id="f9c74-171">Die Version, die von "Requirements **dversion** " angegeben wird, muss im Onlinekatalog vorhanden sein, oder es wird ein Fehler angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f9c74-171">The version specified by **RequiredVersion** must exist in the online gallery or an error is displayed.</span></span> <span data-ttu-id="f9c74-172">Wenn mehr als ein Modul in einem einzigen Befehl aktualisiert wird, können Sie "Requirements **dversion** " nicht verwenden.</span><span class="sxs-lookup"><span data-stu-id="f9c74-172">If more than one module is updated in a single command, you can't use **RequiredVersion** .</span></span>

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

### <span data-ttu-id="f9c74-173">-Bereich</span><span class="sxs-lookup"><span data-stu-id="f9c74-173">-Scope</span></span>

<span data-ttu-id="f9c74-174">Gibt den Bereich der Installation des Moduls an.</span><span class="sxs-lookup"><span data-stu-id="f9c74-174">Specifies the installation scope of the module.</span></span> <span data-ttu-id="f9c74-175">Die zulässigen Werte für diesen Parameter sind **ALLUSERS** und **CurrentUser** .</span><span class="sxs-lookup"><span data-stu-id="f9c74-175">The acceptable values for this parameter are **AllUsers** and **CurrentUser** .</span></span> <span data-ttu-id="f9c74-176">Wenn der **Bereich** nicht angegeben wird, wird das Update im Bereich **CurrentUser** installiert.</span><span class="sxs-lookup"><span data-stu-id="f9c74-176">If **Scope** isn't specified, the update is installed in the **CurrentUser** scope.</span></span>

<span data-ttu-id="f9c74-177">Der Bereich " **ALLUSERS** " erfordert erhöhte Berechtigungen und installiert Module an einem Speicherort, auf den alle Benutzer des Computers zugreifen können:</span><span class="sxs-lookup"><span data-stu-id="f9c74-177">The **AllUsers** scope requires elevated permissions and installs modules in a location that is accessible to all users of the computer:</span></span>

`$env:ProgramFiles\PowerShell\Modules`

<span data-ttu-id="f9c74-178">**CurrentUser** benötigt keine erhöhten Berechtigungen und installiert Module an einem Speicherort, auf den nur der aktuelle Benutzer des Computers zugreifen kann:</span><span class="sxs-lookup"><span data-stu-id="f9c74-178">The **CurrentUser** doesn't require elevated permissions and installs modules in a location that is accessible only to the current user of the computer:</span></span>

`$home\Documents\PowerShell\Modules`

<span data-ttu-id="f9c74-179">Wenn kein **Bereich** definiert ist, wird der Standardwert basierend auf der PowerShellGet-Version festgelegt.</span><span class="sxs-lookup"><span data-stu-id="f9c74-179">When no **Scope** is defined, the default is set based on the PowerShellGet version.</span></span>

- <span data-ttu-id="f9c74-180">In PowerShellGet Version 2.0.0 und höher ist der Standardwert **ALLUSERS** , wenn eine Sitzung mit erhöhten Rechten ausgeführt wird, und **CurrentUser** für alle anderen.</span><span class="sxs-lookup"><span data-stu-id="f9c74-180">In PowerShellGet versions 2.0.0 and above, the default is **AllUsers** when running an elevated session and **CurrentUser** for all others.</span></span>
- <span data-ttu-id="f9c74-181">In PowerShellGet 1. x-Versionen ist der Standardwert " **ALLUSERS** ", für den eine Erhöhung der Installation erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="f9c74-181">In PowerShellGet 1.x versions, the default is **AllUsers** , which requires elevation for install.</span></span>

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

### <span data-ttu-id="f9c74-182">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="f9c74-182">-WhatIf</span></span>

<span data-ttu-id="f9c74-183">Zeigt, was geschieht, wenn ausgeführt wird `Update-Module` .</span><span class="sxs-lookup"><span data-stu-id="f9c74-183">Shows what would happen if `Update-Module` runs.</span></span> <span data-ttu-id="f9c74-184">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="f9c74-184">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="f9c74-185">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="f9c74-185">CommonParameters</span></span>

<span data-ttu-id="f9c74-186">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="f9c74-186">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="f9c74-187">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="f9c74-187">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="f9c74-188">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="f9c74-188">INPUTS</span></span>

### <span data-ttu-id="f9c74-189">System.String[]</span><span class="sxs-lookup"><span data-stu-id="f9c74-189">System.String[]</span></span>

### <span data-ttu-id="f9c74-190">System.String</span><span class="sxs-lookup"><span data-stu-id="f9c74-190">System.String</span></span>

### <span data-ttu-id="f9c74-191">System. Management. Automation. PSCredential</span><span class="sxs-lookup"><span data-stu-id="f9c74-191">System.Management.Automation.PSCredential</span></span>

### <span data-ttu-id="f9c74-192">System.Uri</span><span class="sxs-lookup"><span data-stu-id="f9c74-192">System.Uri</span></span>

## <span data-ttu-id="f9c74-193">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="f9c74-193">OUTPUTS</span></span>

### <span data-ttu-id="f9c74-194">System.Object</span><span class="sxs-lookup"><span data-stu-id="f9c74-194">System.Object</span></span>

## <span data-ttu-id="f9c74-195">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="f9c74-195">NOTES</span></span>

<span data-ttu-id="f9c74-196">Für PowerShell 5,1 oder niedriger ist der Standardbereich in einer Sitzung mit erhöhten Rechten **ALLUSERS** und in einer Sitzung ohne erhöhte Rechte **CurrentUser** .</span><span class="sxs-lookup"><span data-stu-id="f9c74-196">For PowerShell 5.1 or below, the default scope in an elevated session is **AllUsers** , and in a non-elevated session, **CurrentUser** .</span></span> <span data-ttu-id="f9c74-197">Modulupdates für **ALLUSERS** , `$env:ProgramFiles\PowerShell\Modules` , benötigen erhöhte Berechtigungen.</span><span class="sxs-lookup"><span data-stu-id="f9c74-197">Module updates for **AllUsers** , `$env:ProgramFiles\PowerShell\Modules`, need elevated permissions.</span></span> <span data-ttu-id="f9c74-198">Modulupdates für **CurrentUser** , `$home\Documents\PowerShell\Modules` , benötigen keine erhöhten Berechtigungen.</span><span class="sxs-lookup"><span data-stu-id="f9c74-198">Module updates for **CurrentUser** , `$home\Documents\PowerShell\Modules`, don't need elevated permissions.</span></span>

<span data-ttu-id="f9c74-199">`Update-Module` wird in PowerShell 3,0 oder höheren Versionen von PowerShell unter Windows 7 oder Windows 2008 R2 und höheren Versionen von Windows ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="f9c74-199">`Update-Module` runs on PowerShell 3.0 or later releases of PowerShell, on Windows 7 or Windows 2008 R2 and later releases of Windows.</span></span>

<span data-ttu-id="f9c74-200">Wenn das Modul, das Sie mit dem **Name** -Parameter angeben, nicht mithilfe von installiert `Install-Module` wurde, tritt ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="f9c74-200">If the module that you specify with the **Name** parameter wasn't installed by using `Install-Module`, an error occurs.</span></span>

<span data-ttu-id="f9c74-201">Sie können nur `Update-Module` Module ausführen, die Sie aus dem Onlinekatalog installiert haben, indem Sie Ausführen `Install-Module` .</span><span class="sxs-lookup"><span data-stu-id="f9c74-201">You can only run `Update-Module` on modules that you installed from the online gallery by running `Install-Module`.</span></span>

<span data-ttu-id="f9c74-202">Wenn `Update-Module` versucht, Binärdateien zu aktualisieren, die verwendet werden, `Update-Module` gibt einen Fehler zurück, der die Problem Prozesse identifiziert.</span><span class="sxs-lookup"><span data-stu-id="f9c74-202">If `Update-Module` attempts to update binaries that are in use, `Update-Module` returns an error that identifies the problem processes.</span></span> <span data-ttu-id="f9c74-203">Der Benutzer wird informiert, dass er `Update-Module` nach dem Beenden der Prozesse wiederholt werden soll.</span><span class="sxs-lookup"><span data-stu-id="f9c74-203">The user is informed to retry `Update-Module` after the processes are stopped.</span></span>

## <span data-ttu-id="f9c74-204">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="f9c74-204">RELATED LINKS</span></span>

[<span data-ttu-id="f9c74-205">Find-Module</span><span class="sxs-lookup"><span data-stu-id="f9c74-205">Find-Module</span></span>](Find-Module.md)

[<span data-ttu-id="f9c74-206">Get-InstalledModule</span><span class="sxs-lookup"><span data-stu-id="f9c74-206">Get-InstalledModule</span></span>](Get-InstalledModule.md)

[<span data-ttu-id="f9c74-207">Install-Module</span><span class="sxs-lookup"><span data-stu-id="f9c74-207">Install-Module</span></span>](Install-Module.md)

[<span data-ttu-id="f9c74-208">Publish-Module</span><span class="sxs-lookup"><span data-stu-id="f9c74-208">Publish-Module</span></span>](Publish-Module.md)

[<span data-ttu-id="f9c74-209">Uninstall-Module</span><span class="sxs-lookup"><span data-stu-id="f9c74-209">Uninstall-Module</span></span>](Uninstall-Module.md)
