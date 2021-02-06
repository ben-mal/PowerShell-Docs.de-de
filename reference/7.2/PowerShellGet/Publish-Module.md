---
external help file: PSModule-help.xml
Locale: en-US
Module Name: PowerShellGet
ms.date: 10/03/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/publish-module?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Publish-Module
ms.openlocfilehash: 2edc05ff660cfcca232af878c593c29de68eb122
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/19/2020
ms.locfileid: "99602535"
---
# <span data-ttu-id="b6c6a-102">Publish-Module</span><span class="sxs-lookup"><span data-stu-id="b6c6a-102">Publish-Module</span></span>

## <span data-ttu-id="b6c6a-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="b6c6a-103">SYNOPSIS</span></span>
<span data-ttu-id="b6c6a-104">Veröffentlicht ein angegebenes Modul aus dem lokalen Computer in einem Onlinekatalog</span><span class="sxs-lookup"><span data-stu-id="b6c6a-104">Publishes a specified module from the local computer to an online gallery.</span></span>

## <span data-ttu-id="b6c6a-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b6c6a-105">SYNTAX</span></span>

### <span data-ttu-id="b6c6a-106">Modulenameparameterset (Standard)</span><span class="sxs-lookup"><span data-stu-id="b6c6a-106">ModuleNameParameterSet (Default)</span></span>

```
Publish-Module -Name <String> [-RequiredVersion <String>] [-NuGetApiKey <String>]
 [-Repository <String>] [-Credential <PSCredential>] [-FormatVersion <Version>]
 [-ReleaseNotes <String[]>] [-Tags <String[]>] [-LicenseUri <Uri>] [-IconUri <Uri>]
 [-ProjectUri <Uri>] [-Exclude <String[]>] [-Force] [-AllowPrerelease] [-SkipAutomaticTags]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="b6c6a-107">Modulepathparameterset</span><span class="sxs-lookup"><span data-stu-id="b6c6a-107">ModulePathParameterSet</span></span>

```
Publish-Module -Path <String> [-NuGetApiKey <String>] [-Repository <String>]
 [-Credential <PSCredential>] [-FormatVersion <Version>] [-ReleaseNotes <String[]>]
 [-Tags <String[]>] [-LicenseUri <Uri>] [-IconUri <Uri>] [-ProjectUri <Uri>] [-Force]
 [-SkipAutomaticTags] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="b6c6a-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b6c6a-108">DESCRIPTION</span></span>

<span data-ttu-id="b6c6a-109">Das `Publish-Module` -Cmdlet veröffentlicht ein Modul in einem nuget-basierten Onlinekatalog mithilfe eines API-Schlüssels, der als Teil des Benutzerprofils im Katalog gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="b6c6a-109">The `Publish-Module` cmdlet publishes a module to an online NuGet-based gallery by using an API key, stored as part of a user's profile in the gallery.</span></span> <span data-ttu-id="b6c6a-110">Sie können entweder den Namen des Moduls angeben, das veröffentlicht werden soll, oder Sie geben den Pfad zum Ordner an, der das Modul enthält.</span><span class="sxs-lookup"><span data-stu-id="b6c6a-110">You can specify the module to publish either by the module's name, or by the path to the folder containing the module.</span></span>

<span data-ttu-id="b6c6a-111">Wenn Sie ein Modul nach Name angeben, `Publish-Module` veröffentlicht das erste Modul, das durch Ausführen von gefunden wird `Get-Module -ListAvailable <Name>` .</span><span class="sxs-lookup"><span data-stu-id="b6c6a-111">When you specify a module by name, `Publish-Module` publishes the first module that would be found by running `Get-Module -ListAvailable <Name>`.</span></span> <span data-ttu-id="b6c6a-112">Wenn Sie eine Mindestversion eines zu veröffentlichenden Moduls angeben, `Publish-Module` veröffentlicht das erste Modul mit einer Version, die größer oder gleich der von Ihnen angegebenen Mindestversion ist.</span><span class="sxs-lookup"><span data-stu-id="b6c6a-112">If you specify a minimum version of a module to publish, `Publish-Module` publishes the first module with a version that is greater than or equal to the minimum version that you have specified.</span></span>

