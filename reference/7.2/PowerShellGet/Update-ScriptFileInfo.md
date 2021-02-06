---
external help file: PSModule-help.xml
Locale: en-US
Module Name: PowerShellGet
ms.date: 07/09/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/update-scriptfileinfo?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Update-ScriptFileInfo
ms.openlocfilehash: de138a27ed9425057406dc6120a8354b72a3b8a3
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601129"
---
# <span data-ttu-id="0b1c4-102">Update-ScriptFileInfo</span><span class="sxs-lookup"><span data-stu-id="0b1c4-102">Update-ScriptFileInfo</span></span>

## <span data-ttu-id="0b1c4-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="0b1c4-103">SYNOPSIS</span></span>
<span data-ttu-id="0b1c4-104">Aktualisiert Informationen für ein Skript.</span><span class="sxs-lookup"><span data-stu-id="0b1c4-104">Updates information for a script.</span></span>

## <span data-ttu-id="0b1c4-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="0b1c4-105">SYNTAX</span></span>

### <span data-ttu-id="0b1c4-106">Pathparameterset (Standard)</span><span class="sxs-lookup"><span data-stu-id="0b1c4-106">PathParameterSet (Default)</span></span>

```
Update-ScriptFileInfo [-Path] <String> [-Version <String>] [-Author <String>] [-Guid <Guid>]
 [-Description <String>] [-CompanyName <String>] [-Copyright <String>] [-RequiredModules <Object[]>]
 [-ExternalModuleDependencies <String[]>] [-RequiredScripts <String[]>]
 [-ExternalScriptDependencies <String[]>] [-Tags <String[]>] [-ProjectUri <Uri>] [-LicenseUri <Uri>]
 [-IconUri <Uri>] [-ReleaseNotes <String[]>] [-PrivateData <String>] [-PassThru] [-Force] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="0b1c4-107">Literalpathparameterset</span><span class="sxs-lookup"><span data-stu-id="0b1c4-107">LiteralPathParameterSet</span></span>

```
Update-ScriptFileInfo [-LiteralPath] <String> [-Version <String>] [-Author <String>] [-Guid <Guid>]
 [-Description <String>] [-CompanyName <String>] [-Copyright <String>] [-RequiredModules <Object[]>]
 [-ExternalModuleDependencies <String[]>] [-RequiredScripts <String[]>]
 [-ExternalScriptDependencies <String[]>] [-Tags <String[]>] [-ProjectUri <Uri>] [-LicenseUri <Uri>]
 [-IconUri <Uri>] [-ReleaseNotes <String[]>] [-PrivateData <String>] [-PassThru] [-Force] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="0b1c4-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0b1c4-108">DESCRIPTION</span></span>

<span data-ttu-id="0b1c4-109">Mit dem `Update-ScriptFileInfo` -Cmdlet werden die Eigenschaftswerte eines Skripts aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="0b1c4-109">The `Update-ScriptFileInfo` cmdlet updates a script's property values.</span></span> <span data-ttu-id="0b1c4-110">Dies sind z. b. die Werte für Version, Autor oder Beschreibung.</span><span class="sxs-lookup"><span data-stu-id="0b1c4-110">For example, the values for version, author, or description.</span></span>

## <span data-ttu-id="0b1c4-111">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="0b1c4-111">EXAMPLES</span></span>

### <span data-ttu-id="0b1c4-112">Beispiel 1: Aktualisieren der Version einer Skriptdatei</span><span class="sxs-lookup"><span data-stu-id="0b1c4-112">Example 1: Update the version of a script file</span></span>

<span data-ttu-id="0b1c4-113">In diesem Beispiel wird eine vorhandene Skriptdatei mit neuen Eigenschafts Werten aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="0b1c4-113">In this example, an existing script file is updated with new property values.</span></span>

<span data-ttu-id="0b1c4-114">Splatting wird verwendet, um Parameter an das `Update-ScriptFileInfo` Cmdlet zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="0b1c4-114">Splatting is used to pass parameters to the `Update-ScriptFileInfo` cmdlet.</span></span> <span data-ttu-id="0b1c4-115">Weitere Informationen finden Sie unter [about_Splatting](../Microsoft.Powershell.Core/About/about_splatting.md).</span><span class="sxs-lookup"><span data-stu-id="0b1c4-115">For more information, see [about_Splatting](../Microsoft.Powershell.Core/About/about_splatting.md).</span></span>

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

