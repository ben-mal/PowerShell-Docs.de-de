---
external help file: PSModule-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PowerShellGet
ms.date: 08/03/2020
online version: https://docs.microsoft.com/powershell/module/powershellget/install-module?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Install-Module
ms.openlocfilehash: e2e4dc34fb84a54fb92cc4c809c84d67beafe576
ms.sourcegitcommit: 4fc8cf397cb725ae973751d1d5d542f34f0db2d7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/03/2020
ms.locfileid: "93219092"
---
# <span data-ttu-id="e4755-103">Install-Module</span><span class="sxs-lookup"><span data-stu-id="e4755-103">Install-Module</span></span>

## <span data-ttu-id="e4755-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="e4755-104">SYNOPSIS</span></span>
<span data-ttu-id="e4755-105">Lädt ein oder mehrere Module aus einem Repository herunter und installiert Sie auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="e4755-105">Downloads one or more modules from a repository, and installs them on the local computer.</span></span>

## <span data-ttu-id="e4755-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e4755-106">SYNTAX</span></span>

### <span data-ttu-id="e4755-107">Nameparameterset (Standard)</span><span class="sxs-lookup"><span data-stu-id="e4755-107">NameParameterSet (Default)</span></span>

```
Install-Module [-Name] <String[]> [-MinimumVersion <String>] [-MaximumVersion <String>]
 [-RequiredVersion <String>] [-Repository <String[]>] [-Credential <PSCredential>] [-Scope <String>]
 [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-AllowClobber] [-SkipPublisherCheck] [-Force]
 [-AllowPrerelease] [-AcceptLicense] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="e4755-108">InputObject</span><span class="sxs-lookup"><span data-stu-id="e4755-108">InputObject</span></span>

```
Install-Module [-InputObject] <PSObject[]> [-Credential <PSCredential>] [-Scope <String>]
 [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-AllowClobber] [-SkipPublisherCheck] [-Force]
 [-AcceptLicense] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="e4755-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e4755-109">DESCRIPTION</span></span>

<span data-ttu-id="e4755-110">Das `Install-Module` -Cmdlet ruft ein oder mehrere Module ab, die die angegebenen Kriterien aus einem Online-Repository erfüllen.</span><span class="sxs-lookup"><span data-stu-id="e4755-110">The `Install-Module` cmdlet gets one or more modules that meet specified criteria from an online repository.</span></span> <span data-ttu-id="e4755-111">Mit dem-Cmdlet wird überprüft, ob die Suchergebnisse gültige Module sind, und die Modul Ordner werden an den Installations Speicherort kopiert.</span><span class="sxs-lookup"><span data-stu-id="e4755-111">The cmdlet verifies that search results are valid modules and copies the module folders to the installation location.</span></span> <span data-ttu-id="e4755-112">Installierte Module werden nach der Installation nicht automatisch importiert.</span><span class="sxs-lookup"><span data-stu-id="e4755-112">Installed modules are not automatically imported after installation.</span></span>
<span data-ttu-id="e4755-113">Sie können filtern, welches Modul basierend auf den minimalen, maximalen und exakten Versionen der angegebenen Module installiert wird.</span><span class="sxs-lookup"><span data-stu-id="e4755-113">You can filter which module is installed based on the minimum, maximum, and exact versions of specified modules.</span></span>

<span data-ttu-id="e4755-114">Wenn das Modul, das installiert wird, den gleichen Namen oder die gleiche Version aufweist oder Befehle in einem vorhandenen Modul enthält, werden Warnmeldungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e4755-114">If the module being installed has the same name or version, or contains commands in an existing module, warning messages are displayed.</span></span> <span data-ttu-id="e4755-115">Nachdem Sie bestätigt haben, dass Sie das Modul installieren und die Warnungen außer Kraft setzen möchten, verwenden Sie den `-Force` -Parameter und den- `-AllowClobber` Parameter.</span><span class="sxs-lookup"><span data-stu-id="e4755-115">After you confirm that you want to install the module and override the warnings, use the `-Force` and `-AllowClobber` parameters.</span></span> <span data-ttu-id="e4755-116">Abhängig von Ihren Repository-Einstellungen müssen Sie möglicherweise eine Eingabeaufforderung beantworten, damit die Modul Installation fortgesetzt werden kann.</span><span class="sxs-lookup"><span data-stu-id="e4755-116">Dependent upon your repository settings, you might need to answer a prompt for the module installation to continue.</span></span>