<span data-ttu-id="b6c6a-113">Die Veröffentlichung eines Moduls erfordert Metadaten, die auf der Seite „Katalog“ des Moduls angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="b6c6a-113">Publishing a module requires metadata that is displayed on the gallery page for the module.</span></span> <span data-ttu-id="b6c6a-114">Die erforderlichen Metadaten enthalten den Modulnamen, die Version, die Beschreibung und den Autor.</span><span class="sxs-lookup"><span data-stu-id="b6c6a-114">Required metadata includes the module name, version, description, and author.</span></span> <span data-ttu-id="b6c6a-115">Obwohl die meisten Metadaten aus dem Modul Manifest entnommen werden, müssen einige Metadaten in `Publish-Module` Parametern angegeben werden, wie z. b. **Tag**, **Releasenote**, **iconuri**, **projecturi** und **licentaruri**, da diese Parameter den Feldern in einem nuget-basierten Katalog entsprechen.</span><span class="sxs-lookup"><span data-stu-id="b6c6a-115">Although most metadata is taken from the module manifest, some metadata must be specified in `Publish-Module` parameters, such as **Tag**, **ReleaseNote**, **IconUri**, **ProjectUri**, and **LicenseUri**, because these parameters match fields in a NuGet-based gallery.</span></span>

## <span data-ttu-id="b6c6a-116">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="b6c6a-116">EXAMPLES</span></span>

### <span data-ttu-id="b6c6a-117">Beispiel 1: Veröffentlichen eines Moduls</span><span class="sxs-lookup"><span data-stu-id="b6c6a-117">Example 1: Publish a module</span></span>

<span data-ttu-id="b6c6a-118">In diesem Beispiel wird mydscmodule mithilfe des API-Schlüssels im Onlinekatalog veröffentlicht, um das Onlinekatalog Konto des Modul Besitzers anzugeben.</span><span class="sxs-lookup"><span data-stu-id="b6c6a-118">In this example, MyDscModule is published to the online gallery by using the API key to indicate the module owner's online gallery account.</span></span> <span data-ttu-id="b6c6a-119">Wenn mydscmodule kein gültiges Manifest-Modul ist, das einen Namen, eine Version, eine Beschreibung und einen Autor angibt, tritt ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="b6c6a-119">If MyDscModule is not a valid manifest module that specifies a name, version, description, and author, an error occurs.</span></span>

```powershell
Publish-Module -Name "MyDscModule" -NuGetApiKey "11e4b435-6cb4-4bf7-8611-5162ed75eb73"
```

### <span data-ttu-id="b6c6a-120">Beispiel 2: Veröffentlichen eines Moduls mit Katalog Metadaten</span><span class="sxs-lookup"><span data-stu-id="b6c6a-120">Example 2: Publish a module with gallery metadata</span></span>

<span data-ttu-id="b6c6a-121">In diesem Beispiel wird mydscmodule mithilfe des API-Schlüssels im Onlinekatalog veröffentlicht, um das Katalog Konto des Modul Besitzers anzugeben.</span><span class="sxs-lookup"><span data-stu-id="b6c6a-121">In this example, MyDscModule is published to the online gallery by using the API key to indicate the module owner's gallery account.</span></span> <span data-ttu-id="b6c6a-122">Die zusätzlichen bereitgestellten Metadaten werden auf der Webseite für das Modul im Katalog angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b6c6a-122">The additional metadata provided is displayed on the webpage for the module in the gallery.</span></span> <span data-ttu-id="b6c6a-123">Der Besitzer fügt zwei suchtags für das Modul hinzu und bezieht sich auf Active Directory. Es wird ein kurzer Versions Hinweis hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="b6c6a-123">The owner adds two search tags for the module, relating it to Active Directory; a brief release note is added.</span></span> <span data-ttu-id="b6c6a-124">Wenn mydscmodule kein gültiges Manifest-Modul ist, das einen Namen, eine Version, eine Beschreibung und einen Autor angibt, tritt ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="b6c6a-124">If MyDscModule is not a valid manifest module that specifies a name, version, description, and author, an error occurs.</span></span>

```powershell
Publish-Module -Name "MyDscModule" -NuGetApiKey "11e4b435-6cb4-4bf7-8611-5162ed75eb73" -LicenseUri "http://contoso.com/license" -Tag "Active Directory","DSC" -ReleaseNote "Updated the ActiveDirectory DSC Resources to support adding users."
```