<span data-ttu-id="0b1c4-116">`$Parms` speichert die Parameterwerte für **path**, **Version**, **Author**, **CompanyName** und **Description**.</span><span class="sxs-lookup"><span data-stu-id="0b1c4-116">`$Parms` stores the parameter values for **Path**, **Version**, **Author**, **CompanyName**, and **Description**.</span></span> <span data-ttu-id="0b1c4-117">`Update-ScriptFileInfo` Ruft die Parameterwerte aus ab `@Parms` und aktualisiert das Skript.</span><span class="sxs-lookup"><span data-stu-id="0b1c4-117">`Update-ScriptFileInfo` gets the parameter values from `@Parms` and updates the script.</span></span> <span data-ttu-id="0b1c4-118">Der **passthru** -Parameter zeigt den Inhalt des Skripts in der PowerShell-Konsole an.</span><span class="sxs-lookup"><span data-stu-id="0b1c4-118">The **PassThru** parameter displays the script's contents in the PowerShell console.</span></span>

## <span data-ttu-id="0b1c4-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="0b1c4-119">PARAMETERS</span></span>

### <span data-ttu-id="0b1c4-120">-Autor</span><span class="sxs-lookup"><span data-stu-id="0b1c4-120">-Author</span></span>

<span data-ttu-id="0b1c4-121">Gibt den Autor des Skripts an.</span><span class="sxs-lookup"><span data-stu-id="0b1c4-121">Specifies the script author.</span></span>

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

### <span data-ttu-id="0b1c4-122">-CompanyName</span><span class="sxs-lookup"><span data-stu-id="0b1c4-122">-CompanyName</span></span>

<span data-ttu-id="0b1c4-123">Gibt das Unternehmen oder den Hersteller an, das das Skript erstellt hat.</span><span class="sxs-lookup"><span data-stu-id="0b1c4-123">Specifies the company or vendor who created the script.</span></span>

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

### <span data-ttu-id="0b1c4-124">-Confirm</span><span class="sxs-lookup"><span data-stu-id="0b1c4-124">-Confirm</span></span>

<span data-ttu-id="0b1c4-125">Sie werden zur Bestätigung aufgefordert, bevor Sie ausgeführt werden `Update-ScriptFileInfo` .</span><span class="sxs-lookup"><span data-stu-id="0b1c4-125">Prompts you for confirmation before running `Update-ScriptFileInfo`.</span></span>

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

### <span data-ttu-id="0b1c4-126">-Copyright</span><span class="sxs-lookup"><span data-stu-id="0b1c4-126">-Copyright</span></span>

<span data-ttu-id="0b1c4-127">Gibt eine Copyright Anweisung für das Skript an.</span><span class="sxs-lookup"><span data-stu-id="0b1c4-127">Specifies a copyright statement for the script.</span></span>

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

### <span data-ttu-id="0b1c4-128">-Description</span><span class="sxs-lookup"><span data-stu-id="0b1c4-128">-Description</span></span>

<span data-ttu-id="0b1c4-129">Gibt eine Beschreibung für das Skript an.</span><span class="sxs-lookup"><span data-stu-id="0b1c4-129">Specifies a description for the script.</span></span>

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

### <span data-ttu-id="0b1c4-130">-Externalmoduledependen</span><span class="sxs-lookup"><span data-stu-id="0b1c4-130">-ExternalModuleDependencies</span></span>

<span data-ttu-id="0b1c4-131">Gibt ein Array externer Modul Abhängigkeiten an.</span><span class="sxs-lookup"><span data-stu-id="0b1c4-131">Specifies an array of external module dependencies.</span></span>

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

### <span data-ttu-id="0b1c4-132">-Externalscriptdependen</span><span class="sxs-lookup"><span data-stu-id="0b1c4-132">-ExternalScriptDependencies</span></span>

<span data-ttu-id="0b1c4-133">Gibt ein Array externer Skript Abhängigkeiten an.</span><span class="sxs-lookup"><span data-stu-id="0b1c4-133">Specifies an array of external script dependencies.</span></span>

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

### <span data-ttu-id="0b1c4-134">-Force</span><span class="sxs-lookup"><span data-stu-id="0b1c4-134">-Force</span></span>

<span data-ttu-id="0b1c4-135">Erzwingt das `Update-ScriptFileInfo` Ausführen von, ohne dass eine Benutzer Bestätigung angefordert wird.</span><span class="sxs-lookup"><span data-stu-id="0b1c4-135">Forces `Update-ScriptFileInfo` to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="0b1c4-136">-GUID</span><span class="sxs-lookup"><span data-stu-id="0b1c4-136">-Guid</span></span>

