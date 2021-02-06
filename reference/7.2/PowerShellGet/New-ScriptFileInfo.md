---
external help file: PSModule-help.xml
Locale: en-US
Module Name: PowerShellGet
ms.date: 07/01/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/new-scriptfileinfo?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-ScriptFileInfo
ms.openlocfilehash: d3e3c0ec257bd9c405accaf3051abd1ae4501f0f
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99604858"
---
# <span data-ttu-id="4aac2-102">New-ScriptFileInfo</span><span class="sxs-lookup"><span data-stu-id="4aac2-102">New-ScriptFileInfo</span></span>

## <span data-ttu-id="4aac2-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="4aac2-103">SYNOPSIS</span></span>
<span data-ttu-id="4aac2-104">Erstellt eine Skriptdatei mit Metadaten</span><span class="sxs-lookup"><span data-stu-id="4aac2-104">Creates a script file with metadata.</span></span>

## <span data-ttu-id="4aac2-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="4aac2-105">SYNTAX</span></span>

### <span data-ttu-id="4aac2-106">Alle</span><span class="sxs-lookup"><span data-stu-id="4aac2-106">All</span></span>

```
New-ScriptFileInfo [[-Path] <String>] [-Version <String>] [-Author <String>] -Description <String>
 [-Guid <Guid>] [-CompanyName <String>] [-Copyright <String>] [-RequiredModules <Object[]>]
 [-ExternalModuleDependencies <String[]>] [-RequiredScripts <String[]>]
 [-ExternalScriptDependencies <String[]>] [-Tags <String[]>] [-ProjectUri <Uri>] [-LicenseUri <Uri>]
 [-IconUri <Uri>] [-ReleaseNotes <String[]>] [-PrivateData <String>] [-PassThru] [-Force] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="4aac2-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="4aac2-107">DESCRIPTION</span></span>

<span data-ttu-id="4aac2-108">Das- `New-ScriptFileInfo` Cmdlet erstellt eine PowerShell-Skriptdatei, einschließlich Metadaten über das Skript.</span><span class="sxs-lookup"><span data-stu-id="4aac2-108">The `New-ScriptFileInfo` cmdlet creates a PowerShell script file, including metadata about the script.</span></span>

<span data-ttu-id="4aac2-109">In den Beispielen wird Verteilung verwendet, um Parameter an das `New-ScriptFileInfo` Cmdlet zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="4aac2-109">The examples use splatting to pass parameters to the `New-ScriptFileInfo` cmdlet.</span></span> <span data-ttu-id="4aac2-110">Weitere Informationen finden Sie unter [about_Splatting](../Microsoft.Powershell.Core/About/about_splatting.md).</span><span class="sxs-lookup"><span data-stu-id="4aac2-110">For more information, see [about_Splatting](../Microsoft.Powershell.Core/About/about_splatting.md).</span></span>

## <span data-ttu-id="4aac2-111">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="4aac2-111">EXAMPLES</span></span>

### <span data-ttu-id="4aac2-112">Beispiel 1: Erstellen einer Skriptdatei und angeben der zugehörigen Version, des Autors und der Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4aac2-112">Example 1: Create a script file and specify its version, author, and description</span></span>

<span data-ttu-id="4aac2-113">In diesem Beispiel wird eine Skriptdatei erstellt, und ihre Inhalte werden in der PowerShell-Konsole angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4aac2-113">In this example, a script file is created and its contents are displayed in the PowerShell console.</span></span>

```powershell
$Parms = @{
  Path = "C:\Test\Temp-Scriptfile.ps1"
  Version = "1.0"
  Author = "pattif@contoso.com"
  Description = "My test script file description goes here"
  }
New-ScriptFileInfo @Parms
Get-Content -Path C:\Test\Temp-Scriptfile.ps1
```

```Output
<#PSScriptInfo

.VERSION 1.0

.GUID 3bb10ee7-38c1-41b9-88ea-16899164fc19

.AUTHOR pattif@contoso.com

.COMPANYNAME

.COPYRIGHT

.TAGS

.LICENSEURI

.PROJECTURI

.ICONURI

.EXTERNALMODULEDEPENDENCIES

.REQUIREDSCRIPTS

.EXTERNALSCRIPTDEPENDENCIES

.RELEASENOTES

.PRIVATEDATA

#>

<#