## <span data-ttu-id="b6c6a-125">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b6c6a-125">PARAMETERS</span></span>

### <span data-ttu-id="b6c6a-126">-Allowprerelease</span><span class="sxs-lookup"><span data-stu-id="b6c6a-126">-AllowPrerelease</span></span>

<span data-ttu-id="b6c6a-127">Ermöglicht das Veröffentlichen von Modulen, die als Vorabversion markiert sind.</span><span class="sxs-lookup"><span data-stu-id="b6c6a-127">Allows modules marked as prerelease to be published.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ModuleNameParameterSet
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b6c6a-128">-Confirm</span><span class="sxs-lookup"><span data-stu-id="b6c6a-128">-Confirm</span></span>

<span data-ttu-id="b6c6a-129">Fordert Sie zur Bestätigung auf, bevor Sie den ausführen `Publish-Module` .</span><span class="sxs-lookup"><span data-stu-id="b6c6a-129">Prompts you for confirmation before running the `Publish-Module`.</span></span>

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

### <span data-ttu-id="b6c6a-130">-Credential</span><span class="sxs-lookup"><span data-stu-id="b6c6a-130">-Credential</span></span>

<span data-ttu-id="b6c6a-131">Gibt ein Benutzerkonto an, das über Rechte zum Veröffentlichen eines Moduls für einen angegebenen Paketanbieter oder eine angegebene Quelle verfügt.</span><span class="sxs-lookup"><span data-stu-id="b6c6a-131">Specifies a user account that has rights to publish a module for a specified package provider or source.</span></span>

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

### <span data-ttu-id="b6c6a-132">-Ausschließen</span><span class="sxs-lookup"><span data-stu-id="b6c6a-132">-Exclude</span></span>

<span data-ttu-id="b6c6a-133">Definiert Dateien, die aus dem veröffentlichten Modul ausgeschlossen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="b6c6a-133">Defines files to exclude from the published module.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ModuleNameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b6c6a-134">-Force</span><span class="sxs-lookup"><span data-stu-id="b6c6a-134">-Force</span></span>

<span data-ttu-id="b6c6a-135">Erzwingt die Ausführung des Befehls ohne Aufforderung zur Bestätigung durch den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="b6c6a-135">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="b6c6a-136">-Format Version</span><span class="sxs-lookup"><span data-stu-id="b6c6a-136">-FormatVersion</span></span>

<span data-ttu-id="b6c6a-137">Akzeptiert nur gültige Werte, die durch das **validateset** -Attribut angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="b6c6a-137">Accepts only valid values specified by the **ValidateSet** attribute.</span></span>

<span data-ttu-id="b6c6a-138">Weitere Informationen finden Sie unter [validateset-Attribut Deklaration](/powershell/scripting/developer/cmdlet/validateset-attribute-declaration) und [validatesetattribute](/dotnet/api/system.management.automation.validatesetattribute).</span><span class="sxs-lookup"><span data-stu-id="b6c6a-138">For more information, see [ValidateSet Attribute Declaration](/powershell/scripting/developer/cmdlet/validateset-attribute-declaration) and [ValidateSetAttribute](/dotnet/api/system.management.automation.validatesetattribute).</span></span>