<span data-ttu-id="0b1c4-137">Gibt eine eindeutige ID für ein Skript an.</span><span class="sxs-lookup"><span data-stu-id="0b1c4-137">Specifies a unique ID for a script.</span></span>

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

### <span data-ttu-id="0b1c4-138">-Iconuri</span><span class="sxs-lookup"><span data-stu-id="0b1c4-138">-IconUri</span></span>

<span data-ttu-id="0b1c4-139">Gibt die URL eines Symbols für das Skript an.</span><span class="sxs-lookup"><span data-stu-id="0b1c4-139">Specifies the URL of an icon for the script.</span></span> <span data-ttu-id="0b1c4-140">Das angegebene Symbol wird auf der Katalog Webseite für das Skript angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0b1c4-140">The specified icon is displayed on the gallery web page for the script.</span></span>

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

### <span data-ttu-id="0b1c4-141">-Licenaburi</span><span class="sxs-lookup"><span data-stu-id="0b1c4-141">-LicenseUri</span></span>

<span data-ttu-id="0b1c4-142">Gibt die URL der Lizenzbedingungen an.</span><span class="sxs-lookup"><span data-stu-id="0b1c4-142">Specifies the URL of licensing terms.</span></span>

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

### <span data-ttu-id="0b1c4-143">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="0b1c4-143">-LiteralPath</span></span>

<span data-ttu-id="0b1c4-144">Gibt einen Pfad zu einem oder mehreren Speicherorten an.</span><span class="sxs-lookup"><span data-stu-id="0b1c4-144">Specifies a path to one or more locations.</span></span> <span data-ttu-id="0b1c4-145">Der Wert des **literalpath** -Parameters wird genau so verwendet, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="0b1c4-145">The **LiteralPath** parameter's value is used exactly as it's entered.</span></span> <span data-ttu-id="0b1c4-146">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="0b1c4-146">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="0b1c4-147">Wenn der Pfad Escapezeichen enthält, schließen Sie Sie in einfache Anführungszeichen ein.</span><span class="sxs-lookup"><span data-stu-id="0b1c4-147">If the path includes escape characters, enclose them in single quotation marks.</span></span> <span data-ttu-id="0b1c4-148">Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="0b1c4-148">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="0b1c4-149">-PassThru</span><span class="sxs-lookup"><span data-stu-id="0b1c4-149">-PassThru</span></span>

<span data-ttu-id="0b1c4-150">Gibt ein-Objekt zurück, das das Element darstellt, mit dem Sie arbeiten.</span><span class="sxs-lookup"><span data-stu-id="0b1c4-150">Returns an object that represents the item with which you're working.</span></span> <span data-ttu-id="0b1c4-151">Standardmäßig `Update-ScriptFileInfo` generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="0b1c4-151">By default, `Update-ScriptFileInfo` doesn't generate any output.</span></span>

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

### <span data-ttu-id="0b1c4-152">-Path</span><span class="sxs-lookup"><span data-stu-id="0b1c4-152">-Path</span></span>

<span data-ttu-id="0b1c4-153">Gibt den Speicherort der Skriptdatei an.</span><span class="sxs-lookup"><span data-stu-id="0b1c4-153">Specifies the script file's location.</span></span> <span data-ttu-id="0b1c4-154">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="0b1c4-154">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="0b1c4-155">-PRIVATEDATA</span><span class="sxs-lookup"><span data-stu-id="0b1c4-155">-PrivateData</span></span>

<span data-ttu-id="0b1c4-156">Gibt die privaten Daten für das Skript an.</span><span class="sxs-lookup"><span data-stu-id="0b1c4-156">Specifies the private data for the script.</span></span>

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

### <span data-ttu-id="0b1c4-157">-Projecturi</span><span class="sxs-lookup"><span data-stu-id="0b1c4-157">-ProjectUri</span></span>

<span data-ttu-id="0b1c4-158">Gibt die URL einer Webseite zu diesem Projekt an.</span><span class="sxs-lookup"><span data-stu-id="0b1c4-158">Specifies the URL of a web page about this project.</span></span>

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

### <span data-ttu-id="0b1c4-159">-Releasenotes</span><span class="sxs-lookup"><span data-stu-id="0b1c4-159">-ReleaseNotes</span></span>

<span data-ttu-id="0b1c4-160">Gibt ein Zeichen folgen Array an, das Anmerkungen oder Kommentare enthält, die Sie für diese Version des Skripts zur Verfügung stellen möchten.</span><span class="sxs-lookup"><span data-stu-id="0b1c4-160">Specifies a string array that contains release notes or comments that you want available for this version of the script.</span></span>

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

