---
external help file: PSModule-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PowerShellGet
ms.date: 07/08/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/update-modulemanifest?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Update-ModuleManifest
ms.openlocfilehash: 2977992a04e5a94f5124ec85abd980dc3d4f129f
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93217327"
---
# <span data-ttu-id="40846-103">Update-ModuleManifest</span><span class="sxs-lookup"><span data-stu-id="40846-103">Update-ModuleManifest</span></span>

## <span data-ttu-id="40846-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="40846-104">SYNOPSIS</span></span>
<span data-ttu-id="40846-105">Aktualisiert eine Modulmanifestdatei</span><span class="sxs-lookup"><span data-stu-id="40846-105">Updates a module manifest file.</span></span>

## <span data-ttu-id="40846-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="40846-106">SYNTAX</span></span>

### <span data-ttu-id="40846-107">Alle</span><span class="sxs-lookup"><span data-stu-id="40846-107">All</span></span>

```
Update-ModuleManifest [-Path] <String> [-NestedModules <Object[]>] [-Guid <Guid>] [-Author <String>]
 [-CompanyName <String>] [-Copyright <String>] [-RootModule <String>] [-ModuleVersion <Version>]
 [-Description <String>] [-ProcessorArchitecture <ProcessorArchitecture>]
 [-CompatiblePSEditions <String[]>] [-PowerShellVersion <Version>] [-ClrVersion <Version>]
 [-DotNetFrameworkVersion <Version>] [-PowerShellHostName <String>]
 [-PowerShellHostVersion <Version>] [-RequiredModules <Object[]>] [-TypesToProcess <String[]>]
 [-FormatsToProcess <String[]>] [-ScriptsToProcess <String[]>] [-RequiredAssemblies <String[]>]
 [-FileList <String[]>] [-ModuleList <Object[]>] [-FunctionsToExport <String[]>]
 [-AliasesToExport <String[]>] [-VariablesToExport <String[]>] [-CmdletsToExport <String[]>]
 [-DscResourcesToExport <String[]>] [-PrivateData <Hashtable>] [-Tags <String[]>]
 [-ProjectUri <Uri>] [-LicenseUri <Uri>] [-IconUri <Uri>] [-ReleaseNotes <String[]>]
 [-Prerelease <String>] [-HelpInfoUri <Uri>] [-PassThru] [-DefaultCommandPrefix <String>]
 [-ExternalModuleDependencies <String[]>] [-PackageManagementProviders <String[]>]
 [-RequireLicenseAcceptance] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="40846-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="40846-108">DESCRIPTION</span></span>

<span data-ttu-id="40846-109">Mit dem- `Update-ModuleManifest` Cmdlet wird eine Modul Manifest- `.psd1` Datei () aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="40846-109">The `Update-ModuleManifest` cmdlet updates a module manifest (`.psd1`) file.</span></span>

## <span data-ttu-id="40846-110">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="40846-110">EXAMPLES</span></span>

### <span data-ttu-id="40846-111">Beispiel 1: Aktualisieren eines Modul Manifests</span><span class="sxs-lookup"><span data-stu-id="40846-111">Example 1: Update a module manifest</span></span>

<span data-ttu-id="40846-112">In diesem Beispiel wird eine vorhandene Modul Manifest-Datei aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="40846-112">This example updates an existing module manifest file.</span></span> <span data-ttu-id="40846-113">Splatting wird zum Übergeben von Parameterwerten an verwendet `Update-ModuleManifest` .</span><span class="sxs-lookup"><span data-stu-id="40846-113">Splatting is used to pass parameter values to `Update-ModuleManifest`.</span></span> <span data-ttu-id="40846-114">Weitere Informationen finden Sie unter [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md).</span><span class="sxs-lookup"><span data-stu-id="40846-114">For more information, see [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md).</span></span>

```powershell
$Parms = @{
  Path = "C:\Test\TestManifest.psd1"
  Author = "TestUser1"
  CompanyName = "Contoso Corporation"
  Copyright = "(c) 2019 Contoso Corporation. All rights reserved."
}