.DESCRIPTION
 My test script file description goes here

#>
Param()
```

<span data-ttu-id="4aac2-114">Das `New-ScriptFileInfo` Cmdlet verwendet Verteilung, um mehrere Parameter für das Skript zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="4aac2-114">The `New-ScriptFileInfo` cmdlet uses splatting to configure several parameters for the script.</span></span>
<span data-ttu-id="4aac2-115">**Path** legt den Speicherort und den Namen des Skripts fest.</span><span class="sxs-lookup"><span data-stu-id="4aac2-115">**Path** sets the location and name of the script.</span></span> <span data-ttu-id="4aac2-116">**Version** gibt die Versionsnummer des Skripts an.</span><span class="sxs-lookup"><span data-stu-id="4aac2-116">**Version** specifies the script's version number.</span></span> <span data-ttu-id="4aac2-117">**Author** ist die e-Mail-Adresse der Person, die das Skript erstellt hat.</span><span class="sxs-lookup"><span data-stu-id="4aac2-117">**Author** is the email address of the person who created the script.</span></span> <span data-ttu-id="4aac2-118">**Beschreibung** erläutert den Zweck des Skripts.</span><span class="sxs-lookup"><span data-stu-id="4aac2-118">**Description** explains the script's purpose.</span></span>

<span data-ttu-id="4aac2-119">Nachdem das Skript erstellt wurde, `Get-Content` verwendet den **path** -Parameter, um das Skript zu suchen.</span><span class="sxs-lookup"><span data-stu-id="4aac2-119">After the script is created, `Get-Content` uses the **Path** parameter to locate the script.</span></span> <span data-ttu-id="4aac2-120">Der Inhalt des Skripts wird in der PowerShell-Konsole angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4aac2-120">The script's contents are displayed in the PowerShell console.</span></span>

### <span data-ttu-id="4aac2-121">Beispiel 2: Testen einer Skriptdatei</span><span class="sxs-lookup"><span data-stu-id="4aac2-121">Example 2: Test a script file</span></span>

<span data-ttu-id="4aac2-122">In diesem Beispiel werden die Metadaten für das Skript getestet, das in **Beispiel 1** erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="4aac2-122">In this example, the metadata for the script created in **Example 1** is tested.</span></span>

```powershell
Test-ScriptFileInfo -Path C:\Test\Temp-Scriptfile.ps1
```

```Output
Version   Name                  Author               Description
-------   ----                  ------               -----------
1.0       Temp-Scriptfile       pattif@contoso.com   My test script file description goes here
```

<span data-ttu-id="4aac2-123">Das `Test-ScriptFileInfo` Cmdlet verwendet den **path** -Parameter, um den Speicherort der Skriptdatei anzugeben.</span><span class="sxs-lookup"><span data-stu-id="4aac2-123">The `Test-ScriptFileInfo` cmdlet uses the **Path** parameter to specify the script file's location.</span></span>

### <span data-ttu-id="4aac2-124">Beispiel 3: Erstellen einer Skriptdatei mit allen Metadateneigenschaften</span><span class="sxs-lookup"><span data-stu-id="4aac2-124">Example 3: Create a script file with all the metadata properties</span></span>

<span data-ttu-id="4aac2-125">In diesem Beispiel wird Verteilung verwendet, um eine Skriptdatei mit dem Namen zu erstellen `New-ScriptFile.ps1` , die alle zugehörigen Metadateneigenschaften enthält.</span><span class="sxs-lookup"><span data-stu-id="4aac2-125">This example uses splatting to create a script file named `New-ScriptFile.ps1` that includes all its metadata properties.</span></span> <span data-ttu-id="4aac2-126">Der **ausführliche** -Parameter gibt an, dass die ausführliche Ausgabe beim Erstellen des Skripts angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="4aac2-126">The **Verbose** parameter specifies that verbose output is displayed as the script is created.</span></span>

```powershell
$Parms = @{
 Path = "C:\Test\New-ScriptFile.ps1"
 Verbose = $True
 Version = "1.0"
 Author = "pattif@contoso.com"
 Description = "My new script file test"
 CompanyName = "Contoso Corporation"
 Copyright = "2019 Contoso Corporation. All rights reserved."
 ExternalModuleDependencies = "ff","bb"
 RequiredScripts = "Start-WFContosoServer", "Stop-ContosoServerScript"
 ExternalScriptDependencies = "Stop-ContosoServerScript"
 Tags = @("Tag1", "Tag2", "Tag3")
 ProjectUri = "https://contoso.com"
 LicenseUri = "https://contoso.com/License"
 IconUri = "https://contoso.com/Icon"
 PassThru = $True
 ReleaseNotes = @("Contoso script now supports the following features:",
   "Feature 1",
   "Feature 2",
   "Feature 3",
   "Feature 4",
   "Feature 5")
 RequiredModules =
   "1",
   "2",
   "RequiredModule1",
   @{ModuleName="RequiredModule2";ModuleVersion="1.0"},
   @{ModuleName="RequiredModule3";RequiredVersion="2.0"},
   "ExternalModule1"
 }