```yaml
Type: System.Version
Parameter Sets: (All)
Aliases:
Accepted values: 2.0

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b6c6a-139">-Iconuri</span><span class="sxs-lookup"><span data-stu-id="b6c6a-139">-IconUri</span></span>

<span data-ttu-id="b6c6a-140">Gibt die URL eines Symbols für das Modul an.</span><span class="sxs-lookup"><span data-stu-id="b6c6a-140">Specifies the URL of an icon for the module.</span></span> <span data-ttu-id="b6c6a-141">Das angegebene Symbol wird auf der Katalog Webseite für das Modul angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b6c6a-141">The specified icon is displayed on the gallery webpage for the module.</span></span>

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

### <span data-ttu-id="b6c6a-142">-Licenaburi</span><span class="sxs-lookup"><span data-stu-id="b6c6a-142">-LicenseUri</span></span>

<span data-ttu-id="b6c6a-143">Gibt die URL der Lizenzierungs Bedingungen für das Modul an, das Sie veröffentlichen möchten.</span><span class="sxs-lookup"><span data-stu-id="b6c6a-143">Specifies the URL of licensing terms for the module you want to publish.</span></span>

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

### <span data-ttu-id="b6c6a-144">-Name</span><span class="sxs-lookup"><span data-stu-id="b6c6a-144">-Name</span></span>

<span data-ttu-id="b6c6a-145">Gibt den Namen des Moduls an, das Sie veröffentlichen möchten.</span><span class="sxs-lookup"><span data-stu-id="b6c6a-145">Specifies the name of the module that you want to publish.</span></span> <span data-ttu-id="b6c6a-146">`Publish-Module` sucht nach dem angegebenen Modulnamen in `$Env:PSModulePath` .</span><span class="sxs-lookup"><span data-stu-id="b6c6a-146">`Publish-Module` searches for the specified module name in `$Env:PSModulePath`.</span></span>

```yaml
Type: System.String
Parameter Sets: ModuleNameParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="b6c6a-147">-Nugetapikey</span><span class="sxs-lookup"><span data-stu-id="b6c6a-147">-NuGetApiKey</span></span>

<span data-ttu-id="b6c6a-148">Gibt den API-Schlüssel an, den Sie zum Veröffentlichen eines Moduls im Onlinekatalog verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="b6c6a-148">Specifies the API key that you want to use to publish a module to the online gallery.</span></span> <span data-ttu-id="b6c6a-149">Der API-Schlüssel ist Teil Ihres Profils im Onlinekatalog. Sie finden Sie auf der Seite Benutzerkonto im Katalog.</span><span class="sxs-lookup"><span data-stu-id="b6c6a-149">The API key is part of your profile in the online gallery, and can be found on your user account page in the gallery.</span></span> <span data-ttu-id="b6c6a-150">Der API-Schlüssel ist eine nuget-spezifische Funktionalität.</span><span class="sxs-lookup"><span data-stu-id="b6c6a-150">The API key is NuGet-specific functionality.</span></span>

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

### <span data-ttu-id="b6c6a-151">-Path</span><span class="sxs-lookup"><span data-stu-id="b6c6a-151">-Path</span></span>

<span data-ttu-id="b6c6a-152">Gibt den Pfad zu dem Modul an, das Sie veröffentlichen möchten.</span><span class="sxs-lookup"><span data-stu-id="b6c6a-152">Specifies the path to the module that you want to publish.</span></span> <span data-ttu-id="b6c6a-153">Dieser Parameter akzeptiert den Pfad zu dem Ordner, der das Modul enthält.</span><span class="sxs-lookup"><span data-stu-id="b6c6a-153">This parameter accepts the path to the folder that contains the module.</span></span>

```yaml
Type: System.String
Parameter Sets: ModulePathParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="b6c6a-154">-Projecturi</span><span class="sxs-lookup"><span data-stu-id="b6c6a-154">-ProjectUri</span></span>

<span data-ttu-id="b6c6a-155">Gibt die URL einer Webseite zu diesem Projekt an.</span><span class="sxs-lookup"><span data-stu-id="b6c6a-155">Specifies the URL of a webpage about this project.</span></span>

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

### <span data-ttu-id="b6c6a-156">-Releasenotes</span><span class="sxs-lookup"><span data-stu-id="b6c6a-156">-ReleaseNotes</span></span>

<span data-ttu-id="b6c6a-157">Gibt eine Zeichenfolge mit Anmerkungen zu dieser Version oder Kommentaren an, die für Benutzer dieser Version des Moduls verfügbar sein sollen.</span><span class="sxs-lookup"><span data-stu-id="b6c6a-157">Specifies a string containing release notes or comments that you want to be available to users of this version of the module.</span></span>

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

### <span data-ttu-id="b6c6a-158">-Repository</span><span class="sxs-lookup"><span data-stu-id="b6c6a-158">-Repository</span></span>

<span data-ttu-id="b6c6a-159">Gibt den anzeigen Amen eines Repository an, das durch Ausführen von registriert wurde `Register-PSRepository` .</span><span class="sxs-lookup"><span data-stu-id="b6c6a-159">Specifies the friendly name of a repository that has been registered by running `Register-PSRepository`.</span></span> <span data-ttu-id="b6c6a-160">Das Repository muss über einen **publishlocation** verfügen, bei dem es sich um einen gültigen nuget-URI handelt.</span><span class="sxs-lookup"><span data-stu-id="b6c6a-160">The repository must have a **PublishLocation**, which is a valid NuGet URI.</span></span>
<span data-ttu-id="b6c6a-161">**Publishlocation** kann durch Ausführen von festgelegt werden `Set-PSRepository` .</span><span class="sxs-lookup"><span data-stu-id="b6c6a-161">The **PublishLocation** can be set by running `Set-PSRepository`.</span></span>

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

### <span data-ttu-id="b6c6a-162">-Requirements dversion</span><span class="sxs-lookup"><span data-stu-id="b6c6a-162">-RequiredVersion</span></span>

<span data-ttu-id="b6c6a-163">Gibt die exakte Version eines einzelnen zu veröffentlichenden Moduls an.</span><span class="sxs-lookup"><span data-stu-id="b6c6a-163">Specifies the exact version of a single module to publish.</span></span>

```yaml
Type: System.String
Parameter Sets: ModuleNameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b6c6a-164">-Skipautomatictags</span><span class="sxs-lookup"><span data-stu-id="b6c6a-164">-SkipAutomaticTags</span></span>