Update-ModuleManifest @Parms
```

<span data-ttu-id="40846-115">`$Parms` ist ein splat, das die Parameterwerte für " **path** ", " **Author** ", " **CompanyName** " und " **Copyright** " speichert.</span><span class="sxs-lookup"><span data-stu-id="40846-115">`$Parms` is a splat that stores the parameter values for **Path** , **Author** , **CompanyName** , and **Copyright**.</span></span> <span data-ttu-id="40846-116">`Update-ModuleManifest` Ruft die Parameterwerte aus ab `@Parms` und aktualisiert das Modul Manifest, **TestManifest.psd1**.</span><span class="sxs-lookup"><span data-stu-id="40846-116">`Update-ModuleManifest` gets the parameter values from `@Parms` and updates the module manifest, **TestManifest.psd1**.</span></span>

## <span data-ttu-id="40846-117">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="40846-117">PARAMETERS</span></span>

### <span data-ttu-id="40846-118">-Aliasestoexport</span><span class="sxs-lookup"><span data-stu-id="40846-118">-AliasesToExport</span></span>

<span data-ttu-id="40846-119">Gibt die Aliase an, die das Modul exportiert.</span><span class="sxs-lookup"><span data-stu-id="40846-119">Specifies the aliases that the module exports.</span></span> <span data-ttu-id="40846-120">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="40846-120">Wildcards are permitted.</span></span>

<span data-ttu-id="40846-121">Verwenden Sie diesen Parameter, um die Aliase einzuschränken, die vom Modul exportiert werden.</span><span class="sxs-lookup"><span data-stu-id="40846-121">Use this parameter to restrict the aliases that are exported by the module.</span></span> <span data-ttu-id="40846-122">**Aliasestoexport** kann Aliase aus der Liste der exportierten Aliase entfernen, aber keine Aliase zur Liste hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="40846-122">**AliasesToExport** can remove aliases from the list of exported aliases, but it can't add aliases to the list.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="40846-123">-Autor</span><span class="sxs-lookup"><span data-stu-id="40846-123">-Author</span></span>

<span data-ttu-id="40846-124">Gibt den Autor des Moduls an.</span><span class="sxs-lookup"><span data-stu-id="40846-124">Specifies the module author.</span></span>

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

### <span data-ttu-id="40846-125">-ClrVersion</span><span class="sxs-lookup"><span data-stu-id="40846-125">-ClrVersion</span></span>

<span data-ttu-id="40846-126">Gibt die für das Modul erforderliche Mindestversion der Common Language Runtime (CLR) von Microsoft .NET Framework an.</span><span class="sxs-lookup"><span data-stu-id="40846-126">Specifies the minimum version of the Common Language Runtime (CLR) of the Microsoft .NET Framework that the module requires.</span></span>

```yaml
Type: System.Version
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="40846-127">-Cmdletstoexport</span><span class="sxs-lookup"><span data-stu-id="40846-127">-CmdletsToExport</span></span>

<span data-ttu-id="40846-128">Gibt die Cmdlets an, die das Modul exportiert.</span><span class="sxs-lookup"><span data-stu-id="40846-128">Specifies the cmdlets that the module exports.</span></span> <span data-ttu-id="40846-129">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="40846-129">Wildcards are permitted.</span></span>

<span data-ttu-id="40846-130">Verwenden Sie diesen Parameter, um die Cmdlets einzuschränken, die vom Modul exportiert werden.</span><span class="sxs-lookup"><span data-stu-id="40846-130">Use this parameter to restrict the cmdlets that are exported by the module.</span></span> <span data-ttu-id="40846-131">**Cmdletstoexport** kann Cmdlets aus der Liste der exportierten Cmdlets entfernen, aber keine Cmdlets zur Liste hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="40846-131">**CmdletsToExport** can remove cmdlets from the list of exported cmdlets, but it can't add cmdlets to the list.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="40846-132">-CompanyName</span><span class="sxs-lookup"><span data-stu-id="40846-132">-CompanyName</span></span>

<span data-ttu-id="40846-133">Gibt das Unternehmen oder den Hersteller an, der das Modul erstellt hat.</span><span class="sxs-lookup"><span data-stu-id="40846-133">Specifies the company or vendor who created the module.</span></span>

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

### <span data-ttu-id="40846-134">-Compatiblepseditions</span><span class="sxs-lookup"><span data-stu-id="40846-134">-CompatiblePSEditions</span></span>

<span data-ttu-id="40846-135">Gibt die kompatiblen **pseditions** des Moduls an.</span><span class="sxs-lookup"><span data-stu-id="40846-135">Specifies the compatible **PSEditions** of the module.</span></span> <span data-ttu-id="40846-136">Weitere Informationen zu **ppingdition** finden Sie unter [Module mit kompatiblen PowerShell-Editionen](/powershell/scripting/gallery/concepts/module-psedition-support).</span><span class="sxs-lookup"><span data-stu-id="40846-136">For information about **PSEdition** , see [Modules with compatible PowerShell Editions](/powershell/scripting/gallery/concepts/module-psedition-support).</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:
Accepted values: Desktop, Core

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="40846-137">-Confirm</span><span class="sxs-lookup"><span data-stu-id="40846-137">-Confirm</span></span>

<span data-ttu-id="40846-138">Sie werden zur Bestätigung aufgefordert, bevor Sie ausgeführt werden `Update-ModuleManifest` .</span><span class="sxs-lookup"><span data-stu-id="40846-138">Prompts you for confirmation before running `Update-ModuleManifest`.</span></span>

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

### <span data-ttu-id="40846-139">-Copyright</span><span class="sxs-lookup"><span data-stu-id="40846-139">-Copyright</span></span>

<span data-ttu-id="40846-140">Gibt eine Urheberrechtserklärung für das Modul an.</span><span class="sxs-lookup"><span data-stu-id="40846-140">Specifies a copyright statement for the module.</span></span>

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

### <span data-ttu-id="40846-141">-Defaultcommandprefix</span><span class="sxs-lookup"><span data-stu-id="40846-141">-DefaultCommandPrefix</span></span>

<span data-ttu-id="40846-142">Gibt das Standard Befehls Präfix an.</span><span class="sxs-lookup"><span data-stu-id="40846-142">Specifies the default command prefix.</span></span>

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

### <span data-ttu-id="40846-143">-Description</span><span class="sxs-lookup"><span data-stu-id="40846-143">-Description</span></span>