New-ScriptFileInfo @Parms
```

```Output
VERBOSE: Performing the operation "Creating the 'C:\Test\New-ScriptFile.ps1'
  PowerShell Script file" on target "C:\Test\New-ScriptFile.ps1".

<#PSScriptInfo

.VERSION 1.0

.GUID 4fabe8c7-7862-45b1-a72e-1352a433b77d

.AUTHOR pattif@contoso.com

.COMPANYNAME Contoso Corporation

.COPYRIGHT 2019 Contoso Corporation. All rights reserved.

.TAGS Tag1 Tag2 Tag3

.LICENSEURI https://contoso.com/License

.PROJECTURI https://contoso.com/

.ICONURI https://contoso.com/Icon

.EXTERNALMODULEDEPENDENCIES ff,bb

.REQUIREDSCRIPTS Start-WFContosoServer,Stop-ContosoServerScript

.EXTERNALSCRIPTDEPENDENCIES Stop-ContosoServerScript

.RELEASENOTES
Contoso script now supports the following features:
Feature 1
Feature 2
Feature 3
Feature 4
Feature 5

.PRIVATEDATA

#>

#Requires -Module 1
#Requires -Module 2
#Requires -Module RequiredModule1
#Requires -Module @{ModuleName = 'RequiredModule2'; ModuleVersion = '1.0'}
#Requires -Module @{RequiredVersion = '2.0'; ModuleName = 'RequiredModule3'}
#Requires -Module ExternalModule1

<#

.DESCRIPTION
 My new script file test