### <span data-ttu-id="0b1c4-161">-Requirements dmodules</span><span class="sxs-lookup"><span data-stu-id="0b1c4-161">-RequiredModules</span></span>

<span data-ttu-id="0b1c4-162">Gibt die Module an, die im globalen Sitzungsstatus enthalten sein müssen.</span><span class="sxs-lookup"><span data-stu-id="0b1c4-162">Specifies modules that must be in the global session state.</span></span> <span data-ttu-id="0b1c4-163">Wenn sich die erforderlichen Module nicht im globalen Sitzungs Status befinden, importiert PowerShell Sie.</span><span class="sxs-lookup"><span data-stu-id="0b1c4-163">If the required modules aren't in the global session state, PowerShell imports them.</span></span>

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

### <span data-ttu-id="0b1c4-164">-Requirements dscripts</span><span class="sxs-lookup"><span data-stu-id="0b1c4-164">-RequiredScripts</span></span>

<span data-ttu-id="0b1c4-165">Gibt ein Array von erforderlichen Skripts an.</span><span class="sxs-lookup"><span data-stu-id="0b1c4-165">Specifies an array of required scripts.</span></span>

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

### <span data-ttu-id="0b1c4-166">-Tags</span><span class="sxs-lookup"><span data-stu-id="0b1c4-166">-Tags</span></span>

<span data-ttu-id="0b1c4-167">Gibt ein Array von-Tags an.</span><span class="sxs-lookup"><span data-stu-id="0b1c4-167">Specifies an array of tags.</span></span>

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

### <span data-ttu-id="0b1c4-168">-Version</span><span class="sxs-lookup"><span data-stu-id="0b1c4-168">-Version</span></span>

<span data-ttu-id="0b1c4-169">Gibt die Version des Skripts an.</span><span class="sxs-lookup"><span data-stu-id="0b1c4-169">Specifies the script's version.</span></span>

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

### <span data-ttu-id="0b1c4-170">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="0b1c4-170">-WhatIf</span></span>

<span data-ttu-id="0b1c4-171">Zeigt, was geschieht, wenn ausgeführt wird `Update-ScriptFileInfo` .</span><span class="sxs-lookup"><span data-stu-id="0b1c4-171">Shows what would happen if `Update-ScriptFileInfo` runs.</span></span> <span data-ttu-id="0b1c4-172">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="0b1c4-172">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="0b1c4-173">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="0b1c4-173">CommonParameters</span></span>

<span data-ttu-id="0b1c4-174">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="0b1c4-174">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="0b1c4-175">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="0b1c4-175">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="0b1c4-176">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="0b1c4-176">INPUTS</span></span>

### <span data-ttu-id="0b1c4-177">System.String</span><span class="sxs-lookup"><span data-stu-id="0b1c4-177">System.String</span></span>

## <span data-ttu-id="0b1c4-178">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="0b1c4-178">OUTPUTS</span></span>

### <span data-ttu-id="0b1c4-179">System.Object</span><span class="sxs-lookup"><span data-stu-id="0b1c4-179">System.Object</span></span>

## <span data-ttu-id="0b1c4-180">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="0b1c4-180">NOTES</span></span>

<span data-ttu-id="0b1c4-181">Verwenden `Test-ScriptFileInfo` Sie das Cmdlet, um die Metadaten eines Skripts zu validieren.</span><span class="sxs-lookup"><span data-stu-id="0b1c4-181">Use the `Test-ScriptFileInfo` cmdlet to validate a script's metadata.</span></span> <span data-ttu-id="0b1c4-182">Skripts müssen Werte für die Version, die GUID, die Beschreibung und den Autor enthalten.</span><span class="sxs-lookup"><span data-stu-id="0b1c4-182">Scripts must include values for version, GUID, description, and author.</span></span>

## <span data-ttu-id="0b1c4-183">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="0b1c4-183">RELATED LINKS</span></span>

[<span data-ttu-id="0b1c4-184">New-ScriptFileInfo</span><span class="sxs-lookup"><span data-stu-id="0b1c4-184">New-ScriptFileInfo</span></span>](New-ScriptFileInfo.md)

[<span data-ttu-id="0b1c4-185">Test-ScriptFileInfo</span><span class="sxs-lookup"><span data-stu-id="0b1c4-185">Test-ScriptFileInfo</span></span>](Test-ScriptFileInfo.md)