<span data-ttu-id="40846-144">Gibt eine Beschreibung des Moduls an.</span><span class="sxs-lookup"><span data-stu-id="40846-144">Specifies a description of the module.</span></span>

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

### <span data-ttu-id="40846-145">-Dotnetframeworkversion</span><span class="sxs-lookup"><span data-stu-id="40846-145">-DotNetFrameworkVersion</span></span>

<span data-ttu-id="40846-146">Gibt die für das Modul erforderliche Mindestversion des Microsoft .NET Framework an.</span><span class="sxs-lookup"><span data-stu-id="40846-146">Specifies the minimum version of the Microsoft .NET Framework that the module requires.</span></span>

```yaml
Type: System.Version
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="40846-147">-Dscresourcestoexport</span><span class="sxs-lookup"><span data-stu-id="40846-147">-DscResourcesToExport</span></span>

<span data-ttu-id="40846-148">Gibt die DSC-Ressourcen (DSC) an, die vom Modul exportiert werden.</span><span class="sxs-lookup"><span data-stu-id="40846-148">Specifies the Desired State Configuration (DSC) resources that the module exports.</span></span> <span data-ttu-id="40846-149">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="40846-149">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="40846-150">-Externalmoduledependen</span><span class="sxs-lookup"><span data-stu-id="40846-150">-ExternalModuleDependencies</span></span>

<span data-ttu-id="40846-151">Gibt ein Array externer Modul Abhängigkeiten an.</span><span class="sxs-lookup"><span data-stu-id="40846-151">Specifies an array of external module dependencies.</span></span>

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

### <span data-ttu-id="40846-152">-FileList</span><span class="sxs-lookup"><span data-stu-id="40846-152">-FileList</span></span>

<span data-ttu-id="40846-153">Gibt alle Elemente an, die im Modul enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="40846-153">Specifies all items that are included in the module.</span></span>

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

### <span data-ttu-id="40846-154">-Formatstoprocess</span><span class="sxs-lookup"><span data-stu-id="40846-154">-FormatsToProcess</span></span>

<span data-ttu-id="40846-155">Gibt die Formatierungs Dateien ( `.ps1xml` ) an, die beim Importieren des Moduls ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="40846-155">Specifies the formatting files (`.ps1xml`) that run when the module is imported.</span></span>

<span data-ttu-id="40846-156">Wenn Sie ein Modul importieren, führt PowerShell das `Update-FormatData` Cmdlet mit den angegebenen Dateien aus.</span><span class="sxs-lookup"><span data-stu-id="40846-156">When you import a module, PowerShell runs the `Update-FormatData` cmdlet with the specified files.</span></span>
<span data-ttu-id="40846-157">Da Formatierungs Dateien nicht Bereichs bezogen sind, wirken Sie sich auf alle Sitzungs Zustände in der Sitzung aus.</span><span class="sxs-lookup"><span data-stu-id="40846-157">Because formatting files aren't scoped, they affect all session states in the session.</span></span>

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

### <span data-ttu-id="40846-158">-Functionstoexport</span><span class="sxs-lookup"><span data-stu-id="40846-158">-FunctionsToExport</span></span>

<span data-ttu-id="40846-159">Gibt die Funktionen an, die das Modul exportiert.</span><span class="sxs-lookup"><span data-stu-id="40846-159">Specifies the functions that the module exports.</span></span> <span data-ttu-id="40846-160">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="40846-160">Wildcards are permitted.</span></span>

<span data-ttu-id="40846-161">Verwenden Sie diesen Parameter, um die Funktionen einzuschränken, die vom Modul exportiert werden.</span><span class="sxs-lookup"><span data-stu-id="40846-161">Use this parameter to restrict the functions that are exported by the module.</span></span> <span data-ttu-id="40846-162">**Functionstoexport** kann Funktionen aus der Liste der exportierten Aliase entfernen, aber keine Funktionen zur Liste hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="40846-162">**FunctionsToExport** can remove functions from the list of exported aliases, but it can't add functions to the list.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="40846-163">-GUID</span><span class="sxs-lookup"><span data-stu-id="40846-163">-Guid</span></span>

<span data-ttu-id="40846-164">Gibt einen eindeutigen Bezeichner für das Modul an.</span><span class="sxs-lookup"><span data-stu-id="40846-164">Specifies a unique identifier for the module.</span></span> <span data-ttu-id="40846-165">Die GUID kann verwendet werden, um Module mit dem gleichen Namen zu unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="40846-165">The GUID can be used to distinguish among modules with the same name.</span></span>

```yaml
Type: System.Guid
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="40846-166">-Helpinfouri</span><span class="sxs-lookup"><span data-stu-id="40846-166">-HelpInfoUri</span></span>

<span data-ttu-id="40846-167">Gibt die Internetadresse der **helpinfo-XML** -Datei des Moduls an.</span><span class="sxs-lookup"><span data-stu-id="40846-167">Specifies the internet address of the module's **HelpInfo XML** file.</span></span> <span data-ttu-id="40846-168">Geben Sie einen Uniform Resource Identifier (URI) ein, der mit **http** oder **https** beginnt.</span><span class="sxs-lookup"><span data-stu-id="40846-168">Enter a Uniform Resource Identifier (URI) that begins with **http** or **https**.</span></span>