#>
Param()
```

## <span data-ttu-id="4aac2-127">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="4aac2-127">PARAMETERS</span></span>

### <span data-ttu-id="4aac2-128">-Autor</span><span class="sxs-lookup"><span data-stu-id="4aac2-128">-Author</span></span>

<span data-ttu-id="4aac2-129">Gibt den Autor des Skripts an.</span><span class="sxs-lookup"><span data-stu-id="4aac2-129">Specifies the script author.</span></span>

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

### <span data-ttu-id="4aac2-130">-CompanyName</span><span class="sxs-lookup"><span data-stu-id="4aac2-130">-CompanyName</span></span>

<span data-ttu-id="4aac2-131">Gibt das Unternehmen oder den Hersteller an, das das Skript erstellt hat.</span><span class="sxs-lookup"><span data-stu-id="4aac2-131">Specifies the company or vendor who created the script.</span></span>

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

### <span data-ttu-id="4aac2-132">-Confirm</span><span class="sxs-lookup"><span data-stu-id="4aac2-132">-Confirm</span></span>

<span data-ttu-id="4aac2-133">Fordert Sie zur Bestätigung auf, bevor Sie den ausführen `New-ScriptFileInfo` .</span><span class="sxs-lookup"><span data-stu-id="4aac2-133">Prompts you for confirmation before running the `New-ScriptFileInfo`.</span></span>

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

### <span data-ttu-id="4aac2-134">-Copyright</span><span class="sxs-lookup"><span data-stu-id="4aac2-134">-Copyright</span></span>

<span data-ttu-id="4aac2-135">Gibt eine Copyright Anweisung für das Skript an.</span><span class="sxs-lookup"><span data-stu-id="4aac2-135">Specifies a copyright statement for the script.</span></span>

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

### <span data-ttu-id="4aac2-136">-Description</span><span class="sxs-lookup"><span data-stu-id="4aac2-136">-Description</span></span>

<span data-ttu-id="4aac2-137">Gibt eine Beschreibung für das Skript an.</span><span class="sxs-lookup"><span data-stu-id="4aac2-137">Specifies a description for the script.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4aac2-138">-Externalmoduledependen</span><span class="sxs-lookup"><span data-stu-id="4aac2-138">-ExternalModuleDependencies</span></span>

<span data-ttu-id="4aac2-139">Gibt ein Array externer Modul Abhängigkeiten an.</span><span class="sxs-lookup"><span data-stu-id="4aac2-139">Specifies an array of external module dependencies.</span></span>

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

### <span data-ttu-id="4aac2-140">-Externalscriptdependen</span><span class="sxs-lookup"><span data-stu-id="4aac2-140">-ExternalScriptDependencies</span></span>

<span data-ttu-id="4aac2-141">Gibt ein Array externer Skript Abhängigkeiten an.</span><span class="sxs-lookup"><span data-stu-id="4aac2-141">Specifies an array of external script dependencies.</span></span>

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

### <span data-ttu-id="4aac2-142">-Force</span><span class="sxs-lookup"><span data-stu-id="4aac2-142">-Force</span></span>

<span data-ttu-id="4aac2-143">Erzwingt die Ausführung des Befehls ohne Aufforderung zur Bestätigung durch den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="4aac2-143">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="4aac2-144">-GUID</span><span class="sxs-lookup"><span data-stu-id="4aac2-144">-Guid</span></span>

<span data-ttu-id="4aac2-145">Gibt eine eindeutige ID für das Skript an.</span><span class="sxs-lookup"><span data-stu-id="4aac2-145">Specifies a unique ID for the script.</span></span>

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

### <span data-ttu-id="4aac2-146">-Iconuri</span><span class="sxs-lookup"><span data-stu-id="4aac2-146">-IconUri</span></span>

<span data-ttu-id="4aac2-147">Gibt die URL eines Symbols für das Skript an.</span><span class="sxs-lookup"><span data-stu-id="4aac2-147">Specifies the URL of an icon for the script.</span></span> <span data-ttu-id="4aac2-148">Das angegebene Symbol wird auf der Katalog Webseite für das Skript angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4aac2-148">The specified icon is displayed on the gallery web page for the script.</span></span>

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

### <span data-ttu-id="4aac2-149">-Licenaburi</span><span class="sxs-lookup"><span data-stu-id="4aac2-149">-LicenseUri</span></span>

<span data-ttu-id="4aac2-150">Gibt die URL der Lizenzbedingungen an.</span><span class="sxs-lookup"><span data-stu-id="4aac2-150">Specifies the URL of licensing terms.</span></span>

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

### <span data-ttu-id="4aac2-151">-PassThru</span><span class="sxs-lookup"><span data-stu-id="4aac2-151">-PassThru</span></span>

<span data-ttu-id="4aac2-152">Gibt ein-Objekt zurück, das das Element darstellt, mit dem Sie arbeiten.</span><span class="sxs-lookup"><span data-stu-id="4aac2-152">Returns an object that represents the item with which you're working.</span></span> <span data-ttu-id="4aac2-153">Standardmäßig `New-ScriptFileInfo` generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="4aac2-153">By default, `New-ScriptFileInfo` doesn't generate any output.</span></span>

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

### <span data-ttu-id="4aac2-154">-Path</span><span class="sxs-lookup"><span data-stu-id="4aac2-154">-Path</span></span>

<span data-ttu-id="4aac2-155">Gibt den Speicherort an, an dem die Skriptdatei gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="4aac2-155">Specifies the location where the script file is saved.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="4aac2-156">-PRIVATEDATA</span><span class="sxs-lookup"><span data-stu-id="4aac2-156">-PrivateData</span></span>

<span data-ttu-id="4aac2-157">Gibt private Daten für das Skript an.</span><span class="sxs-lookup"><span data-stu-id="4aac2-157">Specifies private data for the script.</span></span>

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

### <span data-ttu-id="4aac2-158">-Projecturi</span><span class="sxs-lookup"><span data-stu-id="4aac2-158">-ProjectUri</span></span>

<span data-ttu-id="4aac2-159">Gibt die URL einer Webseite zu diesem Projekt an.</span><span class="sxs-lookup"><span data-stu-id="4aac2-159">Specifies the URL of a web page about this project.</span></span>

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

### <span data-ttu-id="4aac2-160">-Releasenotes</span><span class="sxs-lookup"><span data-stu-id="4aac2-160">-ReleaseNotes</span></span>

<span data-ttu-id="4aac2-161">Gibt ein Zeichen folgen Array an, das Anmerkungen oder Kommentare enthält, die für Benutzer dieser Skript Version verfügbar sein sollen.</span><span class="sxs-lookup"><span data-stu-id="4aac2-161">Specifies a string array that contains release notes or comments that you want available to users of this version of the script.</span></span>

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

### <span data-ttu-id="4aac2-162">-Requirements dmodules</span><span class="sxs-lookup"><span data-stu-id="4aac2-162">-RequiredModules</span></span>

<span data-ttu-id="4aac2-163">Gibt die Module an, die im globalen Sitzungsstatus enthalten sein müssen.</span><span class="sxs-lookup"><span data-stu-id="4aac2-163">Specifies modules that must be in the global session state.</span></span> <span data-ttu-id="4aac2-164">Wenn sich die erforderlichen Module nicht im globalen Sitzungs Status befinden, importiert PowerShell Sie.</span><span class="sxs-lookup"><span data-stu-id="4aac2-164">If the required modules aren't in the global session state, PowerShell imports them.</span></span>

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

### <span data-ttu-id="4aac2-165">-Requirements dscripts</span><span class="sxs-lookup"><span data-stu-id="4aac2-165">-RequiredScripts</span></span>

<span data-ttu-id="4aac2-166">Gibt ein Array von erforderlichen Skripts an.</span><span class="sxs-lookup"><span data-stu-id="4aac2-166">Specifies an array of required scripts.</span></span>

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

### <span data-ttu-id="4aac2-167">-Tags</span><span class="sxs-lookup"><span data-stu-id="4aac2-167">-Tags</span></span>

<span data-ttu-id="4aac2-168">Gibt ein Array von-Tags an.</span><span class="sxs-lookup"><span data-stu-id="4aac2-168">Specifies an array of tags.</span></span>

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

### <span data-ttu-id="4aac2-169">-Version</span><span class="sxs-lookup"><span data-stu-id="4aac2-169">-Version</span></span>

<span data-ttu-id="4aac2-170">Gibt die Version des Skripts an.</span><span class="sxs-lookup"><span data-stu-id="4aac2-170">Specifies the version of the script.</span></span>

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

### <span data-ttu-id="4aac2-171">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="4aac2-171">-WhatIf</span></span>

<span data-ttu-id="4aac2-172">Zeigt, was geschieht, wenn ausgeführt wird `New-ScriptFileInfo` .</span><span class="sxs-lookup"><span data-stu-id="4aac2-172">Shows what would happen if `New-ScriptFileInfo` runs.</span></span> <span data-ttu-id="4aac2-173">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="4aac2-173">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="4aac2-174">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="4aac2-174">CommonParameters</span></span>

<span data-ttu-id="4aac2-175">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="4aac2-175">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="4aac2-176">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="4aac2-176">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="4aac2-177">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="4aac2-177">INPUTS</span></span>

### <span data-ttu-id="4aac2-178">System.String</span><span class="sxs-lookup"><span data-stu-id="4aac2-178">System.String</span></span>

## <span data-ttu-id="4aac2-179">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="4aac2-179">OUTPUTS</span></span>

### <span data-ttu-id="4aac2-180">System.Object</span><span class="sxs-lookup"><span data-stu-id="4aac2-180">System.Object</span></span>

## <span data-ttu-id="4aac2-181">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="4aac2-181">NOTES</span></span>

## <span data-ttu-id="4aac2-182">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="4aac2-182">RELATED LINKS</span></span>

[<span data-ttu-id="4aac2-183">about_Splatting</span><span class="sxs-lookup"><span data-stu-id="4aac2-183">about_Splatting</span></span>](../Microsoft.Powershell.Core/About/about_splatting.md)

[<span data-ttu-id="4aac2-184">Test-ScriptFileInfo</span><span class="sxs-lookup"><span data-stu-id="4aac2-184">Test-ScriptFileInfo</span></span>](Test-ScriptFileInfo.md)

[<span data-ttu-id="4aac2-185">Update-ScriptFileInfo</span><span class="sxs-lookup"><span data-stu-id="4aac2-185">Update-ScriptFileInfo</span></span>](Update-ScriptFileInfo.md)

