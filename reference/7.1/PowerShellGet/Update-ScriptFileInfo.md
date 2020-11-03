---
external help file: PSModule-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PowerShellGet
ms.date: 07/09/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/update-scriptfileinfo?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Update-ScriptFileInfo
ms.openlocfilehash: 443186a63819809a42d953b60232c9745818fb4f
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93217324"
---
# <span data-ttu-id="6aa09-103">Update-ScriptFileInfo</span><span class="sxs-lookup"><span data-stu-id="6aa09-103">Update-ScriptFileInfo</span></span>

## <span data-ttu-id="6aa09-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="6aa09-104">SYNOPSIS</span></span>
<span data-ttu-id="6aa09-105">Aktualisiert Informationen für ein Skript.</span><span class="sxs-lookup"><span data-stu-id="6aa09-105">Updates information for a script.</span></span>

## <span data-ttu-id="6aa09-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="6aa09-106">SYNTAX</span></span>

### <span data-ttu-id="6aa09-107">Pathparameterset (Standard)</span><span class="sxs-lookup"><span data-stu-id="6aa09-107">PathParameterSet (Default)</span></span>

```
Update-ScriptFileInfo [-Path] <String> [-Version <String>] [-Author <String>] [-Guid <Guid>]
 [-Description <String>] [-CompanyName <String>] [-Copyright <String>] [-RequiredModules <Object[]>]
 [-ExternalModuleDependencies <String[]>] [-RequiredScripts <String[]>]
 [-ExternalScriptDependencies <String[]>] [-Tags <String[]>] [-ProjectUri <Uri>] [-LicenseUri <Uri>]
 [-IconUri <Uri>] [-ReleaseNotes <String[]>] [-PrivateData <String>] [-PassThru] [-Force] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="6aa09-108">Literalpathparameterset</span><span class="sxs-lookup"><span data-stu-id="6aa09-108">LiteralPathParameterSet</span></span>

```
Update-ScriptFileInfo [-LiteralPath] <String> [-Version <String>] [-Author <String>] [-Guid <Guid>]
 [-Description <String>] [-CompanyName <String>] [-Copyright <String>] [-RequiredModules <Object[]>]
 [-ExternalModuleDependencies <String[]>] [-RequiredScripts <String[]>]
 [-ExternalScriptDependencies <String[]>] [-Tags <String[]>] [-ProjectUri <Uri>] [-LicenseUri <Uri>]
 [-IconUri <Uri>] [-ReleaseNotes <String[]>] [-PrivateData <String>] [-PassThru] [-Force] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="6aa09-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="6aa09-109">DESCRIPTION</span></span>

<span data-ttu-id="6aa09-110">Mit dem `Update-ScriptFileInfo` -Cmdlet werden die Eigenschaftswerte eines Skripts aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="6aa09-110">The `Update-ScriptFileInfo` cmdlet updates a script's property values.</span></span> <span data-ttu-id="6aa09-111">Dies sind z. b. die Werte für Version, Autor oder Beschreibung.</span><span class="sxs-lookup"><span data-stu-id="6aa09-111">For example, the values for version, author, or description.</span></span>

## <span data-ttu-id="6aa09-112">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="6aa09-112">EXAMPLES</span></span>

### <span data-ttu-id="6aa09-113">Beispiel 1: Aktualisieren der Version einer Skriptdatei</span><span class="sxs-lookup"><span data-stu-id="6aa09-113">Example 1: Update the version of a script file</span></span>

<span data-ttu-id="6aa09-114">In diesem Beispiel wird eine vorhandene Skriptdatei mit neuen Eigenschafts Werten aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="6aa09-114">In this example, an existing script file is updated with new property values.</span></span>

<span data-ttu-id="6aa09-115">Splatting wird verwendet, um Parameter an das `Update-ScriptFileInfo` Cmdlet zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="6aa09-115">Splatting is used to pass parameters to the `Update-ScriptFileInfo` cmdlet.</span></span> <span data-ttu-id="6aa09-116">Weitere Informationen finden Sie unter [about_Splatting](../Microsoft.Powershell.Core/About/about_splatting.md).</span><span class="sxs-lookup"><span data-stu-id="6aa09-116">For more information, see [about_Splatting](../Microsoft.Powershell.Core/About/about_splatting.md).</span></span>

```powershell
$Parms = @{
  Path = "C:\Test\Temp-Scriptfile.ps1"
  Version = "2.0"
  Author = "bob@contoso.com"
  CompanyName = "Contoso"
  Description = "This is the updated description"
  }
Update-ScriptFileInfo @Parms -PassThru
```