<span data-ttu-id="40846-169">Die **helpinfo-XML** -Datei unterstützt das Feature "aktualisierbare Hilfe", das in PowerShell Version 3,0 eingeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="40846-169">The **HelpInfo XML** file supports the Updatable Help feature that was introduced in PowerShell version 3.0.</span></span> <span data-ttu-id="40846-170">Sie enthält Informationen über den Speicherort der herunterladbaren Hilfedateien des Moduls und die Versionsnummern der neuesten Hilfedateien für jedes unterstützte Gebiets Schema.</span><span class="sxs-lookup"><span data-stu-id="40846-170">It contains information about the location of the module's downloadable help files and the version numbers of the newest help files for each supported locale.</span></span>

<span data-ttu-id="40846-171">Weitere Informationen zur aktualisierbaren Hilfe finden Sie unter [about_Updatable_Help](../Microsoft.PowerShell.Core/About/about_Updatable_Help.md).</span><span class="sxs-lookup"><span data-stu-id="40846-171">For information about Updatable Help, see [about_Updatable_Help](../Microsoft.PowerShell.Core/About/about_Updatable_Help.md).</span></span>
<span data-ttu-id="40846-172">Informationen zur **helpinfo-XML** -Datei finden Sie [unter unterstützen der aktualisierbaren Hilfe](/powershell/scripting/developer/module/supporting-updatable-help).</span><span class="sxs-lookup"><span data-stu-id="40846-172">For information about the **HelpInfo XML** file, see [Supporting Updatable Help](/powershell/scripting/developer/module/supporting-updatable-help).</span></span>

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="40846-173">-Iconuri</span><span class="sxs-lookup"><span data-stu-id="40846-173">-IconUri</span></span>

<span data-ttu-id="40846-174">Gibt die URL eines Symbols für das Modul an.</span><span class="sxs-lookup"><span data-stu-id="40846-174">Specifies the URL of an icon for the module.</span></span> <span data-ttu-id="40846-175">Das angegebene Symbol wird auf der Katalog Webseite für das Modul angezeigt.</span><span class="sxs-lookup"><span data-stu-id="40846-175">The specified icon is displayed on the gallery web page for the module.</span></span>

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="40846-176">-Licenaburi</span><span class="sxs-lookup"><span data-stu-id="40846-176">-LicenseUri</span></span>

<span data-ttu-id="40846-177">Gibt die URL der Lizenzierungs Bedingungen für das Modul an.</span><span class="sxs-lookup"><span data-stu-id="40846-177">Specifies the URL of licensing terms for the module.</span></span>

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="40846-178">-Modulelist</span><span class="sxs-lookup"><span data-stu-id="40846-178">-ModuleList</span></span>

<span data-ttu-id="40846-179">Gibt ein Array von Modulen an, die im Modul enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="40846-179">Specifies an array of modules that are included in the module.</span></span>

<span data-ttu-id="40846-180">Geben Sie jeden Modulnamen als Zeichenfolge oder Hashtabelle mit den Schlüsseln **ModuleName** und **ModuleVersion** ein.</span><span class="sxs-lookup"><span data-stu-id="40846-180">Enter each module name as a string or as a hash table with **ModuleName** and **ModuleVersion** keys.</span></span> <span data-ttu-id="40846-181">Die Hashtabelle kann auch einen optionalen **GUID** -Schlüssel haben.</span><span class="sxs-lookup"><span data-stu-id="40846-181">The hash table can also have an optional **GUID** key.</span></span> <span data-ttu-id="40846-182">Sie können Zeichenfolgen und Hashtabellen im Parameterwert kombinieren.</span><span class="sxs-lookup"><span data-stu-id="40846-182">You can combine strings and hash tables in the parameter value.</span></span>

<span data-ttu-id="40846-183">Dieser Schlüssel ist als Modulinventar konzipiert.</span><span class="sxs-lookup"><span data-stu-id="40846-183">This key is designed to act as a module inventory.</span></span> <span data-ttu-id="40846-184">Die Module, die im Wert dieses Schlüssels aufgeführt sind, werden nicht automatisch verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="40846-184">The modules that are listed in the value of this key aren't automatically processed.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="40846-185">-Moduleversion</span><span class="sxs-lookup"><span data-stu-id="40846-185">-ModuleVersion</span></span>

<span data-ttu-id="40846-186">Gibt die Version des Moduls an.</span><span class="sxs-lookup"><span data-stu-id="40846-186">Specifies the version of the module.</span></span>

