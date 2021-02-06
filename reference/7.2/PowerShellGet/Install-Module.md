---
external help file: PSModule-help.xml
Locale: en-US
Module Name: PowerShellGet
ms.date: 08/03/2020
online version: https://docs.microsoft.com/powershell/module/powershellget/install-module?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Install-Module
ms.openlocfilehash: f4fcf349c439baf4813c37af4bf56c26a46c7877
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/19/2020
ms.locfileid: "99601726"
---
# <span data-ttu-id="bb042-102">Install-Module</span><span class="sxs-lookup"><span data-stu-id="bb042-102">Install-Module</span></span>

## <span data-ttu-id="bb042-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="bb042-103">SYNOPSIS</span></span>
<span data-ttu-id="bb042-104">Lädt ein oder mehrere Module aus einem Repository herunter und installiert Sie auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="bb042-104">Downloads one or more modules from a repository, and installs them on the local computer.</span></span>

## <span data-ttu-id="bb042-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="bb042-105">SYNTAX</span></span>

### <span data-ttu-id="bb042-106">Nameparameterset (Standard)</span><span class="sxs-lookup"><span data-stu-id="bb042-106">NameParameterSet (Default)</span></span>

```
Install-Module [-Name] <String[]> [-MinimumVersion <String>] [-MaximumVersion <String>]
 [-RequiredVersion <String>] [-Repository <String[]>] [-Credential <PSCredential>] [-Scope <String>]
 [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-AllowClobber] [-SkipPublisherCheck] [-Force]
 [-AllowPrerelease] [-AcceptLicense] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="bb042-107">InputObject</span><span class="sxs-lookup"><span data-stu-id="bb042-107">InputObject</span></span>

```
Install-Module [-InputObject] <PSObject[]> [-Credential <PSCredential>] [-Scope <String>]
 [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-AllowClobber] [-SkipPublisherCheck] [-Force]
 [-AcceptLicense] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="bb042-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="bb042-108">DESCRIPTION</span></span>

<span data-ttu-id="bb042-109">Das `Install-Module` -Cmdlet ruft ein oder mehrere Module ab, die die angegebenen Kriterien aus einem Online-Repository erfüllen.</span><span class="sxs-lookup"><span data-stu-id="bb042-109">The `Install-Module` cmdlet gets one or more modules that meet specified criteria from an online repository.</span></span> <span data-ttu-id="bb042-110">Mit dem-Cmdlet wird überprüft, ob die Suchergebnisse gültige Module sind, und die Modul Ordner werden an den Installations Speicherort kopiert.</span><span class="sxs-lookup"><span data-stu-id="bb042-110">The cmdlet verifies that search results are valid modules and copies the module folders to the installation location.</span></span> <span data-ttu-id="bb042-111">Installierte Module werden nach der Installation nicht automatisch importiert.</span><span class="sxs-lookup"><span data-stu-id="bb042-111">Installed modules are not automatically imported after installation.</span></span>
<span data-ttu-id="bb042-112">Sie können filtern, welches Modul basierend auf den minimalen, maximalen und exakten Versionen der angegebenen Module installiert wird.</span><span class="sxs-lookup"><span data-stu-id="bb042-112">You can filter which module is installed based on the minimum, maximum, and exact versions of specified modules.</span></span>

<span data-ttu-id="bb042-113">Wenn das Modul, das installiert wird, den gleichen Namen oder die gleiche Version aufweist oder Befehle in einem vorhandenen Modul enthält, werden Warnmeldungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bb042-113">If the module being installed has the same name or version, or contains commands in an existing module, warning messages are displayed.</span></span> <span data-ttu-id="bb042-114">Nachdem Sie bestätigt haben, dass Sie das Modul installieren und die Warnungen außer Kraft setzen möchten, verwenden Sie den `-Force` -Parameter und den- `-AllowClobber` Parameter.</span><span class="sxs-lookup"><span data-stu-id="bb042-114">After you confirm that you want to install the module and override the warnings, use the `-Force` and `-AllowClobber` parameters.</span></span> <span data-ttu-id="bb042-115">Abhängig von Ihren Repository-Einstellungen müssen Sie möglicherweise eine Eingabeaufforderung beantworten, damit die Modul Installation fortgesetzt werden kann.</span><span class="sxs-lookup"><span data-stu-id="bb042-115">Dependent upon your repository settings, you might need to answer a prompt for the module installation to continue.</span></span>