<span data-ttu-id="b6c6a-165">Entfernt das Einschließen von Befehlen und Ressourcen als Tags.</span><span class="sxs-lookup"><span data-stu-id="b6c6a-165">Removes commands and resources from being included as tags.</span></span> <span data-ttu-id="b6c6a-166">Überspringt das automatische Hinzufügen von Tags zu einem Modul.</span><span class="sxs-lookup"><span data-stu-id="b6c6a-166">Skips automatically adding tags to a module.</span></span>

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

### <span data-ttu-id="b6c6a-167">-Tags</span><span class="sxs-lookup"><span data-stu-id="b6c6a-167">-Tags</span></span>

<span data-ttu-id="b6c6a-168">Fügt dem Modul, das Sie veröffentlichen, ein oder mehrere Tags hinzu.</span><span class="sxs-lookup"><span data-stu-id="b6c6a-168">Adds one or more tags to the module that you are publishing.</span></span> <span data-ttu-id="b6c6a-169">Beispiele hierfür sind "desiredStatus econfiguration", "DSC", "dscresourcekit" oder "psmodule".</span><span class="sxs-lookup"><span data-stu-id="b6c6a-169">Example tags include DesiredStateConfiguration, DSC, DSCResourceKit, or PSModule.</span></span> <span data-ttu-id="b6c6a-170">Trennen Sie mehrere Tags durch Kommas.</span><span class="sxs-lookup"><span data-stu-id="b6c6a-170">Separate multiple tags with commas.</span></span>

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

### <span data-ttu-id="b6c6a-171">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="b6c6a-171">-WhatIf</span></span>

<span data-ttu-id="b6c6a-172">Zeigt, was geschieht, wenn die ausgeführt wird `Publish-Module` .</span><span class="sxs-lookup"><span data-stu-id="b6c6a-172">Shows what would happen if the `Publish-Module` runs.</span></span> <span data-ttu-id="b6c6a-173">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="b6c6a-173">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="b6c6a-174">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="b6c6a-174">CommonParameters</span></span>

<span data-ttu-id="b6c6a-175">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="b6c6a-175">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b6c6a-176">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="b6c6a-176">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b6c6a-177">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="b6c6a-177">INPUTS</span></span>

### <span data-ttu-id="b6c6a-178">System.String</span><span class="sxs-lookup"><span data-stu-id="b6c6a-178">System.String</span></span>

### <span data-ttu-id="b6c6a-179">System. Management. Automation. PSCredential</span><span class="sxs-lookup"><span data-stu-id="b6c6a-179">System.Management.Automation.PSCredential</span></span>

## <span data-ttu-id="b6c6a-180">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="b6c6a-180">OUTPUTS</span></span>

### <span data-ttu-id="b6c6a-181">System.Object</span><span class="sxs-lookup"><span data-stu-id="b6c6a-181">System.Object</span></span>

## <span data-ttu-id="b6c6a-182">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="b6c6a-182">NOTES</span></span>