```yaml
Type: System.Version
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="40846-187">-Netstedmodules</span><span class="sxs-lookup"><span data-stu-id="40846-187">-NestedModules</span></span>

<span data-ttu-id="40846-188">Gibt Skript Module ( `.psm1` ) und binäre Module ( `.dll` ) an, die in den Sitzungs Status des Moduls importiert werden.</span><span class="sxs-lookup"><span data-stu-id="40846-188">Specifies script modules (`.psm1`) and binary modules (`.dll`) that are imported into the module's session state.</span></span> <span data-ttu-id="40846-189">Die Dateien im Schlüssel " **netstedmodules** " werden in der Reihenfolge ausgeführt, in der Sie im Wert aufgelistet sind.</span><span class="sxs-lookup"><span data-stu-id="40846-189">The files in the **NestedModules** key run in the order in which they're listed in the value.</span></span>

<span data-ttu-id="40846-190">Geben Sie jeden Modulnamen als Zeichenfolge oder Hashtabelle mit den Schlüsseln **ModuleName** und **ModuleVersion** ein.</span><span class="sxs-lookup"><span data-stu-id="40846-190">Enter each module name as a string or as a hash table with **ModuleName** and **ModuleVersion** keys.</span></span> <span data-ttu-id="40846-191">Die Hashtabelle kann auch einen optionalen **GUID** -Schlüssel haben.</span><span class="sxs-lookup"><span data-stu-id="40846-191">The hash table can also have an optional **GUID** key.</span></span> <span data-ttu-id="40846-192">Sie können Zeichenfolgen und Hashtabellen im Parameterwert kombinieren.</span><span class="sxs-lookup"><span data-stu-id="40846-192">You can combine strings and hash tables in the parameter value.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="40846-193">-Packagemanagementproviders</span><span class="sxs-lookup"><span data-stu-id="40846-193">-PackageManagementProviders</span></span>

<span data-ttu-id="40846-194">Gibt ein Array von Paket Verwaltungs Anbietern an.</span><span class="sxs-lookup"><span data-stu-id="40846-194">Specifies an array of package management providers.</span></span>

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

### <span data-ttu-id="40846-195">-PassThru</span><span class="sxs-lookup"><span data-stu-id="40846-195">-PassThru</span></span>

<span data-ttu-id="40846-196">Gibt ein Objekt zurück, das das Element darstellt, mit dem Sie arbeiten.</span><span class="sxs-lookup"><span data-stu-id="40846-196">Returns an object representing the item with which you're working.</span></span> <span data-ttu-id="40846-197">Standardmäßig `Update-ModuleManifest` generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="40846-197">By default, `Update-ModuleManifest` doesn't generate any output.</span></span>

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

### <span data-ttu-id="40846-198">-Path</span><span class="sxs-lookup"><span data-stu-id="40846-198">-Path</span></span>

<span data-ttu-id="40846-199">Gibt den Pfad und den Dateinamen des Modul Manifests an.</span><span class="sxs-lookup"><span data-stu-id="40846-199">Specifies the path and file name of the module manifest.</span></span> <span data-ttu-id="40846-200">Geben Sie einen Pfad und einen Dateinamen mit einer `.psd1` Dateinamenerweiterung ein, z `$PSHOME\Modules\MyModule\MyModule.psd1` . b..</span><span class="sxs-lookup"><span data-stu-id="40846-200">Enter a path and file name with a `.psd1` file name extension, such as `$PSHOME\Modules\MyModule\MyModule.psd1`.</span></span>

<span data-ttu-id="40846-201">Wenn Sie den Pfad zu einer vorhandenen Datei angeben, wird `Update-ModuleManifest` die Datei von ohne Warnung ersetzt, es sei denn, die Datei verfügt über das Attribut "schreibgeschützt".</span><span class="sxs-lookup"><span data-stu-id="40846-201">If you specify the path to an existing file, `Update-ModuleManifest` replaces the file without warning unless the file has the read-only attribute.</span></span>

<span data-ttu-id="40846-202">Das Manifest sollte sich im Verzeichnis des Moduls befinden, und der Name der Manifest-Datei muss mit dem Namen des Modul Verzeichnisses übereinstimmen, aber mit einer `.psd1` Erweiterung.</span><span class="sxs-lookup"><span data-stu-id="40846-202">The manifest should be located in the module's directory, and the manifest file name should be the same as the module directory name, but with a `.psd1` extension.</span></span>

<span data-ttu-id="40846-203">Sie können keine Variablen (z. b. oder) als `$PSHOME` `$HOME` Antwort auf eine Eingabeaufforderung für einen **path** -Parameter verwenden.</span><span class="sxs-lookup"><span data-stu-id="40846-203">You can't use variables, such as `$PSHOME` or `$HOME`, in response to a prompt for a **Path** parameter value.</span></span> <span data-ttu-id="40846-204">Um eine Variable zu verwenden, schließen Sie den **Path** -Parameter in den Befehl ein.</span><span class="sxs-lookup"><span data-stu-id="40846-204">To use a variable, include the **Path** parameter in the command.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="40846-205">-Powershellhostname</span><span class="sxs-lookup"><span data-stu-id="40846-205">-PowerShellHostName</span></span>

<span data-ttu-id="40846-206">Gibt den Namen des PowerShell-Host Programms an, das für das Modul erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="40846-206">Specifies the name of the PowerShell host program that the module requires.</span></span> <span data-ttu-id="40846-207">Geben Sie den Namen des Host Programms ein, z. b. PowerShell ISE-Host oder ConsoleHost.</span><span class="sxs-lookup"><span data-stu-id="40846-207">Enter the name of the host program, such as PowerShell ISE Host or ConsoleHost.</span></span> <span data-ttu-id="40846-208">Platzhalter sind nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="40846-208">Wildcards aren't permitted.</span></span>

<span data-ttu-id="40846-209">Um den Namen eines Host Programms zu suchen, geben Sie im Programm ein `$Host.Name` .</span><span class="sxs-lookup"><span data-stu-id="40846-209">To find the name of a host program, in the program, type `$Host.Name`.</span></span>

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

### <span data-ttu-id="40846-210">-Powershellhostversion</span><span class="sxs-lookup"><span data-stu-id="40846-210">-PowerShellHostVersion</span></span>

<span data-ttu-id="40846-211">Gibt die Mindestversion des PowerShell-Host Programms an, das mit dem Modul funktioniert.</span><span class="sxs-lookup"><span data-stu-id="40846-211">Specifies the minimum version of the PowerShell host program that works with the module.</span></span> <span data-ttu-id="40846-212">Geben Sie eine Versionsnummer an, z. B. 1.1.</span><span class="sxs-lookup"><span data-stu-id="40846-212">Enter a version number, such as 1.1.</span></span>

```yaml
Type: System.Version
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="40846-213">-PowerShellVersion</span><span class="sxs-lookup"><span data-stu-id="40846-213">-PowerShellVersion</span></span>