```Output
<#PSScriptInfo

.VERSION 2.0

.GUID 4609f00c-e850-4d3f-9c69-3741e56e4133

.AUTHOR bob@contoso.com

.COMPANYNAME Contoso

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
This is the updated description

#>
Param()
```

<span data-ttu-id="6aa09-117">`$Parms` speichert die Parameterwerte für **path** , **Version** , **Author** , **CompanyName** und **Description**.</span><span class="sxs-lookup"><span data-stu-id="6aa09-117">`$Parms` stores the parameter values for **Path** , **Version** , **Author** , **CompanyName** , and **Description**.</span></span> <span data-ttu-id="6aa09-118">`Update-ScriptFileInfo` Ruft die Parameterwerte aus ab `@Parms` und aktualisiert das Skript.</span><span class="sxs-lookup"><span data-stu-id="6aa09-118">`Update-ScriptFileInfo` gets the parameter values from `@Parms` and updates the script.</span></span> <span data-ttu-id="6aa09-119">Der **passthru** -Parameter zeigt den Inhalt des Skripts in der PowerShell-Konsole an.</span><span class="sxs-lookup"><span data-stu-id="6aa09-119">The **PassThru** parameter displays the script's contents in the PowerShell console.</span></span>

## <span data-ttu-id="6aa09-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="6aa09-120">PARAMETERS</span></span>

### <span data-ttu-id="6aa09-121">-Autor</span><span class="sxs-lookup"><span data-stu-id="6aa09-121">-Author</span></span>

<span data-ttu-id="6aa09-122">Gibt den Autor des Skripts an.</span><span class="sxs-lookup"><span data-stu-id="6aa09-122">Specifies the script author.</span></span>

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

### <span data-ttu-id="6aa09-123">-CompanyName</span><span class="sxs-lookup"><span data-stu-id="6aa09-123">-CompanyName</span></span>

<span data-ttu-id="6aa09-124">Gibt das Unternehmen oder den Hersteller an, das das Skript erstellt hat.</span><span class="sxs-lookup"><span data-stu-id="6aa09-124">Specifies the company or vendor who created the script.</span></span>

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

### <span data-ttu-id="6aa09-125">-Confirm</span><span class="sxs-lookup"><span data-stu-id="6aa09-125">-Confirm</span></span>

<span data-ttu-id="6aa09-126">Sie werden zur Bestätigung aufgefordert, bevor Sie ausgeführt werden `Update-ScriptFileInfo` .</span><span class="sxs-lookup"><span data-stu-id="6aa09-126">Prompts you for confirmation before running `Update-ScriptFileInfo`.</span></span>

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

### <span data-ttu-id="6aa09-127">-Copyright</span><span class="sxs-lookup"><span data-stu-id="6aa09-127">-Copyright</span></span>

<span data-ttu-id="6aa09-128">Gibt eine Copyright Anweisung für das Skript an.</span><span class="sxs-lookup"><span data-stu-id="6aa09-128">Specifies a copyright statement for the script.</span></span>

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

### <span data-ttu-id="6aa09-129">-Description</span><span class="sxs-lookup"><span data-stu-id="6aa09-129">-Description</span></span>

<span data-ttu-id="6aa09-130">Gibt eine Beschreibung für das Skript an.</span><span class="sxs-lookup"><span data-stu-id="6aa09-130">Specifies a description for the script.</span></span>

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

### <span data-ttu-id="6aa09-131">-Externalmoduledependen</span><span class="sxs-lookup"><span data-stu-id="6aa09-131">-ExternalModuleDependencies</span></span>

<span data-ttu-id="6aa09-132">Gibt ein Array externer Modul Abhängigkeiten an.</span><span class="sxs-lookup"><span data-stu-id="6aa09-132">Specifies an array of external module dependencies.</span></span>

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

### <span data-ttu-id="6aa09-133">-Externalscriptdependen</span><span class="sxs-lookup"><span data-stu-id="6aa09-133">-ExternalScriptDependencies</span></span>

<span data-ttu-id="6aa09-134">Gibt ein Array externer Skript Abhängigkeiten an.</span><span class="sxs-lookup"><span data-stu-id="6aa09-134">Specifies an array of external script dependencies.</span></span>

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

### <span data-ttu-id="6aa09-135">-Force</span><span class="sxs-lookup"><span data-stu-id="6aa09-135">-Force</span></span>

