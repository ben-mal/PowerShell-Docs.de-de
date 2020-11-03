---
external help file: PSModule-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PowerShellGet
ms.date: 07/01/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/new-scriptfileinfo?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-ScriptFileInfo
ms.openlocfilehash: 649110ddb4147587dbff31d7b8410b706decca89
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215935"
---
# <span data-ttu-id="d0e93-103">New-ScriptFileInfo</span><span class="sxs-lookup"><span data-stu-id="d0e93-103">New-ScriptFileInfo</span></span>

## <span data-ttu-id="d0e93-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="d0e93-104">SYNOPSIS</span></span>
<span data-ttu-id="d0e93-105">Erstellt eine Skriptdatei mit Metadaten</span><span class="sxs-lookup"><span data-stu-id="d0e93-105">Creates a script file with metadata.</span></span>

## <span data-ttu-id="d0e93-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d0e93-106">SYNTAX</span></span>

### <span data-ttu-id="d0e93-107">Alle</span><span class="sxs-lookup"><span data-stu-id="d0e93-107">All</span></span>

```
New-ScriptFileInfo [[-Path] <String>] [-Version <String>] [-Author <String>] -Description <String>
 [-Guid <Guid>] [-CompanyName <String>] [-Copyright <String>] [-RequiredModules <Object[]>]
 [-ExternalModuleDependencies <String[]>] [-RequiredScripts <String[]>]
 [-ExternalScriptDependencies <String[]>] [-Tags <String[]>] [-ProjectUri <Uri>] [-LicenseUri <Uri>]
 [-IconUri <Uri>] [-ReleaseNotes <String[]>] [-PrivateData <String>] [-PassThru] [-Force] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="d0e93-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d0e93-108">DESCRIPTION</span></span>

<span data-ttu-id="d0e93-109">Das- `New-ScriptFileInfo` Cmdlet erstellt eine PowerShell-Skriptdatei, einschließlich Metadaten über das Skript.</span><span class="sxs-lookup"><span data-stu-id="d0e93-109">The `New-ScriptFileInfo` cmdlet creates a PowerShell script file, including metadata about the script.</span></span>

<span data-ttu-id="d0e93-110">In den Beispielen wird Verteilung verwendet, um Parameter an das `New-ScriptFileInfo` Cmdlet zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="d0e93-110">The examples use splatting to pass parameters to the `New-ScriptFileInfo` cmdlet.</span></span> <span data-ttu-id="d0e93-111">Weitere Informationen finden Sie unter [about_Splatting](../Microsoft.Powershell.Core/About/about_splatting.md).</span><span class="sxs-lookup"><span data-stu-id="d0e93-111">For more information, see [about_Splatting](../Microsoft.Powershell.Core/About/about_splatting.md).</span></span>

## <span data-ttu-id="d0e93-112">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="d0e93-112">EXAMPLES</span></span>

### <span data-ttu-id="d0e93-113">Beispiel 1: Erstellen einer Skriptdatei und angeben der zugehörigen Version, des Autors und der Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d0e93-113">Example 1: Create a script file and specify its version, author, and description</span></span>

<span data-ttu-id="d0e93-114">In diesem Beispiel wird eine Skriptdatei erstellt, und ihre Inhalte werden in der PowerShell-Konsole angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d0e93-114">In this example, a script file is created and its contents are displayed in the PowerShell console.</span></span>

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

<span data-ttu-id="d0e93-115">Das `New-ScriptFileInfo` Cmdlet verwendet Verteilung, um mehrere Parameter für das Skript zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="d0e93-115">The `New-ScriptFileInfo` cmdlet uses splatting to configure several parameters for the script.</span></span>
<span data-ttu-id="d0e93-116">**Path** legt den Speicherort und den Namen des Skripts fest.</span><span class="sxs-lookup"><span data-stu-id="d0e93-116">**Path** sets the location and name of the script.</span></span> <span data-ttu-id="d0e93-117">**Version** gibt die Versionsnummer des Skripts an.</span><span class="sxs-lookup"><span data-stu-id="d0e93-117">**Version** specifies the script's version number.</span></span> <span data-ttu-id="d0e93-118">**Author** ist die e-Mail-Adresse der Person, die das Skript erstellt hat.</span><span class="sxs-lookup"><span data-stu-id="d0e93-118">**Author** is the email address of the person who created the script.</span></span> <span data-ttu-id="d0e93-119">**Beschreibung** erläutert den Zweck des Skripts.</span><span class="sxs-lookup"><span data-stu-id="d0e93-119">**Description** explains the script's purpose.</span></span>

<span data-ttu-id="d0e93-120">Nachdem das Skript erstellt wurde, `Get-Content` verwendet den **path** -Parameter, um das Skript zu suchen.</span><span class="sxs-lookup"><span data-stu-id="d0e93-120">After the script is created, `Get-Content` uses the **Path** parameter to locate the script.</span></span> <span data-ttu-id="d0e93-121">Der Inhalt des Skripts wird in der PowerShell-Konsole angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d0e93-121">The script's contents are displayed in the PowerShell console.</span></span>

### <span data-ttu-id="d0e93-122">Beispiel 2: Testen einer Skriptdatei</span><span class="sxs-lookup"><span data-stu-id="d0e93-122">Example 2: Test a script file</span></span>

<span data-ttu-id="d0e93-123">In diesem Beispiel werden die Metadaten für das Skript getestet, das in **Beispiel 1** erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="d0e93-123">In this example, the metadata for the script created in **Example 1** is tested.</span></span>

```powershell
Test-ScriptFileInfo -Path C:\Test\Temp-Scriptfile.ps1
```

```Output
Version   Name                  Author               Description
-------   ----                  ------               -----------
1.0       Temp-Scriptfile       pattif@contoso.com   My test script file description goes here
```

<span data-ttu-id="d0e93-124">Das `Test-ScriptFileInfo` Cmdlet verwendet den **path** -Parameter, um den Speicherort der Skriptdatei anzugeben.</span><span class="sxs-lookup"><span data-stu-id="d0e93-124">The `Test-ScriptFileInfo` cmdlet uses the **Path** parameter to specify the script file's location.</span></span>

### <span data-ttu-id="d0e93-125">Beispiel 3: Erstellen einer Skriptdatei mit allen Metadateneigenschaften</span><span class="sxs-lookup"><span data-stu-id="d0e93-125">Example 3: Create a script file with all the metadata properties</span></span>

<span data-ttu-id="d0e93-126">In diesem Beispiel wird Verteilung verwendet, um eine Skriptdatei mit dem Namen zu erstellen `New-ScriptFile.ps1` , die alle zugehörigen Metadateneigenschaften enthält.</span><span class="sxs-lookup"><span data-stu-id="d0e93-126">This example uses splatting to create a script file named `New-ScriptFile.ps1` that includes all its metadata properties.</span></span> <span data-ttu-id="d0e93-127">Der **ausführliche** -Parameter gibt an, dass die ausführliche Ausgabe beim Erstellen des Skripts angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="d0e93-127">The **Verbose** parameter specifies that verbose output is displayed as the script is created.</span></span>

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

## <span data-ttu-id="d0e93-128">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d0e93-128">PARAMETERS</span></span>

### <span data-ttu-id="d0e93-129">-Autor</span><span class="sxs-lookup"><span data-stu-id="d0e93-129">-Author</span></span>

<span data-ttu-id="d0e93-130">Gibt den Autor des Skripts an.</span><span class="sxs-lookup"><span data-stu-id="d0e93-130">Specifies the script author.</span></span>

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

### <span data-ttu-id="d0e93-131">-CompanyName</span><span class="sxs-lookup"><span data-stu-id="d0e93-131">-CompanyName</span></span>

<span data-ttu-id="d0e93-132">Gibt das Unternehmen oder den Hersteller an, das das Skript erstellt hat.</span><span class="sxs-lookup"><span data-stu-id="d0e93-132">Specifies the company or vendor who created the script.</span></span>

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

### <span data-ttu-id="d0e93-133">-Confirm</span><span class="sxs-lookup"><span data-stu-id="d0e93-133">-Confirm</span></span>

<span data-ttu-id="d0e93-134">Fordert Sie zur Bestätigung auf, bevor Sie den ausführen `New-ScriptFileInfo` .</span><span class="sxs-lookup"><span data-stu-id="d0e93-134">Prompts you for confirmation before running the `New-ScriptFileInfo`.</span></span>

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

### <span data-ttu-id="d0e93-135">-Copyright</span><span class="sxs-lookup"><span data-stu-id="d0e93-135">-Copyright</span></span>

<span data-ttu-id="d0e93-136">Gibt eine Copyright Anweisung für das Skript an.</span><span class="sxs-lookup"><span data-stu-id="d0e93-136">Specifies a copyright statement for the script.</span></span>

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

### <span data-ttu-id="d0e93-137">-Description</span><span class="sxs-lookup"><span data-stu-id="d0e93-137">-Description</span></span>

<span data-ttu-id="d0e93-138">Gibt eine Beschreibung für das Skript an.</span><span class="sxs-lookup"><span data-stu-id="d0e93-138">Specifies a description for the script.</span></span>

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

### <span data-ttu-id="d0e93-139">-Externalmoduledependen</span><span class="sxs-lookup"><span data-stu-id="d0e93-139">-ExternalModuleDependencies</span></span>

<span data-ttu-id="d0e93-140">Gibt ein Array externer Modul Abhängigkeiten an.</span><span class="sxs-lookup"><span data-stu-id="d0e93-140">Specifies an array of external module dependencies.</span></span>

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

### <span data-ttu-id="d0e93-141">-Externalscriptdependen</span><span class="sxs-lookup"><span data-stu-id="d0e93-141">-ExternalScriptDependencies</span></span>

<span data-ttu-id="d0e93-142">Gibt ein Array externer Skript Abhängigkeiten an.</span><span class="sxs-lookup"><span data-stu-id="d0e93-142">Specifies an array of external script dependencies.</span></span>

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

### <span data-ttu-id="d0e93-143">-Force</span><span class="sxs-lookup"><span data-stu-id="d0e93-143">-Force</span></span>

<span data-ttu-id="d0e93-144">Erzwingt die Ausführung des Befehls ohne Aufforderung zur Bestätigung durch den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="d0e93-144">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="d0e93-145">-GUID</span><span class="sxs-lookup"><span data-stu-id="d0e93-145">-Guid</span></span>

<span data-ttu-id="d0e93-146">Gibt eine eindeutige ID für das Skript an.</span><span class="sxs-lookup"><span data-stu-id="d0e93-146">Specifies a unique ID for the script.</span></span>

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

### <span data-ttu-id="d0e93-147">-Iconuri</span><span class="sxs-lookup"><span data-stu-id="d0e93-147">-IconUri</span></span>

<span data-ttu-id="d0e93-148">Gibt die URL eines Symbols für das Skript an.</span><span class="sxs-lookup"><span data-stu-id="d0e93-148">Specifies the URL of an icon for the script.</span></span> <span data-ttu-id="d0e93-149">Das angegebene Symbol wird auf der Katalog Webseite für das Skript angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d0e93-149">The specified icon is displayed on the gallery web page for the script.</span></span>

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

### <span data-ttu-id="d0e93-150">-Licenaburi</span><span class="sxs-lookup"><span data-stu-id="d0e93-150">-LicenseUri</span></span>

<span data-ttu-id="d0e93-151">Gibt die URL der Lizenzbedingungen an.</span><span class="sxs-lookup"><span data-stu-id="d0e93-151">Specifies the URL of licensing terms.</span></span>

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

### <span data-ttu-id="d0e93-152">-PassThru</span><span class="sxs-lookup"><span data-stu-id="d0e93-152">-PassThru</span></span>

<span data-ttu-id="d0e93-153">Gibt ein-Objekt zurück, das das Element darstellt, mit dem Sie arbeiten.</span><span class="sxs-lookup"><span data-stu-id="d0e93-153">Returns an object that represents the item with which you're working.</span></span> <span data-ttu-id="d0e93-154">Standardmäßig `New-ScriptFileInfo` generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="d0e93-154">By default, `New-ScriptFileInfo` doesn't generate any output.</span></span>

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

### <span data-ttu-id="d0e93-155">-Path</span><span class="sxs-lookup"><span data-stu-id="d0e93-155">-Path</span></span>

<span data-ttu-id="d0e93-156">Gibt den Speicherort an, an dem die Skriptdatei gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="d0e93-156">Specifies the location where the script file is saved.</span></span>

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

### <span data-ttu-id="d0e93-157">-PRIVATEDATA</span><span class="sxs-lookup"><span data-stu-id="d0e93-157">-PrivateData</span></span>

<span data-ttu-id="d0e93-158">Gibt private Daten für das Skript an.</span><span class="sxs-lookup"><span data-stu-id="d0e93-158">Specifies private data for the script.</span></span>

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

### <span data-ttu-id="d0e93-159">-Projecturi</span><span class="sxs-lookup"><span data-stu-id="d0e93-159">-ProjectUri</span></span>

<span data-ttu-id="d0e93-160">Gibt die URL einer Webseite zu diesem Projekt an.</span><span class="sxs-lookup"><span data-stu-id="d0e93-160">Specifies the URL of a web page about this project.</span></span>

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

### <span data-ttu-id="d0e93-161">-Releasenotes</span><span class="sxs-lookup"><span data-stu-id="d0e93-161">-ReleaseNotes</span></span>

<span data-ttu-id="d0e93-162">Gibt ein Zeichen folgen Array an, das Anmerkungen oder Kommentare enthält, die für Benutzer dieser Skript Version verfügbar sein sollen.</span><span class="sxs-lookup"><span data-stu-id="d0e93-162">Specifies a string array that contains release notes or comments that you want available to users of this version of the script.</span></span>

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

### <span data-ttu-id="d0e93-163">-Requirements dmodules</span><span class="sxs-lookup"><span data-stu-id="d0e93-163">-RequiredModules</span></span>

<span data-ttu-id="d0e93-164">Gibt die Module an, die im globalen Sitzungsstatus enthalten sein müssen.</span><span class="sxs-lookup"><span data-stu-id="d0e93-164">Specifies modules that must be in the global session state.</span></span> <span data-ttu-id="d0e93-165">Wenn sich die erforderlichen Module nicht im globalen Sitzungs Status befinden, importiert PowerShell Sie.</span><span class="sxs-lookup"><span data-stu-id="d0e93-165">If the required modules aren't in the global session state, PowerShell imports them.</span></span>

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

### <span data-ttu-id="d0e93-166">-Requirements dscripts</span><span class="sxs-lookup"><span data-stu-id="d0e93-166">-RequiredScripts</span></span>

<span data-ttu-id="d0e93-167">Gibt ein Array von erforderlichen Skripts an.</span><span class="sxs-lookup"><span data-stu-id="d0e93-167">Specifies an array of required scripts.</span></span>

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

### <span data-ttu-id="d0e93-168">-Tags</span><span class="sxs-lookup"><span data-stu-id="d0e93-168">-Tags</span></span>

<span data-ttu-id="d0e93-169">Gibt ein Array von-Tags an.</span><span class="sxs-lookup"><span data-stu-id="d0e93-169">Specifies an array of tags.</span></span>

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

### <span data-ttu-id="d0e93-170">-Version</span><span class="sxs-lookup"><span data-stu-id="d0e93-170">-Version</span></span>

<span data-ttu-id="d0e93-171">Gibt die Version des Skripts an.</span><span class="sxs-lookup"><span data-stu-id="d0e93-171">Specifies the version of the script.</span></span>

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

### <span data-ttu-id="d0e93-172">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="d0e93-172">-WhatIf</span></span>

<span data-ttu-id="d0e93-173">Zeigt, was geschieht, wenn ausgeführt wird `New-ScriptFileInfo` .</span><span class="sxs-lookup"><span data-stu-id="d0e93-173">Shows what would happen if `New-ScriptFileInfo` runs.</span></span> <span data-ttu-id="d0e93-174">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="d0e93-174">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="d0e93-175">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="d0e93-175">CommonParameters</span></span>

<span data-ttu-id="d0e93-176">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="d0e93-176">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="d0e93-177">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="d0e93-177">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="d0e93-178">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="d0e93-178">INPUTS</span></span>

### <span data-ttu-id="d0e93-179">System.String</span><span class="sxs-lookup"><span data-stu-id="d0e93-179">System.String</span></span>

## <span data-ttu-id="d0e93-180">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="d0e93-180">OUTPUTS</span></span>

### <span data-ttu-id="d0e93-181">System.Object</span><span class="sxs-lookup"><span data-stu-id="d0e93-181">System.Object</span></span>

## <span data-ttu-id="d0e93-182">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="d0e93-182">NOTES</span></span>

## <span data-ttu-id="d0e93-183">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="d0e93-183">RELATED LINKS</span></span>

[<span data-ttu-id="d0e93-184">about_Splatting</span><span class="sxs-lookup"><span data-stu-id="d0e93-184">about_Splatting</span></span>](../Microsoft.Powershell.Core/About/about_splatting.md)

[<span data-ttu-id="d0e93-185">Test-ScriptFileInfo</span><span class="sxs-lookup"><span data-stu-id="d0e93-185">Test-ScriptFileInfo</span></span>](Test-ScriptFileInfo.md)

[<span data-ttu-id="d0e93-186">Update-ScriptFileInfo</span><span class="sxs-lookup"><span data-stu-id="d0e93-186">Update-ScriptFileInfo</span></span>](Update-ScriptFileInfo.md)