<span data-ttu-id="e4755-117">In diesen Beispielen wird die [PowerShell-Katalog](https://www.powershellgallery.com/) als einziges registriertes Repository verwendet.</span><span class="sxs-lookup"><span data-stu-id="e4755-117">These examples use the [PowerShell Gallery](https://www.powershellgallery.com/) as the only registered repository.</span></span> <span data-ttu-id="e4755-118">`Get-PSRepository` zeigt die registrierten Depots an.</span><span class="sxs-lookup"><span data-stu-id="e4755-118">`Get-PSRepository` displays the registered repositories.</span></span> <span data-ttu-id="e4755-119">Wenn Sie über mehrere registrierte Repository verfügen, verwenden Sie den `-Repository` -Parameter, um den Namen des Repository anzugeben.</span><span class="sxs-lookup"><span data-stu-id="e4755-119">If you have multiple registered repositories, use the `-Repository` parameter to specify the repository's name.</span></span>

## <span data-ttu-id="e4755-120">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="e4755-120">EXAMPLES</span></span>

### <span data-ttu-id="e4755-121">Beispiel 1: Suchen und Installieren eines Moduls</span><span class="sxs-lookup"><span data-stu-id="e4755-121">Example 1: Find and install a module</span></span>

<span data-ttu-id="e4755-122">In diesem Beispiel wird ein Modul im Repository gefunden und das Modul installiert.</span><span class="sxs-lookup"><span data-stu-id="e4755-122">This example finds a module in the repository and installs the module.</span></span>

```powershell
Find-Module -Name PowerShellGet | Install-Module
```

<span data-ttu-id="e4755-123">Der `Find-Module` verwendet den **Name** -Parameter, um das **PowerShellGet** -Modul anzugeben.</span><span class="sxs-lookup"><span data-stu-id="e4755-123">The `Find-Module` uses the **Name** parameter to specify the **PowerShellGet** module.</span></span> <span data-ttu-id="e4755-124">Standardmäßig wird die neueste Version des Moduls aus dem Repository heruntergeladen.</span><span class="sxs-lookup"><span data-stu-id="e4755-124">By default, the newest version of the module is downloaded from the repository.</span></span> <span data-ttu-id="e4755-125">Das Objekt wird über die Pipeline an das `Install-Module` Cmdlet gesendet.</span><span class="sxs-lookup"><span data-stu-id="e4755-125">The object is sent down the pipeline to the `Install-Module` cmdlet.</span></span> <span data-ttu-id="e4755-126">`Install-Module` installiert das Modul für alle Benutzer in `$env:ProgramFiles\PowerShell\Modules` .</span><span class="sxs-lookup"><span data-stu-id="e4755-126">`Install-Module` installs the module for all users in `$env:ProgramFiles\PowerShell\Modules`.</span></span>

### <span data-ttu-id="e4755-127">Beispiel 2: Installieren eines Moduls nach Name</span><span class="sxs-lookup"><span data-stu-id="e4755-127">Example 2: Install a module by name</span></span>

<span data-ttu-id="e4755-128">In diesem Beispiel ist die neueste Version des **PowerShellGet** -Moduls installiert.</span><span class="sxs-lookup"><span data-stu-id="e4755-128">In this example, the newest version of the **PowerShellGet** module is installed.</span></span>

```powershell
Install-Module -Name PowerShellGet
```

<span data-ttu-id="e4755-129">Der `Install-Module` verwendet den **Name** -Parameter, um das **PowerShellGet** -Modul anzugeben.</span><span class="sxs-lookup"><span data-stu-id="e4755-129">The `Install-Module` uses the **Name** parameter to specify the **PowerShellGet** module.</span></span> <span data-ttu-id="e4755-130">Standardmäßig wird die neueste Version des Moduls aus dem Repository heruntergeladen und installiert.</span><span class="sxs-lookup"><span data-stu-id="e4755-130">By default, the newest version of the module is downloaded from the repository and installed.</span></span>

### <span data-ttu-id="e4755-131">Beispiel 3: Installieren eines Moduls mit der Mindestversion</span><span class="sxs-lookup"><span data-stu-id="e4755-131">Example 3: Install a module using its minimum version</span></span>

<span data-ttu-id="e4755-132">In diesem Beispiel ist die Mindestversion des **PowerShellGet** -Moduls installiert.</span><span class="sxs-lookup"><span data-stu-id="e4755-132">In this example, the minimum version of the **PowerShellGet** module is installed.</span></span> <span data-ttu-id="e4755-133">Der **MinimumVersion** -Parameter gibt die niedrigste Version des Moduls an, das installiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="e4755-133">The **MinimumVersion** parameter specifies the lowest version of the module that should be installed.</span></span> <span data-ttu-id="e4755-134">Wenn eine neuere Version des Moduls verfügbar ist, wird diese Version heruntergeladen und für alle Benutzer installiert.</span><span class="sxs-lookup"><span data-stu-id="e4755-134">If a newer version of the module is available, that version is downloaded and installed for all users.</span></span>

```powershell
Install-Module -Name PowerShellGet -MinimumVersion 2.0.1
```

<span data-ttu-id="e4755-135">Der `Install-Module` verwendet den **Name** -Parameter, um das **PowerShellGet** -Modul anzugeben.</span><span class="sxs-lookup"><span data-stu-id="e4755-135">The `Install-Module` uses the **Name** parameter to specify the **PowerShellGet** module.</span></span> <span data-ttu-id="e4755-136">Der **MinimumVersion** -Parameter gibt an, dass Version **2.0.1** aus dem Repository heruntergeladen und installiert wird.</span><span class="sxs-lookup"><span data-stu-id="e4755-136">The **MinimumVersion** parameter specifies that version **2.0.1** is downloaded from the repository and installed.</span></span> <span data-ttu-id="e4755-137">Da Version **2.0.4** verfügbar ist, wird diese Version heruntergeladen und für alle Benutzer installiert.</span><span class="sxs-lookup"><span data-stu-id="e4755-137">Because version **2.0.4** is available, that version is downloaded and installed for all users.</span></span>

### <span data-ttu-id="e4755-138">Beispiel 4: Installieren einer bestimmten Version eines Moduls</span><span class="sxs-lookup"><span data-stu-id="e4755-138">Example 4: Install a specific version of a module</span></span>

<span data-ttu-id="e4755-139">In diesem Beispiel wird eine bestimmte Version des **PowerShellGet** -Moduls installiert.</span><span class="sxs-lookup"><span data-stu-id="e4755-139">In this example, a specific version of the **PowerShellGet** module is installed.</span></span>

```powershell
Install-Module -Name PowerShellGet -RequiredVersion 2.0.0
```

<span data-ttu-id="e4755-140">Der `Install-Module` verwendet den **Name** -Parameter, um das **PowerShellGet** -Modul anzugeben.</span><span class="sxs-lookup"><span data-stu-id="e4755-140">The `Install-Module` uses the **Name** parameter to specify the **PowerShellGet** module.</span></span> <span data-ttu-id="e4755-141">Der Parameter "Requirements **dversion** " gibt an, dass Version **2.0.0** heruntergeladen und für alle Benutzer installiert wird.</span><span class="sxs-lookup"><span data-stu-id="e4755-141">The **RequiredVersion** parameter specifies that version **2.0.0** is downloaded and installed for all users.</span></span>

### <span data-ttu-id="e4755-142">Beispiel 5: Installieren eines Moduls nur für den aktuellen Benutzer</span><span class="sxs-lookup"><span data-stu-id="e4755-142">Example 5: Install a module only for the current user</span></span>

<span data-ttu-id="e4755-143">In diesem Beispiel wird die neueste Version eines Moduls heruntergeladen und installiert, nur für den aktuellen Benutzer.</span><span class="sxs-lookup"><span data-stu-id="e4755-143">This example downloads and installs the newest version of a module, only for the current user.</span></span>

```powershell
Install-Module -Name PowerShellGet -Scope CurrentUser
```

<span data-ttu-id="e4755-144">Der `Install-Module` verwendet den **Name** -Parameter, um das **PowerShellGet** -Modul anzugeben.</span><span class="sxs-lookup"><span data-stu-id="e4755-144">The `Install-Module` uses the **Name** parameter to specify the **PowerShellGet** module.</span></span>
<span data-ttu-id="e4755-145">`Install-Module` herunterladen und Installieren der neuesten Version von **PowerShellGet** in das Verzeichnis des aktuellen Benutzers `$home\Documents\PowerShell\Modules` .</span><span class="sxs-lookup"><span data-stu-id="e4755-145">`Install-Module` downloads and installs the newest version of **PowerShellGet** into the current user's directory, `$home\Documents\PowerShell\Modules`.</span></span>

## <span data-ttu-id="e4755-146">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e4755-146">PARAMETERS</span></span>

### <span data-ttu-id="e4755-147">-AcceptLicense</span><span class="sxs-lookup"><span data-stu-id="e4755-147">-AcceptLicense</span></span>

<span data-ttu-id="e4755-148">Bei Modulen, die eine Lizenz erfordern, akzeptiert " **akzeptlicense** " den Lizenzvertrag während der Installation automatisch.</span><span class="sxs-lookup"><span data-stu-id="e4755-148">For modules that require a license, **AcceptLicense** automatically accepts the license agreement during installation.</span></span> <span data-ttu-id="e4755-149">Weitere Informationen finden Sie unter Module, die die [Zustimmung zur Lizenz erfordern](/powershell/scripting/gallery/concepts/module-license-acceptance).</span><span class="sxs-lookup"><span data-stu-id="e4755-149">For more information, see [Modules Requiring License Acceptance](/powershell/scripting/gallery/concepts/module-license-acceptance).</span></span>

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

### <span data-ttu-id="e4755-150">-Allowclobber</span><span class="sxs-lookup"><span data-stu-id="e4755-150">-AllowClobber</span></span>

<span data-ttu-id="e4755-151">Überschreibt Warnmeldungen zu Installations Konflikten in Bezug auf vorhandene Befehle auf einem Computer.</span><span class="sxs-lookup"><span data-stu-id="e4755-151">Overrides warning messages about installation conflicts about existing commands on a computer.</span></span>
<span data-ttu-id="e4755-152">Überschreibt vorhandene Befehle mit demselben Namen wie Befehle, die von einem Modul installiert werden.</span><span class="sxs-lookup"><span data-stu-id="e4755-152">Overwrites existing commands that have the same name as commands being installed by a module.</span></span>
<span data-ttu-id="e4755-153">**Allowclobber** und **Force** können in einem Befehl verwendet werden `Install-Module` .</span><span class="sxs-lookup"><span data-stu-id="e4755-153">**AllowClobber** and **Force** can be used together in an `Install-Module` command.</span></span>

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

### <span data-ttu-id="e4755-154">-Allowprerelease</span><span class="sxs-lookup"><span data-stu-id="e4755-154">-AllowPrerelease</span></span>

<span data-ttu-id="e4755-155">Ermöglicht das Installieren eines als Vorabversion markierten Moduls.</span><span class="sxs-lookup"><span data-stu-id="e4755-155">Allows you to install a module marked as a pre-release.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e4755-156">-Confirm</span><span class="sxs-lookup"><span data-stu-id="e4755-156">-Confirm</span></span>

<span data-ttu-id="e4755-157">Sie werden zur Bestätigung aufgefordert, bevor Sie das `Install-Module` Cmdlet ausführen.</span><span class="sxs-lookup"><span data-stu-id="e4755-157">Prompts you for confirmation before running the `Install-Module` cmdlet.</span></span>

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

### <span data-ttu-id="e4755-158">-Credential</span><span class="sxs-lookup"><span data-stu-id="e4755-158">-Credential</span></span>

<span data-ttu-id="e4755-159">Gibt ein Benutzerkonto an, das über Rechte zum Installieren eines Moduls für einen angegebenen Paketanbieter oder eine angegebene Quelle verfügt.</span><span class="sxs-lookup"><span data-stu-id="e4755-159">Specifies a user account that has rights to install a module for a specified package provider or source.</span></span>

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

### <span data-ttu-id="e4755-160">-Force</span><span class="sxs-lookup"><span data-stu-id="e4755-160">-Force</span></span>

<span data-ttu-id="e4755-161">Installiert ein Modul und überschreibt Warnmeldungen zu Modul Installations Konflikten.</span><span class="sxs-lookup"><span data-stu-id="e4755-161">Installs a module and overrides warning messages about module installation conflicts.</span></span> <span data-ttu-id="e4755-162">Wenn ein Modul mit dem gleichen Namen bereits auf dem Computer vorhanden ist, ermöglicht **Force** die Installation mehrerer Versionen.</span><span class="sxs-lookup"><span data-stu-id="e4755-162">If a module with the same name already exists on the computer, **Force** allows for multiple versions to be installed.</span></span> <span data-ttu-id="e4755-163">Wenn ein Modul mit dem gleichen Namen und der gleichen Version vorhanden ist, wird diese Version von **Force** überschrieben.</span><span class="sxs-lookup"><span data-stu-id="e4755-163">If there is an existing module with the same name and version, **Force** overwrites that version.</span></span> <span data-ttu-id="e4755-164">**Force** und **allowclobber** können in einem Befehl verwendet werden `Install-Module` .</span><span class="sxs-lookup"><span data-stu-id="e4755-164">**Force** and **AllowClobber** can be used together in an `Install-Module` command.</span></span>

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

### <span data-ttu-id="e4755-165">-InputObject</span><span class="sxs-lookup"><span data-stu-id="e4755-165">-InputObject</span></span>

<span data-ttu-id="e4755-166">Wird für Pipeline Eingaben verwendet.</span><span class="sxs-lookup"><span data-stu-id="e4755-166">Used for pipeline input.</span></span>

```yaml
Type: System.Management.Automation.PSObject[]
Parameter Sets: InputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="e4755-167">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="e4755-167">-MaximumVersion</span></span>

<span data-ttu-id="e4755-168">Gibt die maximale Version eines einzelnen Moduls an, das installiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="e4755-168">Specifies the maximum version of a single module to install.</span></span> <span data-ttu-id="e4755-169">Die installierte Version muss kleiner oder gleich **MaximumVersion** sein.</span><span class="sxs-lookup"><span data-stu-id="e4755-169">The version installed must be less than or equal to **MaximumVersion**.</span></span> <span data-ttu-id="e4755-170">Wenn Sie mehrere Module installieren möchten, können Sie **MaximumVersion** nicht verwenden.</span><span class="sxs-lookup"><span data-stu-id="e4755-170">If you want to install multiple modules, you cannot use **MaximumVersion**.</span></span> <span data-ttu-id="e4755-171">**MaximumVersion** und Requirements **dversion** können nicht im selben Befehl verwendet werden `Install-Module` .</span><span class="sxs-lookup"><span data-stu-id="e4755-171">**MaximumVersion** and **RequiredVersion** cannot be used in the same `Install-Module` command.</span></span>

```yaml
Type: System.String
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="e4755-172">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="e4755-172">-MinimumVersion</span></span>

<span data-ttu-id="e4755-173">Gibt die Mindestversion eines einzelnen zu installierenden Moduls an.</span><span class="sxs-lookup"><span data-stu-id="e4755-173">Specifies the minimum version of a single module to install.</span></span> <span data-ttu-id="e4755-174">Die installierte Version muss größer oder gleich **MinimumVersion** sein.</span><span class="sxs-lookup"><span data-stu-id="e4755-174">The version installed must be greater than or equal to **MinimumVersion**.</span></span> <span data-ttu-id="e4755-175">Wenn eine neuere Version des Moduls verfügbar ist, wird die neuere Version installiert.</span><span class="sxs-lookup"><span data-stu-id="e4755-175">If there is a newer version of the module available, the newer version is installed.</span></span> <span data-ttu-id="e4755-176">Wenn Sie mehrere Module installieren möchten, können Sie **MinimumVersion** nicht verwenden.</span><span class="sxs-lookup"><span data-stu-id="e4755-176">If you want to install multiple modules, you cannot use **MinimumVersion**.</span></span>
<span data-ttu-id="e4755-177">**MinimumVersion** und Requirements **dversion** können nicht im selben Befehl verwendet werden `Install-Module` .</span><span class="sxs-lookup"><span data-stu-id="e4755-177">**MinimumVersion** and **RequiredVersion** cannot be used in the same `Install-Module` command.</span></span>

```yaml
Type: System.String
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="e4755-178">-Name</span><span class="sxs-lookup"><span data-stu-id="e4755-178">-Name</span></span>

<span data-ttu-id="e4755-179">Gibt die genauen Namen der Module an, die aus dem Onlinekatalog installiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="e4755-179">Specifies the exact names of modules to install from the online gallery.</span></span> <span data-ttu-id="e4755-180">Eine durch Trennzeichen getrennte Liste von Modulnamen wird akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="e4755-180">A comma-separated list of module names is accepted.</span></span> <span data-ttu-id="e4755-181">Der Modulname muss mit dem Modulnamen im Repository identisch sein.</span><span class="sxs-lookup"><span data-stu-id="e4755-181">The module name must match the module name in the repository.</span></span> <span data-ttu-id="e4755-182">Verwenden `Find-Module` Sie, um eine Liste von Modulnamen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="e4755-182">Use `Find-Module` to get a list of module names.</span></span>

```yaml
Type: System.String[]
Parameter Sets: NameParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="e4755-183">-PassThru</span><span class="sxs-lookup"><span data-stu-id="e4755-183">-PassThru</span></span>

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

### <span data-ttu-id="e4755-184">-Proxy</span><span class="sxs-lookup"><span data-stu-id="e4755-184">-Proxy</span></span>

<span data-ttu-id="e4755-185">Gibt einen Proxy Server für die Anforderung an, anstatt eine direkte Verbindung mit der Internet Ressource herzustellen.</span><span class="sxs-lookup"><span data-stu-id="e4755-185">Specifies a proxy server for the request, rather than connecting directly to the Internet resource.</span></span>

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

### <span data-ttu-id="e4755-186">-Proxy Credential</span><span class="sxs-lookup"><span data-stu-id="e4755-186">-ProxyCredential</span></span>

<span data-ttu-id="e4755-187">Gibt ein Benutzerkonto an, das über die Berechtigung zur Verwendung des Proxyservers verfügt, der durch den **Proxy** -Parameter angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="e4755-187">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="e4755-188">-Repository</span><span class="sxs-lookup"><span data-stu-id="e4755-188">-Repository</span></span>

<span data-ttu-id="e4755-189">Verwenden Sie den **Repository** -Parameter, um anzugeben, welches Repository zum herunterladen und Installieren eines Moduls verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e4755-189">Use the **Repository** parameter to specify which repository is used to download and install a module.</span></span> <span data-ttu-id="e4755-190">Wird verwendet, wenn mehrere Depots registriert sind.</span><span class="sxs-lookup"><span data-stu-id="e4755-190">Used when multiple repositories are registered.</span></span> <span data-ttu-id="e4755-191">Gibt den Namen eines registrierten Repository im Befehl an `Install-Module` .</span><span class="sxs-lookup"><span data-stu-id="e4755-191">Specifies the name of a registered repository in the `Install-Module` command.</span></span> <span data-ttu-id="e4755-192">Verwenden Sie zum Registrieren eines Repository `Register-PSRepository` .</span><span class="sxs-lookup"><span data-stu-id="e4755-192">To register a repository, use `Register-PSRepository`.</span></span>
<span data-ttu-id="e4755-193">Verwenden Sie, um registrierte Depots anzuzeigen `Get-PSRepository` .</span><span class="sxs-lookup"><span data-stu-id="e4755-193">To display registered repositories, use `Get-PSRepository`.</span></span>

```yaml
Type: System.String[]
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e4755-194">-Requirements dversion</span><span class="sxs-lookup"><span data-stu-id="e4755-194">-RequiredVersion</span></span>

<span data-ttu-id="e4755-195">Gibt die exakte Version eines einzelnen Moduls an, das installiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="e4755-195">Specifies the exact version of a single module to install.</span></span> <span data-ttu-id="e4755-196">Wenn keine Entsprechung im Repository für die angegebene Version vorhanden ist, wird ein Fehler angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e4755-196">If there is no match in the repository for the specified version, an error is displayed.</span></span> <span data-ttu-id="e4755-197">Wenn Sie mehrere Module installieren möchten, können Sie "Requirements **dversion** " nicht verwenden.</span><span class="sxs-lookup"><span data-stu-id="e4755-197">If you want to install multiple modules, you cannot use **RequiredVersion**.</span></span> <span data-ttu-id="e4755-198">"Requirements **dversion** " kann nicht im gleichen `Install-Module` Befehl wie " **MinimumVersion** " oder " **MaximumVersion** " verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e4755-198">**RequiredVersion** cannot be used in the same `Install-Module` command as **MinimumVersion** or **MaximumVersion**.</span></span>

```yaml
Type: System.String
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="e4755-199">-Bereich</span><span class="sxs-lookup"><span data-stu-id="e4755-199">-Scope</span></span>

<span data-ttu-id="e4755-200">Gibt den Bereich der Installation des Moduls an.</span><span class="sxs-lookup"><span data-stu-id="e4755-200">Specifies the installation scope of the module.</span></span> <span data-ttu-id="e4755-201">Die zulässigen Werte für diesen Parameter sind **ALLUSERS** und **CurrentUser**.</span><span class="sxs-lookup"><span data-stu-id="e4755-201">The acceptable values for this parameter are **AllUsers** and **CurrentUser**.</span></span>

<span data-ttu-id="e4755-202">Der Bereich " **ALLUSERS** " installiert Module an einem Speicherort, auf den alle Benutzer des Computers zugreifen können:</span><span class="sxs-lookup"><span data-stu-id="e4755-202">The **AllUsers** scope installs modules in a location that is accessible to all users of the computer:</span></span>

`$env:ProgramFiles\PowerShell\Modules`

<span data-ttu-id="e4755-203">**CurrentUser** installiert Module an einem Speicherort, auf den nur der aktuelle Benutzer des Computers zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="e4755-203">The **CurrentUser** installs modules in a location that is accessible only to the current user of the computer.</span></span> <span data-ttu-id="e4755-204">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="e4755-204">For example:</span></span>

`$home\Documents\PowerShell\Modules`

<span data-ttu-id="e4755-205">Wenn kein **Bereich** definiert ist, wird der Standardwert basierend auf der PowerShellGet-Version festgelegt.</span><span class="sxs-lookup"><span data-stu-id="e4755-205">When no **Scope** is defined, the default is set based on the PowerShellGet version.</span></span>

- <span data-ttu-id="e4755-206">In PowerShellGet Version 2.0.0 und höher ist der Standardwert **CurrentUser** , der keine Erhöhung der Rechte für die Installation erfordert.</span><span class="sxs-lookup"><span data-stu-id="e4755-206">In PowerShellGet versions 2.0.0 and above, the default is **CurrentUser** , which does not require elevation for install.</span></span>
- <span data-ttu-id="e4755-207">In PowerShellGet 1. x-Versionen ist der Standardwert " **ALLUSERS** ", für den eine Erhöhung der Installation erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="e4755-207">In PowerShellGet 1.x versions, the default is **AllUsers** , which requires elevation for install.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: CurrentUser, AllUsers

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e4755-208">-Skippublishercheck</span><span class="sxs-lookup"><span data-stu-id="e4755-208">-SkipPublisherCheck</span></span>

<span data-ttu-id="e4755-209">Ermöglicht es Ihnen, eine neuere Version eines Moduls zu installieren, die bereits auf dem Computer vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="e4755-209">Allows you to install a newer version of a module that already exists on your computer.</span></span> <span data-ttu-id="e4755-210">Wenn ein vorhandenes Modul z. b. Digital von einem vertrauenswürdigen Verleger signiert ist, die neue Version jedoch nicht Digital von einem vertrauenswürdigen Herausgeber signiert wurde.</span><span class="sxs-lookup"><span data-stu-id="e4755-210">For example, when an existing module is digitally signed by a trusted publisher but the new version is not digitally signed by a trusted publisher.</span></span>

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

### <span data-ttu-id="e4755-211">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="e4755-211">-WhatIf</span></span>

<span data-ttu-id="e4755-212">Zeigt, was geschieht, wenn ein `Install-Module` Befehl ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="e4755-212">Shows what would happen if an `Install-Module` command was run.</span></span> <span data-ttu-id="e4755-213">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="e4755-213">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="e4755-214">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="e4755-214">CommonParameters</span></span>

<span data-ttu-id="e4755-215">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="e4755-215">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e4755-216">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="e4755-216">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="e4755-217">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="e4755-217">INPUTS</span></span>

### <span data-ttu-id="e4755-218">PSRepositoryItemInfo</span><span class="sxs-lookup"><span data-stu-id="e4755-218">PSRepositoryItemInfo</span></span>

<span data-ttu-id="e4755-219">`Find-Module` erstellt **PSRepositoryItemInfo** -Objekte, die über die Pipeline an gesendet werden können `Install-Module` .</span><span class="sxs-lookup"><span data-stu-id="e4755-219">`Find-Module` creates **PSRepositoryItemInfo** objects that can be sent down the pipeline to `Install-Module`.</span></span>

### <span data-ttu-id="e4755-220">System.String[]</span><span class="sxs-lookup"><span data-stu-id="e4755-220">System.String[]</span></span>

### <span data-ttu-id="e4755-221">System. Management. Automation. psobject []</span><span class="sxs-lookup"><span data-stu-id="e4755-221">System.Management.Automation.PSObject[]</span></span>

### <span data-ttu-id="e4755-222">System.String</span><span class="sxs-lookup"><span data-stu-id="e4755-222">System.String</span></span>

### <span data-ttu-id="e4755-223">System. Management. Automation. PSCredential</span><span class="sxs-lookup"><span data-stu-id="e4755-223">System.Management.Automation.PSCredential</span></span>

### <span data-ttu-id="e4755-224">System.Uri</span><span class="sxs-lookup"><span data-stu-id="e4755-224">System.Uri</span></span>

## <span data-ttu-id="e4755-225">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="e4755-225">OUTPUTS</span></span>

### <span data-ttu-id="e4755-226">Microsoft. PowerShell. Commands. PSRepositoryItemInfo</span><span class="sxs-lookup"><span data-stu-id="e4755-226">Microsoft.PowerShell.Commands.PSRepositoryItemInfo</span></span>

<span data-ttu-id="e4755-227">Wenn Sie den **passthru** -Parameter verwenden, gibt `Install-Module` ein **PSRepositoryItemInfo** -Objekt für das Modul aus.</span><span class="sxs-lookup"><span data-stu-id="e4755-227">When using the **PassThru** parameter, `Install-Module` outputs a **PSRepositoryItemInfo** object for the module.</span></span> <span data-ttu-id="e4755-228">Dies sind die gleichen Informationen, die Sie vom `Find-Module` Cmdlet erhalten.</span><span class="sxs-lookup"><span data-stu-id="e4755-228">This is the same information that you get from the `Find-Module` cmdlet.</span></span>

## <span data-ttu-id="e4755-229">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="e4755-229">NOTES</span></span>

<span data-ttu-id="e4755-230">`Install-Module` wird in PowerShell 5,0 oder höheren Versionen unter Windows 7 oder Windows 2008 R2 und neueren Versionen von Windows ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="e4755-230">`Install-Module` runs on PowerShell 5.0 or later releases, on Windows 7 or Windows 2008 R2 and later releases of Windows.</span></span>

<span data-ttu-id="e4755-231">Als bewährte Sicherheitsmaßnahme sollten Sie den Code eines Moduls auswerten, bevor Sie zum ersten Mal Cmdlets oder Funktionen ausführen.</span><span class="sxs-lookup"><span data-stu-id="e4755-231">As a security best practice, evaluate a module's code before running any cmdlets or functions for the first time.</span></span> <span data-ttu-id="e4755-232">Um das Ausführen von Modulen zu verhindern, die bösartigen Code enthalten, werden installierte Module nach der Installation nicht automatisch importiert.</span><span class="sxs-lookup"><span data-stu-id="e4755-232">To prevent running modules that contain malicious code, installed modules are not automatically imported after installation.</span></span>

<span data-ttu-id="e4755-233">Wenn der durch den **Name** -Parameter angegebene Modulname im Repository nicht vorhanden ist, `Install-Module` gibt einen Fehler zurück.</span><span class="sxs-lookup"><span data-stu-id="e4755-233">If the module name specified by the **Name** parameter does not exist in the repository, `Install-Module` returns an error.</span></span>

<span data-ttu-id="e4755-234">Verwenden Sie den **Name** -Parameter, und geben Sie ein durch Trennzeichen getrenntes Array von Modulnamen an, um mehrere Module zu installieren.</span><span class="sxs-lookup"><span data-stu-id="e4755-234">To install multiple modules, use the **Name** parameter and specify a comma-separated array of module names.</span></span> <span data-ttu-id="e4755-235">Wenn Sie mehrere Modulnamen angeben, können Sie **MinimumVersion** , **MaximumVersion** oder Requirements **dversion** nicht verwenden.</span><span class="sxs-lookup"><span data-stu-id="e4755-235">If you specify multiple module names, you cannot use **MinimumVersion** , **MaximumVersion** , or **RequiredVersion**.</span></span> <span data-ttu-id="e4755-236">`Find-Module` erstellt **PSRepositoryItemInfo** -Objekte, die über die Pipeline an gesendet werden können `Install-Module` .</span><span class="sxs-lookup"><span data-stu-id="e4755-236">`Find-Module` creates **PSRepositoryItemInfo** objects that can be sent down the pipeline to `Install-Module`.</span></span> <span data-ttu-id="e4755-237">Die Pipeline ist eine andere Möglichkeit, mehrere Module anzugeben, die mit einem einzigen Befehl installiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="e4755-237">The pipeline is another way to specify multiple modules to install in a single command.</span></span>

<span data-ttu-id="e4755-238">Standardmäßig werden Module für den Bereich von **ALLUSERS** in installiert `$env:ProgramFiles\PowerShell\Modules` .</span><span class="sxs-lookup"><span data-stu-id="e4755-238">By default, modules for the scope of **AllUsers** are installed in `$env:ProgramFiles\PowerShell\Modules`.</span></span> <span data-ttu-id="e4755-239">Der Standardwert verhindert Verwechslungen bei der Installation von PowerShell DSC-Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="e4755-239">The default prevents confusion when you install PowerShell Desired State Configuration (DSC) resources.</span></span>

<span data-ttu-id="e4755-240">Bei einer Modul Installation tritt ein Fehler auf, und Sie kann nicht importiert werden, wenn Sie im Ordner nicht über einen-,-oder-Wert `.psm1` `.psd1` `.dll` mit demselben Namen verfügt.</span><span class="sxs-lookup"><span data-stu-id="e4755-240">A module installation fails and cannot be imported if it does not have a `.psm1`, `.psd1`, or `.dll` of the same name within the folder.</span></span> <span data-ttu-id="e4755-241">Verwenden Sie den **Force** -Parameter, um das Modul zu installieren.</span><span class="sxs-lookup"><span data-stu-id="e4755-241">Use the **Force** parameter to install the module.</span></span>

<span data-ttu-id="e4755-242">Wenn die Version eines vorhandenen Moduls mit dem im **Name** -Parameter angegebenen Namen übereinstimmt und der **MinimumVersion** -Parameter oder der Requirements **dversion** -Parameter nicht verwendet wird, wird der Hintergrund `Install-Module` fortgesetzt, das Modul wird jedoch nicht installiert.</span><span class="sxs-lookup"><span data-stu-id="e4755-242">If an existing module's version matches the name specified by the **Name** parameter, and the **MinimumVersion** or **RequiredVersion** parameter are not used, `Install-Module` silently continues but does not install the module.</span></span>

<span data-ttu-id="e4755-243">Wenn die Version eines vorhandenen Moduls größer als der Wert des **MinimumVersion** -Parameters ist oder gleich dem Wert des Parameters "Requirements **dversion** " ist, wird `Install-Module` im Hintergrund fortgesetzt, das Modul wird jedoch nicht installiert.</span><span class="sxs-lookup"><span data-stu-id="e4755-243">If an existing module's version is greater than the value of the **MinimumVersion** parameter, or equal to the value of the **RequiredVersion** parameter, `Install-Module` silently continues but does not install the module.</span></span>

<span data-ttu-id="e4755-244">Wenn das vorhandene Modul nicht mit den Werten in den Parametern **Minimum Version** oder Requirements **dversion** identisch ist, tritt im Befehl ein Fehler auf `Install-Module` .</span><span class="sxs-lookup"><span data-stu-id="e4755-244">If the existing module does not match the values specified by the **MinimumVersion** or **RequiredVersion** parameters, an error occurs in the `Install-Module` command.</span></span> <span data-ttu-id="e4755-245">Wenn beispielsweise die Version des vorhandenen installierten Moduls niedriger ist als der **MinimumVersion** -Wert oder nicht gleich dem Wert "Requirements- **Version** ".</span><span class="sxs-lookup"><span data-stu-id="e4755-245">For example, if the version of the existing installed module is lower than the **MinimumVersion** value or not equal to the **RequiredVersion** value.</span></span>

<span data-ttu-id="e4755-246">Bei einer Modul Installation werden auch alle abhängigen Module installiert, die vom Modul Herausgeber benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="e4755-246">A module installation will also install any dependent modules specified as required by the module publisher.</span></span>
<span data-ttu-id="e4755-247">Der Verleger gibt die erforderlichen Module und deren Versionen im Modul Manifest an.</span><span class="sxs-lookup"><span data-stu-id="e4755-247">The publisher will specify the required modules and their versions in the module manifest.</span></span>

## <span data-ttu-id="e4755-248">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="e4755-248">RELATED LINKS</span></span>

[<span data-ttu-id="e4755-249">Find-Module</span><span class="sxs-lookup"><span data-stu-id="e4755-249">Find-Module</span></span>](Find-Module.md)

[<span data-ttu-id="e4755-250">Get-PSRepository</span><span class="sxs-lookup"><span data-stu-id="e4755-250">Get-PSRepository</span></span>](Get-PSRepository.md)

[<span data-ttu-id="e4755-251">Import-Module</span><span class="sxs-lookup"><span data-stu-id="e4755-251">Import-Module</span></span>](../Microsoft.PowerShell.Core/Import-Module.md)

[<span data-ttu-id="e4755-252">Publish-Module</span><span class="sxs-lookup"><span data-stu-id="e4755-252">Publish-Module</span></span>](Publish-Module.md)

[<span data-ttu-id="e4755-253">Register-PSRepository</span><span class="sxs-lookup"><span data-stu-id="e4755-253">Register-PSRepository</span></span>](Register-PSRepository.md)

[<span data-ttu-id="e4755-254">Uninstall-Module</span><span class="sxs-lookup"><span data-stu-id="e4755-254">Uninstall-Module</span></span>](Uninstall-Module.md)

[<span data-ttu-id="e4755-255">Update-Module</span><span class="sxs-lookup"><span data-stu-id="e4755-255">Update-Module</span></span>](Update-Module.md)

[<span data-ttu-id="e4755-256">about_Module</span><span class="sxs-lookup"><span data-stu-id="e4755-256">about_Module</span></span>](../Microsoft.PowerShell.Core/About/about_Modules.md)