<span data-ttu-id="6aa09-136">Erzwingt das `Update-ScriptFileInfo` Ausführen von, ohne dass eine Benutzer Bestätigung angefordert wird.</span><span class="sxs-lookup"><span data-stu-id="6aa09-136">Forces `Update-ScriptFileInfo` to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="6aa09-137">-GUID</span><span class="sxs-lookup"><span data-stu-id="6aa09-137">-Guid</span></span>

<span data-ttu-id="6aa09-138">Gibt eine eindeutige ID für ein Skript an.</span><span class="sxs-lookup"><span data-stu-id="6aa09-138">Specifies a unique ID for a script.</span></span>

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

### <span data-ttu-id="6aa09-139">-Iconuri</span><span class="sxs-lookup"><span data-stu-id="6aa09-139">-IconUri</span></span>

<span data-ttu-id="6aa09-140">Gibt die URL eines Symbols für das Skript an.</span><span class="sxs-lookup"><span data-stu-id="6aa09-140">Specifies the URL of an icon for the script.</span></span> <span data-ttu-id="6aa09-141">Das angegebene Symbol wird auf der Katalog Webseite für das Skript angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6aa09-141">The specified icon is displayed on the gallery web page for the script.</span></span>

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

### <span data-ttu-id="6aa09-142">-Licenaburi</span><span class="sxs-lookup"><span data-stu-id="6aa09-142">-LicenseUri</span></span>

<span data-ttu-id="6aa09-143">Gibt die URL der Lizenzbedingungen an.</span><span class="sxs-lookup"><span data-stu-id="6aa09-143">Specifies the URL of licensing terms.</span></span>

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

### <span data-ttu-id="6aa09-144">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="6aa09-144">-LiteralPath</span></span>

<span data-ttu-id="6aa09-145">Gibt einen Pfad zu einem oder mehreren Speicherorten an.</span><span class="sxs-lookup"><span data-stu-id="6aa09-145">Specifies a path to one or more locations.</span></span> <span data-ttu-id="6aa09-146">Der Wert des **literalpath** -Parameters wird genau so verwendet, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="6aa09-146">The **LiteralPath** parameter's value is used exactly as it's entered.</span></span> <span data-ttu-id="6aa09-147">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="6aa09-147">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="6aa09-148">Wenn der Pfad Escapezeichen enthält, schließen Sie Sie in einfache Anführungszeichen ein.</span><span class="sxs-lookup"><span data-stu-id="6aa09-148">If the path includes escape characters, enclose them in single quotation marks.</span></span> <span data-ttu-id="6aa09-149">Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="6aa09-149">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String
Parameter Sets: LiteralPathParameterSet
Aliases: PSPath

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="6aa09-150">-PassThru</span><span class="sxs-lookup"><span data-stu-id="6aa09-150">-PassThru</span></span>

<span data-ttu-id="6aa09-151">Gibt ein-Objekt zurück, das das Element darstellt, mit dem Sie arbeiten.</span><span class="sxs-lookup"><span data-stu-id="6aa09-151">Returns an object that represents the item with which you're working.</span></span> <span data-ttu-id="6aa09-152">Standardmäßig `Update-ScriptFileInfo` generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="6aa09-152">By default, `Update-ScriptFileInfo` doesn't generate any output.</span></span>

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

### <span data-ttu-id="6aa09-153">-Path</span><span class="sxs-lookup"><span data-stu-id="6aa09-153">-Path</span></span>

<span data-ttu-id="6aa09-154">Gibt den Speicherort der Skriptdatei an.</span><span class="sxs-lookup"><span data-stu-id="6aa09-154">Specifies the script file's location.</span></span> <span data-ttu-id="6aa09-155">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="6aa09-155">Wildcards are permitted.</span></span>