<span data-ttu-id="b6c6a-183">`Publish-Module` wird in PowerShell 3,0 oder höheren Versionen von PowerShell unter Windows 7 oder Windows 2008 R2 und höheren Versionen von Windows ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="b6c6a-183">`Publish-Module` runs on PowerShell 3.0 or later releases of PowerShell, on Windows 7 or Windows 2008 R2 and later releases of Windows.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b6c6a-184">Ab April 2020 unterstützt der PowerShell-Katalog die TLS-Versionen (Transport Layer Security) 1.0 und 1.1 nicht mehr.</span><span class="sxs-lookup"><span data-stu-id="b6c6a-184">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="b6c6a-185">Wenn Sie nicht TLS 1.2 oder höher verwenden, erhalten Sie beim Versuch des Zugriffs auf den PowerShell-Katalog eine Fehlermeldung.</span><span class="sxs-lookup"><span data-stu-id="b6c6a-185">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="b6c6a-186">Mit dem folgenden Befehl können Sie sicherstellen, dass Sie TLS 1.2 verwenden:</span><span class="sxs-lookup"><span data-stu-id="b6c6a-186">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="b6c6a-187">Weitere Informationen finden Sie im PowerShell-Blog in der [Ankündigung](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/).</span><span class="sxs-lookup"><span data-stu-id="b6c6a-187">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

<span data-ttu-id="b6c6a-188">Die Veröffentlichung eines Moduls erfordert Metadaten, die auf der Seite „Katalog“ des Moduls angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="b6c6a-188">Publishing a module requires metadata that is displayed on the gallery page for the module.</span></span> <span data-ttu-id="b6c6a-189">Die erforderlichen Metadaten enthalten den Modulnamen, die Version, die Beschreibung und den Autor.</span><span class="sxs-lookup"><span data-stu-id="b6c6a-189">Required metadata includes the module name, version, description, and author.</span></span> <span data-ttu-id="b6c6a-190">Die meisten Metadaten werden aus dem Modul Manifest entnommen, aber einige Metadaten können in `Publish-Module` Parametern angegeben werden, wie z. b. **Tag**, **Releasenote**, **iconuri**, **projecturi** und **licentaruri**.</span><span class="sxs-lookup"><span data-stu-id="b6c6a-190">Most metadata is taken from the module manifest, but some metadata can be specified in `Publish-Module` parameters, such as **Tag**, **ReleaseNote**, **IconUri**, **ProjectUri**, and **LicenseUri**.</span></span> <span data-ttu-id="b6c6a-191">Weitere Informationen finden Sie unter [Paket Manifest-Werte, die Auswirkungen auf die PowerShell-Katalog-Benutzeroberfläche](/powershell/scripting/gallery/concepts/package-manifest-affecting-ui)haben.</span><span class="sxs-lookup"><span data-stu-id="b6c6a-191">For more information, see [Package manifest values that impact the PowerShell Gallery UI](/powershell/scripting/gallery/concepts/package-manifest-affecting-ui).</span></span>

## <span data-ttu-id="b6c6a-192">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="b6c6a-192">RELATED LINKS</span></span>

[<span data-ttu-id="b6c6a-193">Find-Module</span><span class="sxs-lookup"><span data-stu-id="b6c6a-193">Find-Module</span></span>](Find-Module.md)

[<span data-ttu-id="b6c6a-194">Install-Module</span><span class="sxs-lookup"><span data-stu-id="b6c6a-194">Install-Module</span></span>](Install-Module.md)

[<span data-ttu-id="b6c6a-195">Register-PSRepository</span><span class="sxs-lookup"><span data-stu-id="b6c6a-195">Register-PSRepository</span></span>](Register-PSRepository.md)

[<span data-ttu-id="b6c6a-196">Set-PSRepository</span><span class="sxs-lookup"><span data-stu-id="b6c6a-196">Set-PSRepository</span></span>](Set-PSRepository.md)

[<span data-ttu-id="b6c6a-197">Uninstall-Module</span><span class="sxs-lookup"><span data-stu-id="b6c6a-197">Uninstall-Module</span></span>](Uninstall-Module.md)

[<span data-ttu-id="b6c6a-198">Update-Module</span><span class="sxs-lookup"><span data-stu-id="b6c6a-198">Update-Module</span></span>](Update-Module.md)