<span data-ttu-id="40846-214">Gibt die Mindestversion von PowerShell an, die mit diesem Modul funktionieren wird.</span><span class="sxs-lookup"><span data-stu-id="40846-214">Specifies the minimum version of PowerShell that will work with this module.</span></span> <span data-ttu-id="40846-215">Sie können z. b. 3,0, 4,0 oder 5,0 als Wert dieses Parameters angeben.</span><span class="sxs-lookup"><span data-stu-id="40846-215">For example, you can specify 3.0, 4.0, or 5.0 as the value of this parameter.</span></span>

```yaml
Type: System.Version
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="40846-216">-Vorabversion</span><span class="sxs-lookup"><span data-stu-id="40846-216">-Prerelease</span></span>

<span data-ttu-id="40846-217">Gibt an, dass das Modul eine Vorabversion ist.</span><span class="sxs-lookup"><span data-stu-id="40846-217">Indicates the module is prerelease.</span></span>

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

### <span data-ttu-id="40846-218">-PRIVATEDATA</span><span class="sxs-lookup"><span data-stu-id="40846-218">-PrivateData</span></span>

<span data-ttu-id="40846-219">Gibt Daten an, die beim Importieren an das Modul übermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="40846-219">Specifies data that is passed to the module when it's imported.</span></span>

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="40846-220">-ProcessorArchitecture</span><span class="sxs-lookup"><span data-stu-id="40846-220">-ProcessorArchitecture</span></span>

<span data-ttu-id="40846-221">Gibt die Prozessorarchitektur an, die das Modul erfordert.</span><span class="sxs-lookup"><span data-stu-id="40846-221">Specifies the processor architecture that the module requires.</span></span>

<span data-ttu-id="40846-222">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="40846-222">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="40846-223">Amd64</span><span class="sxs-lookup"><span data-stu-id="40846-223">Amd64</span></span>
- <span data-ttu-id="40846-224">Arm</span><span class="sxs-lookup"><span data-stu-id="40846-224">Arm</span></span>
- <span data-ttu-id="40846-225">IA64</span><span class="sxs-lookup"><span data-stu-id="40846-225">IA64</span></span>
- <span data-ttu-id="40846-226">MSIL</span><span class="sxs-lookup"><span data-stu-id="40846-226">MSIL</span></span>
- <span data-ttu-id="40846-227">None (unbekannt oder nicht angegeben)</span><span class="sxs-lookup"><span data-stu-id="40846-227">None (unknown or unspecified)</span></span>
- <span data-ttu-id="40846-228">X86</span><span class="sxs-lookup"><span data-stu-id="40846-228">X86</span></span>

```yaml
Type: System.Reflection.ProcessorArchitecture
Parameter Sets: (All)
Aliases:
Accepted values: None, MSIL, X86, IA64, Amd64, Arm

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="40846-229">-Projecturi</span><span class="sxs-lookup"><span data-stu-id="40846-229">-ProjectUri</span></span>

<span data-ttu-id="40846-230">Gibt die URL einer Webseite zu diesem Projekt an.</span><span class="sxs-lookup"><span data-stu-id="40846-230">Specifies the URL of a web page about this project.</span></span>

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="40846-231">-Releasenotes</span><span class="sxs-lookup"><span data-stu-id="40846-231">-ReleaseNotes</span></span>

<span data-ttu-id="40846-232">Gibt ein Zeichen folgen Array an, das Anmerkungen oder Kommentare enthält, die Sie für diese Version des Skripts zur Verfügung stellen möchten.</span><span class="sxs-lookup"><span data-stu-id="40846-232">Specifies a string array that contains release notes or comments that you want available for this version of the script.</span></span>

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

### <span data-ttu-id="40846-233">-Requirelicenabakzeptanz</span><span class="sxs-lookup"><span data-stu-id="40846-233">-RequireLicenseAcceptance</span></span>

<span data-ttu-id="40846-234">Gibt an, dass für das Modul eine Zustimmung zur Lizenz erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="40846-234">Specifies that a license acceptance is required for the module.</span></span>

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