```yaml
Type: System.String
Parameter Sets: PathParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="6aa09-156">-PRIVATEDATA</span><span class="sxs-lookup"><span data-stu-id="6aa09-156">-PrivateData</span></span>

<span data-ttu-id="6aa09-157">Gibt die privaten Daten für das Skript an.</span><span class="sxs-lookup"><span data-stu-id="6aa09-157">Specifies the private data for the script.</span></span>

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

### <span data-ttu-id="6aa09-158">-Projecturi</span><span class="sxs-lookup"><span data-stu-id="6aa09-158">-ProjectUri</span></span>

<span data-ttu-id="6aa09-159">Gibt die URL einer Webseite zu diesem Projekt an.</span><span class="sxs-lookup"><span data-stu-id="6aa09-159">Specifies the URL of a web page about this project.</span></span>

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

### <span data-ttu-id="6aa09-160">-Releasenotes</span><span class="sxs-lookup"><span data-stu-id="6aa09-160">-ReleaseNotes</span></span>

<span data-ttu-id="6aa09-161">Gibt ein Zeichen folgen Array an, das Anmerkungen oder Kommentare enthält, die Sie für diese Version des Skripts zur Verfügung stellen möchten.</span><span class="sxs-lookup"><span data-stu-id="6aa09-161">Specifies a string array that contains release notes or comments that you want available for this version of the script.</span></span>

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

### <span data-ttu-id="6aa09-162">-Requirements dmodules</span><span class="sxs-lookup"><span data-stu-id="6aa09-162">-RequiredModules</span></span>

<span data-ttu-id="6aa09-163">Gibt die Module an, die im globalen Sitzungsstatus enthalten sein müssen.</span><span class="sxs-lookup"><span data-stu-id="6aa09-163">Specifies modules that must be in the global session state.</span></span> <span data-ttu-id="6aa09-164">Wenn sich die erforderlichen Module nicht im globalen Sitzungs Status befinden, importiert PowerShell Sie.</span><span class="sxs-lookup"><span data-stu-id="6aa09-164">If the required modules aren't in the global session state, PowerShell imports them.</span></span>

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

### <span data-ttu-id="6aa09-165">-Requirements dscripts</span><span class="sxs-lookup"><span data-stu-id="6aa09-165">-RequiredScripts</span></span>

<span data-ttu-id="6aa09-166">Gibt ein Array von erforderlichen Skripts an.</span><span class="sxs-lookup"><span data-stu-id="6aa09-166">Specifies an array of required scripts.</span></span>

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

### <span data-ttu-id="6aa09-167">-Tags</span><span class="sxs-lookup"><span data-stu-id="6aa09-167">-Tags</span></span>

<span data-ttu-id="6aa09-168">Gibt ein Array von-Tags an.</span><span class="sxs-lookup"><span data-stu-id="6aa09-168">Specifies an array of tags.</span></span>

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

### <span data-ttu-id="6aa09-169">-Version</span><span class="sxs-lookup"><span data-stu-id="6aa09-169">-Version</span></span>

<span data-ttu-id="6aa09-170">Gibt die Version des Skripts an.</span><span class="sxs-lookup"><span data-stu-id="6aa09-170">Specifies the script's version.</span></span>

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

### <span data-ttu-id="6aa09-171">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="6aa09-171">-WhatIf</span></span>

<span data-ttu-id="6aa09-172">Zeigt, was geschieht, wenn ausgeführt wird `Update-ScriptFileInfo` .</span><span class="sxs-lookup"><span data-stu-id="6aa09-172">Shows what would happen if `Update-ScriptFileInfo` runs.</span></span> <span data-ttu-id="6aa09-173">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="6aa09-173">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="6aa09-174">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="6aa09-174">CommonParameters</span></span>

<span data-ttu-id="6aa09-175">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="6aa09-175">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="6aa09-176">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="6aa09-176">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="6aa09-177">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="6aa09-177">INPUTS</span></span>

### <span data-ttu-id="6aa09-178">System.String</span><span class="sxs-lookup"><span data-stu-id="6aa09-178">System.String</span></span>

## <span data-ttu-id="6aa09-179">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="6aa09-179">OUTPUTS</span></span>

### <span data-ttu-id="6aa09-180">System.Object</span><span class="sxs-lookup"><span data-stu-id="6aa09-180">System.Object</span></span>

## <span data-ttu-id="6aa09-181">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="6aa09-181">NOTES</span></span>

<span data-ttu-id="6aa09-182">Verwenden `Test-ScriptFileInfo` Sie das Cmdlet, um die Metadaten eines Skripts zu validieren.</span><span class="sxs-lookup"><span data-stu-id="6aa09-182">Use the `Test-ScriptFileInfo` cmdlet to validate a script's metadata.</span></span> <span data-ttu-id="6aa09-183">Skripts müssen Werte für die Version, die GUID, die Beschreibung und den Autor enthalten.</span><span class="sxs-lookup"><span data-stu-id="6aa09-183">Scripts must include values for version, GUID, description, and author.</span></span>

## <span data-ttu-id="6aa09-184">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="6aa09-184">RELATED LINKS</span></span>

[<span data-ttu-id="6aa09-185">New-ScriptFileInfo</span><span class="sxs-lookup"><span data-stu-id="6aa09-185">New-ScriptFileInfo</span></span>](New-ScriptFileInfo.md)

[<span data-ttu-id="6aa09-186">Test-ScriptFileInfo</span><span class="sxs-lookup"><span data-stu-id="6aa09-186">Test-ScriptFileInfo</span></span>](Test-ScriptFileInfo.md)