<span data-ttu-id="bb042-116">In diesen Beispielen wird die [PowerShell-Katalog](https://www.powershellgallery.com/) als einziges registriertes Repository verwendet.</span><span class="sxs-lookup"><span data-stu-id="bb042-116">These examples use the [PowerShell Gallery](https://www.powershellgallery.com/) as the only registered repository.</span></span> <span data-ttu-id="bb042-117">`Get-PSRepository` zeigt die registrierten Depots an.</span><span class="sxs-lookup"><span data-stu-id="bb042-117">`Get-PSRepository` displays the registered repositories.</span></span> <span data-ttu-id="bb042-118">Wenn Sie über mehrere registrierte Repository verfügen, verwenden Sie den `-Repository` -Parameter, um den Namen des Repository anzugeben.</span><span class="sxs-lookup"><span data-stu-id="bb042-118">If you have multiple registered repositories, use the `-Repository` parameter to specify the repository's name.</span></span>

## <span data-ttu-id="bb042-119">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="bb042-119">EXAMPLES</span></span>

### <span data-ttu-id="bb042-120">Beispiel 1: Suchen und Installieren eines Moduls</span><span class="sxs-lookup"><span data-stu-id="bb042-120">Example 1: Find and install a module</span></span>

<span data-ttu-id="bb042-121">In diesem Beispiel wird ein Modul im Repository gefunden und das Modul installiert.</span><span class="sxs-lookup"><span data-stu-id="bb042-121">This example finds a module in the repository and installs the module.</span></span>

```powershell
Find-Module -Name PowerShellGet | Install-Module
```

<span data-ttu-id="bb042-122">Der `Find-Module` verwendet den **Name** -Parameter, um das **PowerShellGet** -Modul anzugeben.</span><span class="sxs-lookup"><span data-stu-id="bb042-122">The `Find-Module` uses the **Name** parameter to specify the **PowerShellGet** module.</span></span> <span data-ttu-id="bb042-123">Standardmäßig wird die neueste Version des Moduls aus dem Repository heruntergeladen.</span><span class="sxs-lookup"><span data-stu-id="bb042-123">By default, the newest version of the module is downloaded from the repository.</span></span> <span data-ttu-id="bb042-124">Das Objekt wird über die Pipeline an das `Install-Module` Cmdlet gesendet.</span><span class="sxs-lookup"><span data-stu-id="bb042-124">The object is sent down the pipeline to the `Install-Module` cmdlet.</span></span> <span data-ttu-id="bb042-125">`Install-Module` installiert das Modul für alle Benutzer in `$env:ProgramFiles\PowerShell\Modules` .</span><span class="sxs-lookup"><span data-stu-id="bb042-125">`Install-Module` installs the module for all users in `$env:ProgramFiles\PowerShell\Modules`.</span></span>

### <span data-ttu-id="bb042-126">Beispiel 2: Installieren eines Moduls nach Name</span><span class="sxs-lookup"><span data-stu-id="bb042-126">Example 2: Install a module by name</span></span>

<span data-ttu-id="bb042-127">In diesem Beispiel ist die neueste Version des **PowerShellGet** -Moduls installiert.</span><span class="sxs-lookup"><span data-stu-id="bb042-127">In this example, the newest version of the **PowerShellGet** module is installed.</span></span>

```powershell
Install-Module -Name PowerShellGet
```

<span data-ttu-id="bb042-128">Der `Install-Module` verwendet den **Name** -Parameter, um das **PowerShellGet** -Modul anzugeben.</span><span class="sxs-lookup"><span data-stu-id="bb042-128">The `Install-Module` uses the **Name** parameter to specify the **PowerShellGet** module.</span></span> <span data-ttu-id="bb042-129">Standardmäßig wird die neueste Version des Moduls aus dem Repository heruntergeladen und installiert.</span><span class="sxs-lookup"><span data-stu-id="bb042-129">By default, the newest version of the module is downloaded from the repository and installed.</span></span>

### <span data-ttu-id="bb042-130">Beispiel 3: Installieren eines Moduls mit der Mindestversion</span><span class="sxs-lookup"><span data-stu-id="bb042-130">Example 3: Install a module using its minimum version</span></span>

<span data-ttu-id="bb042-131">In diesem Beispiel ist die Mindestversion des **PowerShellGet** -Moduls installiert.</span><span class="sxs-lookup"><span data-stu-id="bb042-131">In this example, the minimum version of the **PowerShellGet** module is installed.</span></span> <span data-ttu-id="bb042-132">Der **MinimumVersion** -Parameter gibt die niedrigste Version des Moduls an, das installiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="bb042-132">The **MinimumVersion** parameter specifies the lowest version of the module that should be installed.</span></span> <span data-ttu-id="bb042-133">Wenn eine neuere Version des Moduls verfügbar ist, wird diese Version heruntergeladen und für alle Benutzer installiert.</span><span class="sxs-lookup"><span data-stu-id="bb042-133">If a newer version of the module is available, that version is downloaded and installed for all users.</span></span>

```powershell
Install-Module -Name PowerShellGet -MinimumVersion 2.0.1
```

<span data-ttu-id="bb042-134">Der `Install-Module` verwendet den **Name** -Parameter, um das **PowerShellGet** -Modul anzugeben.</span><span class="sxs-lookup"><span data-stu-id="bb042-134">The `Install-Module` uses the **Name** parameter to specify the **PowerShellGet** module.</span></span> <span data-ttu-id="bb042-135">Der **MinimumVersion** -Parameter gibt an, dass Version **2.0.1** aus dem Repository heruntergeladen und installiert wird.</span><span class="sxs-lookup"><span data-stu-id="bb042-135">The **MinimumVersion** parameter specifies that version **2.0.1** is downloaded from the repository and installed.</span></span> <span data-ttu-id="bb042-136">Da Version **2.0.4** verfügbar ist, wird diese Version heruntergeladen und für alle Benutzer installiert.</span><span class="sxs-lookup"><span data-stu-id="bb042-136">Because version **2.0.4** is available, that version is downloaded and installed for all users.</span></span>

### <span data-ttu-id="bb042-137">Beispiel 4: Installieren einer bestimmten Version eines Moduls</span><span class="sxs-lookup"><span data-stu-id="bb042-137">Example 4: Install a specific version of a module</span></span>

<span data-ttu-id="bb042-138">In diesem Beispiel wird eine bestimmte Version des **PowerShellGet** -Moduls installiert.</span><span class="sxs-lookup"><span data-stu-id="bb042-138">In this example, a specific version of the **PowerShellGet** module is installed.</span></span>

```powershell
Install-Module -Name PowerShellGet -RequiredVersion 2.0.0
```

<span data-ttu-id="bb042-139">Der `Install-Module` verwendet den **Name** -Parameter, um das **PowerShellGet** -Modul anzugeben.</span><span class="sxs-lookup"><span data-stu-id="bb042-139">The `Install-Module` uses the **Name** parameter to specify the **PowerShellGet** module.</span></span> <span data-ttu-id="bb042-140">Der Parameter "Requirements **dversion** " gibt an, dass Version **2.0.0** heruntergeladen und für alle Benutzer installiert wird.</span><span class="sxs-lookup"><span data-stu-id="bb042-140">The **RequiredVersion** parameter specifies that version **2.0.0** is downloaded and installed for all users.</span></span>

### <span data-ttu-id="bb042-141">Beispiel 5: Installieren eines Moduls nur für den aktuellen Benutzer</span><span class="sxs-lookup"><span data-stu-id="bb042-141">Example 5: Install a module only for the current user</span></span>

<span data-ttu-id="bb042-142">In diesem Beispiel wird die neueste Version eines Moduls heruntergeladen und installiert, nur für den aktuellen Benutzer.</span><span class="sxs-lookup"><span data-stu-id="bb042-142">This example downloads and installs the newest version of a module, only for the current user.</span></span>

```powershell
Install-Module -Name PowerShellGet -Scope CurrentUser
```

<span data-ttu-id="bb042-143">Der `Install-Module` verwendet den **Name** -Parameter, um das **PowerShellGet** -Modul anzugeben.</span><span class="sxs-lookup"><span data-stu-id="bb042-143">The `Install-Module` uses the **Name** parameter to specify the **PowerShellGet** module.</span></span>
<span data-ttu-id="bb042-144">`Install-Module` herunterladen und Installieren der neuesten Version von **PowerShellGet** in das Verzeichnis des aktuellen Benutzers `$home\Documents\PowerShell\Modules` .</span><span class="sxs-lookup"><span data-stu-id="bb042-144">`Install-Module` downloads and installs the newest version of **PowerShellGet** into the current user's directory, `$home\Documents\PowerShell\Modules`.</span></span>

## <span data-ttu-id="bb042-145">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="bb042-145">PARAMETERS</span></span>

### <span data-ttu-id="bb042-146">-AcceptLicense</span><span class="sxs-lookup"><span data-stu-id="bb042-146">-AcceptLicense</span></span>

<span data-ttu-id="bb042-147">Bei Modulen, die eine Lizenz erfordern, akzeptiert " **akzeptlicense** " den Lizenzvertrag während der Installation automatisch.</span><span class="sxs-lookup"><span data-stu-id="bb042-147">For modules that require a license, **AcceptLicense** automatically accepts the license agreement during installation.</span></span> <span data-ttu-id="bb042-148">Weitere Informationen finden Sie unter Module, die die [Zustimmung zur Lizenz erfordern](/powershell/scripting/gallery/concepts/module-license-acceptance).</span><span class="sxs-lookup"><span data-stu-id="bb042-148">For more information, see [Modules Requiring License Acceptance](/powershell/scripting/gallery/concepts/module-license-acceptance).</span></span>

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

### <span data-ttu-id="bb042-149">-Allowclobber</span><span class="sxs-lookup"><span data-stu-id="bb042-149">-AllowClobber</span></span>

<span data-ttu-id="bb042-150">Überschreibt Warnmeldungen zu Installations Konflikten in Bezug auf vorhandene Befehle auf einem Computer.</span><span class="sxs-lookup"><span data-stu-id="bb042-150">Overrides warning messages about installation conflicts about existing commands on a computer.</span></span>
<span data-ttu-id="bb042-151">Überschreibt vorhandene Befehle mit demselben Namen wie Befehle, die von einem Modul installiert werden.</span><span class="sxs-lookup"><span data-stu-id="bb042-151">Overwrites existing commands that have the same name as commands being installed by a module.</span></span>
<span data-ttu-id="bb042-152">**Allowclobber** und **Force** können in einem Befehl verwendet werden `Install-Module` .</span><span class="sxs-lookup"><span data-stu-id="bb042-152">**AllowClobber** and **Force** can be used together in an `Install-Module` command.</span></span>

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

### <span data-ttu-id="bb042-153">-Allowprerelease</span><span class="sxs-lookup"><span data-stu-id="bb042-153">-AllowPrerelease</span></span>

<span data-ttu-id="bb042-154">Ermöglicht das Installieren eines als Vorabversion markierten Moduls.</span><span class="sxs-lookup"><span data-stu-id="bb042-154">Allows you to install a module marked as a pre-release.</span></span>

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

### <span data-ttu-id="bb042-155">-Confirm</span><span class="sxs-lookup"><span data-stu-id="bb042-155">-Confirm</span></span>

<span data-ttu-id="bb042-156">Sie werden zur Bestätigung aufgefordert, bevor Sie das `Install-Module` Cmdlet ausführen.</span><span class="sxs-lookup"><span data-stu-id="bb042-156">Prompts you for confirmation before running the `Install-Module` cmdlet.</span></span>

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

### <span data-ttu-id="bb042-157">-Credential</span><span class="sxs-lookup"><span data-stu-id="bb042-157">-Credential</span></span>

<span data-ttu-id="bb042-158">Gibt ein Benutzerkonto an, das über Rechte zum Installieren eines Moduls für einen angegebenen Paketanbieter oder eine angegebene Quelle verfügt.</span><span class="sxs-lookup"><span data-stu-id="bb042-158">Specifies a user account that has rights to install a module for a specified package provider or source.</span></span>

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

### <span data-ttu-id="bb042-159">-Force</span><span class="sxs-lookup"><span data-stu-id="bb042-159">-Force</span></span>

<span data-ttu-id="bb042-160">Installiert ein Modul und überschreibt Warnmeldungen zu Modul Installations Konflikten.</span><span class="sxs-lookup"><span data-stu-id="bb042-160">Installs a module and overrides warning messages about module installation conflicts.</span></span> <span data-ttu-id="bb042-161">Wenn ein Modul mit dem gleichen Namen bereits auf dem Computer vorhanden ist, ermöglicht **Force** die Installation mehrerer Versionen.</span><span class="sxs-lookup"><span data-stu-id="bb042-161">If a module with the same name already exists on the computer, **Force** allows for multiple versions to be installed.</span></span> <span data-ttu-id="bb042-162">Wenn ein Modul mit dem gleichen Namen und der gleichen Version vorhanden ist, wird diese Version von **Force** überschrieben.</span><span class="sxs-lookup"><span data-stu-id="bb042-162">If there is an existing module with the same name and version, **Force** overwrites that version.</span></span> <span data-ttu-id="bb042-163">**Force** und **allowclobber** können in einem Befehl verwendet werden `Install-Module` .</span><span class="sxs-lookup"><span data-stu-id="bb042-163">**Force** and **AllowClobber** can be used together in an `Install-Module` command.</span></span>

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

### <span data-ttu-id="bb042-164">-InputObject</span><span class="sxs-lookup"><span data-stu-id="bb042-164">-InputObject</span></span>

<span data-ttu-id="bb042-165">Wird für Pipeline Eingaben verwendet.</span><span class="sxs-lookup"><span data-stu-id="bb042-165">Used for pipeline input.</span></span>

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

### <span data-ttu-id="bb042-166">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="bb042-166">-MaximumVersion</span></span>

<span data-ttu-id="bb042-167">Gibt die maximale Version eines einzelnen Moduls an, das installiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="bb042-167">Specifies the maximum version of a single module to install.</span></span> <span data-ttu-id="bb042-168">Die installierte Version muss kleiner oder gleich **MaximumVersion** sein.</span><span class="sxs-lookup"><span data-stu-id="bb042-168">The version installed must be less than or equal to **MaximumVersion**.</span></span> <span data-ttu-id="bb042-169">Wenn Sie mehrere Module installieren möchten, können Sie **MaximumVersion** nicht verwenden.</span><span class="sxs-lookup"><span data-stu-id="bb042-169">If you want to install multiple modules, you cannot use **MaximumVersion**.</span></span> <span data-ttu-id="bb042-170">**MaximumVersion** und Requirements **dversion** können nicht im selben Befehl verwendet werden `Install-Module` .</span><span class="sxs-lookup"><span data-stu-id="bb042-170">**MaximumVersion** and **RequiredVersion** cannot be used in the same `Install-Module` command.</span></span>

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

### <span data-ttu-id="bb042-171">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="bb042-171">-MinimumVersion</span></span>

<span data-ttu-id="bb042-172">Gibt die Mindestversion eines einzelnen zu installierenden Moduls an.</span><span class="sxs-lookup"><span data-stu-id="bb042-172">Specifies the minimum version of a single module to install.</span></span> <span data-ttu-id="bb042-173">Die installierte Version muss größer oder gleich **MinimumVersion** sein.</span><span class="sxs-lookup"><span data-stu-id="bb042-173">The version installed must be greater than or equal to **MinimumVersion**.</span></span> <span data-ttu-id="bb042-174">Wenn eine neuere Version des Moduls verfügbar ist, wird die neuere Version installiert.</span><span class="sxs-lookup"><span data-stu-id="bb042-174">If there is a newer version of the module available, the newer version is installed.</span></span> <span data-ttu-id="bb042-175">Wenn Sie mehrere Module installieren möchten, können Sie **MinimumVersion** nicht verwenden.</span><span class="sxs-lookup"><span data-stu-id="bb042-175">If you want to install multiple modules, you cannot use **MinimumVersion**.</span></span>
<span data-ttu-id="bb042-176">**MinimumVersion** und Requirements **dversion** können nicht im selben Befehl verwendet werden `Install-Module` .</span><span class="sxs-lookup"><span data-stu-id="bb042-176">**MinimumVersion** and **RequiredVersion** cannot be used in the same `Install-Module` command.</span></span>

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

### <span data-ttu-id="bb042-177">-Name</span><span class="sxs-lookup"><span data-stu-id="bb042-177">-Name</span></span>

<span data-ttu-id="bb042-178">Gibt die genauen Namen der Module an, die aus dem Onlinekatalog installiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="bb042-178">Specifies the exact names of modules to install from the online gallery.</span></span> <span data-ttu-id="bb042-179">Eine durch Trennzeichen getrennte Liste von Modulnamen wird akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="bb042-179">A comma-separated list of module names is accepted.</span></span> <span data-ttu-id="bb042-180">Der Modulname muss mit dem Modulnamen im Repository identisch sein.</span><span class="sxs-lookup"><span data-stu-id="bb042-180">The module name must match the module name in the repository.</span></span> <span data-ttu-id="bb042-181">Verwenden `Find-Module` Sie, um eine Liste von Modulnamen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="bb042-181">Use `Find-Module` to get a list of module names.</span></span>

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

### <span data-ttu-id="bb042-182">-PassThru</span><span class="sxs-lookup"><span data-stu-id="bb042-182">-PassThru</span></span>

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

### <span data-ttu-id="bb042-183">-Proxy</span><span class="sxs-lookup"><span data-stu-id="bb042-183">-Proxy</span></span>

<span data-ttu-id="bb042-184">Gibt einen Proxy Server für die Anforderung an, anstatt eine direkte Verbindung mit der Internet Ressource herzustellen.</span><span class="sxs-lookup"><span data-stu-id="bb042-184">Specifies a proxy server for the request, rather than connecting directly to the Internet resource.</span></span>

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

### <span data-ttu-id="bb042-185">-Proxy Credential</span><span class="sxs-lookup"><span data-stu-id="bb042-185">-ProxyCredential</span></span>

<span data-ttu-id="bb042-186">Gibt ein Benutzerkonto an, das über die Berechtigung zur Verwendung des Proxyservers verfügt, der durch den **Proxy**-Parameter angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="bb042-186">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="bb042-187">-Repository</span><span class="sxs-lookup"><span data-stu-id="bb042-187">-Repository</span></span>

<span data-ttu-id="bb042-188">Verwenden Sie den **Repository** -Parameter, um anzugeben, welches Repository zum herunterladen und Installieren eines Moduls verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="bb042-188">Use the **Repository** parameter to specify which repository is used to download and install a module.</span></span> <span data-ttu-id="bb042-189">Wird verwendet, wenn mehrere Depots registriert sind.</span><span class="sxs-lookup"><span data-stu-id="bb042-189">Used when multiple repositories are registered.</span></span> <span data-ttu-id="bb042-190">Gibt den Namen eines registrierten Repository im Befehl an `Install-Module` .</span><span class="sxs-lookup"><span data-stu-id="bb042-190">Specifies the name of a registered repository in the `Install-Module` command.</span></span> <span data-ttu-id="bb042-191">Verwenden Sie zum Registrieren eines Repository `Register-PSRepository` .</span><span class="sxs-lookup"><span data-stu-id="bb042-191">To register a repository, use `Register-PSRepository`.</span></span>
<span data-ttu-id="bb042-192">Verwenden Sie, um registrierte Depots anzuzeigen `Get-PSRepository` .</span><span class="sxs-lookup"><span data-stu-id="bb042-192">To display registered repositories, use `Get-PSRepository`.</span></span>

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

### <span data-ttu-id="bb042-193">-Requirements dversion</span><span class="sxs-lookup"><span data-stu-id="bb042-193">-RequiredVersion</span></span>

<span data-ttu-id="bb042-194">Gibt die exakte Version eines einzelnen Moduls an, das installiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="bb042-194">Specifies the exact version of a single module to install.</span></span> <span data-ttu-id="bb042-195">Wenn keine Entsprechung im Repository für die angegebene Version vorhanden ist, wird ein Fehler angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bb042-195">If there is no match in the repository for the specified version, an error is displayed.</span></span> <span data-ttu-id="bb042-196">Wenn Sie mehrere Module installieren möchten, können Sie "Requirements **dversion**" nicht verwenden.</span><span class="sxs-lookup"><span data-stu-id="bb042-196">If you want to install multiple modules, you cannot use **RequiredVersion**.</span></span> <span data-ttu-id="bb042-197">"Requirements **dversion** " kann nicht im gleichen `Install-Module` Befehl wie " **MinimumVersion** " oder " **MaximumVersion**" verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="bb042-197">**RequiredVersion** cannot be used in the same `Install-Module` command as **MinimumVersion** or **MaximumVersion**.</span></span>

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

### <span data-ttu-id="bb042-198">-Bereich</span><span class="sxs-lookup"><span data-stu-id="bb042-198">-Scope</span></span>

<span data-ttu-id="bb042-199">Gibt den Bereich der Installation des Moduls an.</span><span class="sxs-lookup"><span data-stu-id="bb042-199">Specifies the installation scope of the module.</span></span> <span data-ttu-id="bb042-200">Die zulässigen Werte für diesen Parameter sind **ALLUSERS** und **CurrentUser**.</span><span class="sxs-lookup"><span data-stu-id="bb042-200">The acceptable values for this parameter are **AllUsers** and **CurrentUser**.</span></span>

<span data-ttu-id="bb042-201">Der Bereich " **ALLUSERS** " installiert Module an einem Speicherort, auf den alle Benutzer des Computers zugreifen können:</span><span class="sxs-lookup"><span data-stu-id="bb042-201">The **AllUsers** scope installs modules in a location that is accessible to all users of the computer:</span></span>

`$env:ProgramFiles\PowerShell\Modules`

<span data-ttu-id="bb042-202">**CurrentUser** installiert Module an einem Speicherort, auf den nur der aktuelle Benutzer des Computers zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="bb042-202">The **CurrentUser** installs modules in a location that is accessible only to the current user of the computer.</span></span> <span data-ttu-id="bb042-203">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="bb042-203">For example:</span></span>

`$home\Documents\PowerShell\Modules`

<span data-ttu-id="bb042-204">Wenn kein **Bereich** definiert ist, wird der Standardwert basierend auf der PowerShellGet-Version festgelegt.</span><span class="sxs-lookup"><span data-stu-id="bb042-204">When no **Scope** is defined, the default is set based on the PowerShellGet version.</span></span>

- <span data-ttu-id="bb042-205">In PowerShellGet Version 2.0.0 und höher ist der Standardwert **CurrentUser**, der keine Erhöhung der Rechte für die Installation erfordert.</span><span class="sxs-lookup"><span data-stu-id="bb042-205">In PowerShellGet versions 2.0.0 and above, the default is **CurrentUser**, which does not require elevation for install.</span></span>
- <span data-ttu-id="bb042-206">In PowerShellGet 1. x-Versionen ist der Standardwert " **ALLUSERS**", für den eine Erhöhung der Installation erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="bb042-206">In PowerShellGet 1.x versions, the default is **AllUsers**, which requires elevation for install.</span></span>

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

### <span data-ttu-id="bb042-207">-Skippublishercheck</span><span class="sxs-lookup"><span data-stu-id="bb042-207">-SkipPublisherCheck</span></span>

<span data-ttu-id="bb042-208">Ermöglicht es Ihnen, eine neuere Version eines Moduls zu installieren, die bereits auf dem Computer vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="bb042-208">Allows you to install a newer version of a module that already exists on your computer.</span></span> <span data-ttu-id="bb042-209">Wenn ein vorhandenes Modul z. b. Digital von einem vertrauenswürdigen Verleger signiert ist, die neue Version jedoch nicht Digital von einem vertrauenswürdigen Herausgeber signiert wurde.</span><span class="sxs-lookup"><span data-stu-id="bb042-209">For example, when an existing module is digitally signed by a trusted publisher but the new version is not digitally signed by a trusted publisher.</span></span>

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

### <span data-ttu-id="bb042-210">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="bb042-210">-WhatIf</span></span>

<span data-ttu-id="bb042-211">Zeigt, was geschieht, wenn ein `Install-Module` Befehl ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="bb042-211">Shows what would happen if an `Install-Module` command was run.</span></span> <span data-ttu-id="bb042-212">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="bb042-212">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="bb042-213">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="bb042-213">CommonParameters</span></span>

<span data-ttu-id="bb042-214">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="bb042-214">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="bb042-215">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="bb042-215">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="bb042-216">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="bb042-216">INPUTS</span></span>

### <span data-ttu-id="bb042-217">PSRepositoryItemInfo</span><span class="sxs-lookup"><span data-stu-id="bb042-217">PSRepositoryItemInfo</span></span>

<span data-ttu-id="bb042-218">`Find-Module` erstellt **PSRepositoryItemInfo** -Objekte, die über die Pipeline an gesendet werden können `Install-Module` .</span><span class="sxs-lookup"><span data-stu-id="bb042-218">`Find-Module` creates **PSRepositoryItemInfo** objects that can be sent down the pipeline to `Install-Module`.</span></span>

### <span data-ttu-id="bb042-219">System.String[]</span><span class="sxs-lookup"><span data-stu-id="bb042-219">System.String[]</span></span>

### <span data-ttu-id="bb042-220">System. Management. Automation. psobject []</span><span class="sxs-lookup"><span data-stu-id="bb042-220">System.Management.Automation.PSObject[]</span></span>

### <span data-ttu-id="bb042-221">System.String</span><span class="sxs-lookup"><span data-stu-id="bb042-221">System.String</span></span>

### <span data-ttu-id="bb042-222">System. Management. Automation. PSCredential</span><span class="sxs-lookup"><span data-stu-id="bb042-222">System.Management.Automation.PSCredential</span></span>

### <span data-ttu-id="bb042-223">System.Uri</span><span class="sxs-lookup"><span data-stu-id="bb042-223">System.Uri</span></span>

## <span data-ttu-id="bb042-224">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="bb042-224">OUTPUTS</span></span>

### <span data-ttu-id="bb042-225">Microsoft. PowerShell. Commands. PSRepositoryItemInfo</span><span class="sxs-lookup"><span data-stu-id="bb042-225">Microsoft.PowerShell.Commands.PSRepositoryItemInfo</span></span>

<span data-ttu-id="bb042-226">Wenn Sie den **passthru** -Parameter verwenden, gibt `Install-Module` ein **PSRepositoryItemInfo** -Objekt für das Modul aus.</span><span class="sxs-lookup"><span data-stu-id="bb042-226">When using the **PassThru** parameter, `Install-Module` outputs a **PSRepositoryItemInfo** object for the module.</span></span> <span data-ttu-id="bb042-227">Dies sind die gleichen Informationen, die Sie vom `Find-Module` Cmdlet erhalten.</span><span class="sxs-lookup"><span data-stu-id="bb042-227">This is the same information that you get from the `Find-Module` cmdlet.</span></span>

## <span data-ttu-id="bb042-228">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="bb042-228">NOTES</span></span>

<span data-ttu-id="bb042-229">`Install-Module` wird in PowerShell 5,0 oder höheren Versionen unter Windows 7 oder Windows 2008 R2 und neueren Versionen von Windows ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="bb042-229">`Install-Module` runs on PowerShell 5.0 or later releases, on Windows 7 or Windows 2008 R2 and later releases of Windows.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bb042-230">Ab April 2020 unterstützt der PowerShell-Katalog die TLS-Versionen (Transport Layer Security) 1.0 und 1.1 nicht mehr.</span><span class="sxs-lookup"><span data-stu-id="bb042-230">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="bb042-231">Wenn Sie nicht TLS 1.2 oder höher verwenden, erhalten Sie beim Versuch des Zugriffs auf den PowerShell-Katalog eine Fehlermeldung.</span><span class="sxs-lookup"><span data-stu-id="bb042-231">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="bb042-232">Mit dem folgenden Befehl können Sie sicherstellen, dass Sie TLS 1.2 verwenden:</span><span class="sxs-lookup"><span data-stu-id="bb042-232">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="bb042-233">Weitere Informationen finden Sie im PowerShell-Blog in der [Ankündigung](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/).</span><span class="sxs-lookup"><span data-stu-id="bb042-233">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

<span data-ttu-id="bb042-234">Als bewährte Sicherheitsmaßnahme sollten Sie den Code eines Moduls auswerten, bevor Sie zum ersten Mal Cmdlets oder Funktionen ausführen.</span><span class="sxs-lookup"><span data-stu-id="bb042-234">As a security best practice, evaluate a module's code before running any cmdlets or functions for the first time.</span></span> <span data-ttu-id="bb042-235">Um das Ausführen von Modulen zu verhindern, die bösartigen Code enthalten, werden installierte Module nach der Installation nicht automatisch importiert.</span><span class="sxs-lookup"><span data-stu-id="bb042-235">To prevent running modules that contain malicious code, installed modules are not automatically imported after installation.</span></span>

<span data-ttu-id="bb042-236">Wenn der durch den **Name** -Parameter angegebene Modulname im Repository nicht vorhanden ist, `Install-Module` gibt einen Fehler zurück.</span><span class="sxs-lookup"><span data-stu-id="bb042-236">If the module name specified by the **Name** parameter does not exist in the repository, `Install-Module` returns an error.</span></span>

<span data-ttu-id="bb042-237">Verwenden Sie den **Name** -Parameter, und geben Sie ein durch Trennzeichen getrenntes Array von Modulnamen an, um mehrere Module zu installieren.</span><span class="sxs-lookup"><span data-stu-id="bb042-237">To install multiple modules, use the **Name** parameter and specify a comma-separated array of module names.</span></span> <span data-ttu-id="bb042-238">Wenn Sie mehrere Modulnamen angeben, können Sie **MinimumVersion**, **MaximumVersion** oder Requirements **dversion** nicht verwenden.</span><span class="sxs-lookup"><span data-stu-id="bb042-238">If you specify multiple module names, you cannot use **MinimumVersion**, **MaximumVersion**, or **RequiredVersion**.</span></span> <span data-ttu-id="bb042-239">`Find-Module` erstellt **PSRepositoryItemInfo** -Objekte, die über die Pipeline an gesendet werden können `Install-Module` .</span><span class="sxs-lookup"><span data-stu-id="bb042-239">`Find-Module` creates **PSRepositoryItemInfo** objects that can be sent down the pipeline to `Install-Module`.</span></span> <span data-ttu-id="bb042-240">Die Pipeline ist eine andere Möglichkeit, mehrere Module anzugeben, die mit einem einzigen Befehl installiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="bb042-240">The pipeline is another way to specify multiple modules to install in a single command.</span></span>

<span data-ttu-id="bb042-241">Standardmäßig werden Module für den Bereich von **ALLUSERS** in installiert `$env:ProgramFiles\PowerShell\Modules` .</span><span class="sxs-lookup"><span data-stu-id="bb042-241">By default, modules for the scope of **AllUsers** are installed in `$env:ProgramFiles\PowerShell\Modules`.</span></span> <span data-ttu-id="bb042-242">Der Standardwert verhindert Verwechslungen bei der Installation von PowerShell DSC-Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="bb042-242">The default prevents confusion when you install PowerShell Desired State Configuration (DSC) resources.</span></span>

<span data-ttu-id="bb042-243">Bei einer Modul Installation tritt ein Fehler auf, und Sie kann nicht importiert werden, wenn Sie im Ordner nicht über einen-,-oder-Wert `.psm1` `.psd1` `.dll` mit demselben Namen verfügt.</span><span class="sxs-lookup"><span data-stu-id="bb042-243">A module installation fails and cannot be imported if it does not have a `.psm1`, `.psd1`, or `.dll` of the same name within the folder.</span></span> <span data-ttu-id="bb042-244">Verwenden Sie den **Force** -Parameter, um das Modul zu installieren.</span><span class="sxs-lookup"><span data-stu-id="bb042-244">Use the **Force** parameter to install the module.</span></span>

<span data-ttu-id="bb042-245">Wenn die Version eines vorhandenen Moduls mit dem im **Name** -Parameter angegebenen Namen übereinstimmt und der **MinimumVersion** -Parameter oder der Requirements **dversion** -Parameter nicht verwendet wird, wird der Hintergrund `Install-Module` fortgesetzt, das Modul wird jedoch nicht installiert.</span><span class="sxs-lookup"><span data-stu-id="bb042-245">If an existing module's version matches the name specified by the **Name** parameter, and the **MinimumVersion** or **RequiredVersion** parameter are not used, `Install-Module` silently continues but does not install the module.</span></span>

<span data-ttu-id="bb042-246">Wenn die Version eines vorhandenen Moduls größer als der Wert des **MinimumVersion** -Parameters ist oder gleich dem Wert des Parameters "Requirements **dversion** " ist, wird `Install-Module` im Hintergrund fortgesetzt, das Modul wird jedoch nicht installiert.</span><span class="sxs-lookup"><span data-stu-id="bb042-246">If an existing module's version is greater than the value of the **MinimumVersion** parameter, or equal to the value of the **RequiredVersion** parameter, `Install-Module` silently continues but does not install the module.</span></span>

<span data-ttu-id="bb042-247">Wenn das vorhandene Modul nicht mit den Werten in den Parametern **Minimum Version** oder Requirements **dversion** identisch ist, tritt im Befehl ein Fehler auf `Install-Module` .</span><span class="sxs-lookup"><span data-stu-id="bb042-247">If the existing module does not match the values specified by the **MinimumVersion** or **RequiredVersion** parameters, an error occurs in the `Install-Module` command.</span></span> <span data-ttu-id="bb042-248">Wenn beispielsweise die Version des vorhandenen installierten Moduls niedriger ist als der **MinimumVersion** -Wert oder nicht gleich dem Wert "Requirements- **Version** ".</span><span class="sxs-lookup"><span data-stu-id="bb042-248">For example, if the version of the existing installed module is lower than the **MinimumVersion** value or not equal to the **RequiredVersion** value.</span></span>

<span data-ttu-id="bb042-249">Bei einer Modul Installation werden auch alle abhängigen Module installiert, die vom Modul Herausgeber benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="bb042-249">A module installation will also install any dependent modules specified as required by the module publisher.</span></span>
<span data-ttu-id="bb042-250">Der Verleger gibt die erforderlichen Module und deren Versionen im Modul Manifest an.</span><span class="sxs-lookup"><span data-stu-id="bb042-250">The publisher will specify the required modules and their versions in the module manifest.</span></span>

## <span data-ttu-id="bb042-251">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="bb042-251">RELATED LINKS</span></span>

[<span data-ttu-id="bb042-252">Find-Module</span><span class="sxs-lookup"><span data-stu-id="bb042-252">Find-Module</span></span>](Find-Module.md)

[<span data-ttu-id="bb042-253">Get-PSRepository</span><span class="sxs-lookup"><span data-stu-id="bb042-253">Get-PSRepository</span></span>](Get-PSRepository.md)

[<span data-ttu-id="bb042-254">Import-Module</span><span class="sxs-lookup"><span data-stu-id="bb042-254">Import-Module</span></span>](../Microsoft.PowerShell.Core/Import-Module.md)

[<span data-ttu-id="bb042-255">Publish-Module</span><span class="sxs-lookup"><span data-stu-id="bb042-255">Publish-Module</span></span>](Publish-Module.md)

[<span data-ttu-id="bb042-256">Register-PSRepository</span><span class="sxs-lookup"><span data-stu-id="bb042-256">Register-PSRepository</span></span>](Register-PSRepository.md)

[<span data-ttu-id="bb042-257">Uninstall-Module</span><span class="sxs-lookup"><span data-stu-id="bb042-257">Uninstall-Module</span></span>](Uninstall-Module.md)

[<span data-ttu-id="bb042-258">Update-Module</span><span class="sxs-lookup"><span data-stu-id="bb042-258">Update-Module</span></span>](Update-Module.md)

[<span data-ttu-id="bb042-259">about_Module</span><span class="sxs-lookup"><span data-stu-id="bb042-259">about_Module</span></span>](../Microsoft.PowerShell.Core/About/about_Modules.md)