### <span data-ttu-id="40846-235">-Requirements dassemblys</span><span class="sxs-lookup"><span data-stu-id="40846-235">-RequiredAssemblies</span></span>

<span data-ttu-id="40846-236">Gibt die Assemblydateien ( `.dll` ) an, die das Modul erfordert.</span><span class="sxs-lookup"><span data-stu-id="40846-236">Specifies the assembly (`.dll`) files that the module requires.</span></span> <span data-ttu-id="40846-237">Geben Sie die Namen der Assemblydateien ein.</span><span class="sxs-lookup"><span data-stu-id="40846-237">Enter the assembly file names.</span></span>
<span data-ttu-id="40846-238">PowerShell lädt die angegebenen Assemblys vor dem Aktualisieren von Typen oder Formaten, dem Importieren von geschbten Modulen oder dem Importieren der Modul Datei, die im Wert des **rootmodule** -Schlüssels angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="40846-238">PowerShell loads the specified assemblies before updating types or formats, importing nested modules, or importing the module file that is specified in the value of the **RootModule** key.</span></span>

<span data-ttu-id="40846-239">Verwenden Sie diesen Parameter, um alle Assemblys anzugeben, die das Modul benötigt, einschließlich Assemblys, die geladen werden müssen, um Formatierungs-oder Typdateien zu aktualisieren, die in den Schlüsseln **formatstoprocess** oder **typestoprocess** aufgeführt sind, auch wenn diese Assemblys auch als binäre Module im Schlüssel " **netstedmodules** " aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="40846-239">Use this parameter to specify all the assemblies that the module requires, including assemblies that must be loaded to update any formatting or type files that are listed in the **FormatsToProcess** or **TypesToProcess** keys, even if those assemblies are also listed as binary modules in the **NestedModules** key.</span></span>

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

### <span data-ttu-id="40846-240">-Requirements dmodules</span><span class="sxs-lookup"><span data-stu-id="40846-240">-RequiredModules</span></span>

<span data-ttu-id="40846-241">Gibt die Module an, die im globalen Sitzungsstatus enthalten sein müssen.</span><span class="sxs-lookup"><span data-stu-id="40846-241">Specifies modules that must be in the global session state.</span></span> <span data-ttu-id="40846-242">Wenn sich die erforderlichen Module nicht im globalen Sitzungs Status befinden, importiert PowerShell Sie.</span><span class="sxs-lookup"><span data-stu-id="40846-242">If the required modules aren't in the global session state, PowerShell imports them.</span></span> <span data-ttu-id="40846-243">Wenn die erforderlichen Module nicht verfügbar sind, `Import-Module` schlägt der Befehl fehl.</span><span class="sxs-lookup"><span data-stu-id="40846-243">If the required modules aren't available, the `Import-Module` command fails.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="40846-244">-Rootmodule</span><span class="sxs-lookup"><span data-stu-id="40846-244">-RootModule</span></span>

<span data-ttu-id="40846-245">Gibt die primäre oder Stammdatei des Moduls an.</span><span class="sxs-lookup"><span data-stu-id="40846-245">Specifies the primary or root file of the module.</span></span> <span data-ttu-id="40846-246">Geben Sie den Dateinamen eines Skripts ( `.ps1` ), eines Skript Moduls ( `.psm1` ), eines Modul Manifests ( `.psd1` ), einer Assembly ( `.dll` ), einer Cmdlet-Definitions-XML-Datei ( `.cdxml` ) oder eines Workflows () ein `.xaml` .</span><span class="sxs-lookup"><span data-stu-id="40846-246">Enter the file name of a script (`.ps1`), a script module (`.psm1`), a module manifest (`.psd1`), an assembly (`.dll`), a cmdlet definition XML file (`.cdxml`), or a workflow (`.xaml`).</span></span> <span data-ttu-id="40846-247">Wenn das Modul importiert wird, werden die aus der Stammmodul-Datei exportierten Member in den Sitzungsstatus des Aufrufers importiert.</span><span class="sxs-lookup"><span data-stu-id="40846-247">When the module is imported, the members that are exported from the root module file are imported into the caller's session state.</span></span>

<span data-ttu-id="40846-248">Wenn ein Modul über eine Manifest-Datei verfügt und im **rootmodule** -Schlüssel keine Stammdatei angegeben wurde, wird das Manifest zur primären Datei für das Modul.</span><span class="sxs-lookup"><span data-stu-id="40846-248">If a module has a manifest file and no root file has been specified in the **RootModule** key, the manifest becomes the primary file for the module.</span></span> <span data-ttu-id="40846-249">Und das Modul wird zu einem Manifest-Modul (ModuleType = Manifest).</span><span class="sxs-lookup"><span data-stu-id="40846-249">And, the module becomes a manifest module (ModuleType = Manifest).</span></span>

<span data-ttu-id="40846-250">Zum Exportieren von Membern aus- `.psm1` oder- `.dll` Dateien in einem Modul mit einem Manifest müssen die Namen dieser Dateien in den Werten der **rootmodule** -oder **netstedmodules** -Schlüssel im Manifest angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="40846-250">To export members from `.psm1` or `.dll` files in a module that has a manifest, the names of those files must be specified in the values of the **RootModule** or **NestedModules** keys in the manifest.</span></span> <span data-ttu-id="40846-251">Andernfalls werden die Member nicht exportiert.</span><span class="sxs-lookup"><span data-stu-id="40846-251">Otherwise, their members aren't exported.</span></span>

<span data-ttu-id="40846-252">In PowerShell 2,0 hieß dieser Schlüssel " **moduletoprocess** ".</span><span class="sxs-lookup"><span data-stu-id="40846-252">In PowerShell 2.0, this key was called **ModuleToProcess**.</span></span>

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

### <span data-ttu-id="40846-253">-Scriptstoprocess</span><span class="sxs-lookup"><span data-stu-id="40846-253">-ScriptsToProcess</span></span>

<span data-ttu-id="40846-254">Gibt Skript `.ps1` Dateien () an, die im Sitzungszustand des Aufrufers ausgeführt werden, wenn das Modul importiert wird.</span><span class="sxs-lookup"><span data-stu-id="40846-254">Specifies script (`.ps1`) files that run in the caller's session state when the module is imported.</span></span>
<span data-ttu-id="40846-255">Sie können diese Skripte zur Vorbereitung einer Umgebung verwenden, wie Sie ein Anmeldeskript verwenden würden.</span><span class="sxs-lookup"><span data-stu-id="40846-255">You can use these scripts to prepare an environment, just as you might use a login script.</span></span>

<span data-ttu-id="40846-256">Um Skripte anzugeben, die im Sitzungsstatus des Moduls ausgeführt werden, verwenden Sie den **NestedModules** -Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="40846-256">To specify scripts that run in the module's session state, use the **NestedModules** key.</span></span>

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

### <span data-ttu-id="40846-257">-Tags</span><span class="sxs-lookup"><span data-stu-id="40846-257">-Tags</span></span>

<span data-ttu-id="40846-258">Gibt ein Array von-Tags an.</span><span class="sxs-lookup"><span data-stu-id="40846-258">Specifies an array of tags.</span></span>

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

### <span data-ttu-id="40846-259">-Typestoprocess</span><span class="sxs-lookup"><span data-stu-id="40846-259">-TypesToProcess</span></span>

<span data-ttu-id="40846-260">Gibt die Typdateien ( `.ps1xml` ) an, die beim Importieren des Moduls ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="40846-260">Specifies the type files (`.ps1xml`) that run when the module is imported.</span></span>

<span data-ttu-id="40846-261">Wenn Sie das Modul importieren, führt PowerShell das `Update-TypeData` Cmdlet mit den angegebenen Dateien aus.</span><span class="sxs-lookup"><span data-stu-id="40846-261">When you import the module, PowerShell runs the `Update-TypeData` cmdlet with the specified files.</span></span>
<span data-ttu-id="40846-262">Da Typdateien nicht Bereichs bezogen sind, wirken Sie sich auf alle Sitzungs Zustände in der Sitzung aus.</span><span class="sxs-lookup"><span data-stu-id="40846-262">Because type files aren't scoped, they affect all session states in the session.</span></span>

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

### <span data-ttu-id="40846-263">-Variablestoexport</span><span class="sxs-lookup"><span data-stu-id="40846-263">-VariablesToExport</span></span>

<span data-ttu-id="40846-264">Gibt die Variablen an, die das Modul exportiert.</span><span class="sxs-lookup"><span data-stu-id="40846-264">Specifies the variables that the module exports.</span></span> <span data-ttu-id="40846-265">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="40846-265">Wildcards are permitted.</span></span>

<span data-ttu-id="40846-266">Verwenden Sie diesen Parameter, um die Variablen einzuschränken, die vom Modul exportiert werden.</span><span class="sxs-lookup"><span data-stu-id="40846-266">Use this parameter to restrict the variables that are exported by the module.</span></span> <span data-ttu-id="40846-267">**Variablestoexport** kann Variablen aus der Liste der exportierten Variablen entfernen, aber keine Variablen zur Liste hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="40846-267">**VariablesToExport** can remove variables from the list of exported variables, but it can't add variables to the list.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="40846-268">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="40846-268">-WhatIf</span></span>

<span data-ttu-id="40846-269">Zeigt, was geschieht, wenn ausgeführt wird `Update-ModuleManifest` .</span><span class="sxs-lookup"><span data-stu-id="40846-269">Shows what would happen if `Update-ModuleManifest` runs.</span></span> <span data-ttu-id="40846-270">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="40846-270">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="40846-271">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="40846-271">CommonParameters</span></span>

<span data-ttu-id="40846-272">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="40846-272">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="40846-273">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="40846-273">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="40846-274">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="40846-274">INPUTS</span></span>

### <span data-ttu-id="40846-275">System.String</span><span class="sxs-lookup"><span data-stu-id="40846-275">System.String</span></span>

## <span data-ttu-id="40846-276">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="40846-276">OUTPUTS</span></span>

### <span data-ttu-id="40846-277">System.Object</span><span class="sxs-lookup"><span data-stu-id="40846-277">System.Object</span></span>

## <span data-ttu-id="40846-278">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="40846-278">NOTES</span></span>

## <span data-ttu-id="40846-279">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="40846-279">RELATED LINKS</span></span>
