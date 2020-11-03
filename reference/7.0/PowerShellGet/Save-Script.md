---
external help file: PSModule-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PowerShellGet
ms.date: 07/02/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/save-script?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Save-Script
ms.openlocfilehash: 72c27ddbcdce935bdad3e424ebdf834b9a82a69c
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2020
ms.locfileid: "93209959"
---
# <span data-ttu-id="6ef04-103">Save-Script</span><span class="sxs-lookup"><span data-stu-id="6ef04-103">Save-Script</span></span>

## <span data-ttu-id="6ef04-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="6ef04-104">SYNOPSIS</span></span>
<span data-ttu-id="6ef04-105">Speichert ein Skript.</span><span class="sxs-lookup"><span data-stu-id="6ef04-105">Saves a script.</span></span>

## <span data-ttu-id="6ef04-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="6ef04-106">SYNTAX</span></span>

### <span data-ttu-id="6ef04-107">Nameandpathparameterset (Standard)</span><span class="sxs-lookup"><span data-stu-id="6ef04-107">NameAndPathParameterSet (Default)</span></span>

```
Save-Script [-Name] <String[]> [-MinimumVersion <String>] [-MaximumVersion <String>]
 [-RequiredVersion <String>] [-Repository <String[]>] [-Path] <String> [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-Credential <PSCredential>] [-Force] [-AllowPrerelease]
 [-AcceptLicense] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="6ef04-108">Nameandliteralpathparameterset</span><span class="sxs-lookup"><span data-stu-id="6ef04-108">NameAndLiteralPathParameterSet</span></span>

```
Save-Script [-Name] <String[]> [-MinimumVersion <String>] [-MaximumVersion <String>]
 [-RequiredVersion <String>] [-Repository <String[]>] -LiteralPath <String> [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-Credential <PSCredential>] [-Force] [-AllowPrerelease]
 [-AcceptLicense] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="6ef04-109">Inputobjectandliteralpathparameterset</span><span class="sxs-lookup"><span data-stu-id="6ef04-109">InputObjectAndLiteralPathParameterSet</span></span>

```
Save-Script [-InputObject] <PSObject[]> -LiteralPath <String> [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-Credential <PSCredential>] [-Force] [-AcceptLicense] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="6ef04-110">Inputobjectandpathparameterset</span><span class="sxs-lookup"><span data-stu-id="6ef04-110">InputObjectAndPathParameterSet</span></span>

```
Save-Script [-InputObject] <PSObject[]> [-Path] <String> [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-Credential <PSCredential>] [-Force] [-AcceptLicense] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="6ef04-111">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="6ef04-111">DESCRIPTION</span></span>

<span data-ttu-id="6ef04-112">Das- `Save-Script` Cmdlet speichert das angegebene Skript.</span><span class="sxs-lookup"><span data-stu-id="6ef04-112">The `Save-Script` cmdlet saves the specified script.</span></span>

## <span data-ttu-id="6ef04-113">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="6ef04-113">EXAMPLES</span></span>

### <span data-ttu-id="6ef04-114">Beispiel 1: Speichern eines Skripts und Validieren der Skript Metadaten</span><span class="sxs-lookup"><span data-stu-id="6ef04-114">Example 1: Save a script and validate the script's metadata</span></span>

<span data-ttu-id="6ef04-115">In diesem Beispiel wird ein Skript aus einem Repository auf dem lokalen Computer gespeichert, und die Metadaten des Skripts werden überprüft.</span><span class="sxs-lookup"><span data-stu-id="6ef04-115">In this example, a script from a repository is saved to the local computer and the script's metadata is validated.</span></span>

```powershell
Save-Script -Name Install-VSCode -Repository PSGallery -Path C:\Test\Scripts
Test-ScriptFileInfo -Path C:\Test\Scripts\Install-VSCode.ps1
```

```Output
Version   Name              Author      Description
-------   ----              ------      -----------
1.3       Install-VSCode    Microsoft   This script can be used to easily install Visual Studio Code
```

<span data-ttu-id="6ef04-116">`Save-Script` verwendet den **Name** -Parameter, um den Namen des Skripts anzugeben.</span><span class="sxs-lookup"><span data-stu-id="6ef04-116">`Save-Script` uses the **Name** parameter to specify the script's name.</span></span> <span data-ttu-id="6ef04-117">Der **Repository** -Parameter gibt an, wo das Skript zu finden ist.</span><span class="sxs-lookup"><span data-stu-id="6ef04-117">The **Repository** parameter specifies where to find the script.</span></span> <span data-ttu-id="6ef04-118">Das Skript wird an dem Speicherort gespeichert, der durch den **path** -Parameter angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="6ef04-118">The script is saved in the location specified by the **Path** parameter.</span></span> <span data-ttu-id="6ef04-119">`Test-ScriptFileInfo` Gibt den **Pfad** an und überprüft die Metadaten des Skripts.</span><span class="sxs-lookup"><span data-stu-id="6ef04-119">`Test-ScriptFileInfo` specifies the **Path** and validates the script's metadata.</span></span>

## <span data-ttu-id="6ef04-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="6ef04-120">PARAMETERS</span></span>

### <span data-ttu-id="6ef04-121">-AcceptLicense</span><span class="sxs-lookup"><span data-stu-id="6ef04-121">-AcceptLicense</span></span>

<span data-ttu-id="6ef04-122">Akzeptieren Sie den Lizenzvertrag automatisch, wenn dies für das Skript erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="6ef04-122">Automatically accept the license agreement if the script requires it.</span></span>

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

### <span data-ttu-id="6ef04-123">-Allowprerelease</span><span class="sxs-lookup"><span data-stu-id="6ef04-123">-AllowPrerelease</span></span>

<span data-ttu-id="6ef04-124">Ermöglicht das Speichern eines als Vorabversion markierten Skripts.</span><span class="sxs-lookup"><span data-stu-id="6ef04-124">Allows you to save a script marked as a prerelease.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NameAndPathParameterSet, NameAndLiteralPathParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6ef04-125">-Confirm</span><span class="sxs-lookup"><span data-stu-id="6ef04-125">-Confirm</span></span>

<span data-ttu-id="6ef04-126">Sie werden zur Bestätigung aufgefordert, bevor Sie ausgeführt werden `Save-Script` .</span><span class="sxs-lookup"><span data-stu-id="6ef04-126">Prompts you for confirmation before running `Save-Script`.</span></span>

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

### <span data-ttu-id="6ef04-127">-Credential</span><span class="sxs-lookup"><span data-stu-id="6ef04-127">-Credential</span></span>

<span data-ttu-id="6ef04-128">Gibt ein Benutzerkonto an, das über die Berechtigung zum Speichern eines Skripts verfügt.</span><span class="sxs-lookup"><span data-stu-id="6ef04-128">Specifies a user account that has permission to save a script.</span></span>

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

### <span data-ttu-id="6ef04-129">-Force</span><span class="sxs-lookup"><span data-stu-id="6ef04-129">-Force</span></span>

<span data-ttu-id="6ef04-130">Erzwingt das `Save-Script` Ausführen von, ohne dass eine Benutzer Bestätigung angefordert wird.</span><span class="sxs-lookup"><span data-stu-id="6ef04-130">Forces `Save-Script` to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="6ef04-131">-InputObject</span><span class="sxs-lookup"><span data-stu-id="6ef04-131">-InputObject</span></span>

<span data-ttu-id="6ef04-132">Akzeptiert ein **PSRepositoryItemInfo** -Objekt.</span><span class="sxs-lookup"><span data-stu-id="6ef04-132">Accepts a **PSRepositoryItemInfo** object.</span></span> <span data-ttu-id="6ef04-133">Geben `Find-Script` Sie z. b. eine Ausgabe an eine Variable ein, und verwenden Sie diese Variable als **Inputobject** -Argument.</span><span class="sxs-lookup"><span data-stu-id="6ef04-133">For example, output `Find-Script` to a variable and use that variable as the **InputObject** argument.</span></span>

```yaml
Type: System.Management.Automation.PSObject[]
Parameter Sets: InputObjectAndLiteralPathParameterSet, InputObjectAndPathParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="6ef04-134">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="6ef04-134">-LiteralPath</span></span>

<span data-ttu-id="6ef04-135">Gibt einen Pfad zu einem oder mehreren Speicherorten an.</span><span class="sxs-lookup"><span data-stu-id="6ef04-135">Specifies a path to one or more locations.</span></span> <span data-ttu-id="6ef04-136">Der Wert des **literalpath** -Parameters wird genau so verwendet, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="6ef04-136">The value of the **LiteralPath** parameter is used exactly as entered.</span></span> <span data-ttu-id="6ef04-137">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="6ef04-137">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="6ef04-138">Wenn der Pfad Escapezeichen enthält, müssen Sie den Pfad in einfache Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="6ef04-138">If the path includes escape characters, enclose the path within single quotation marks.</span></span> <span data-ttu-id="6ef04-139">PowerShell interpretiert keine Zeichen, die in einfache Anführungszeichen eingeschlossen sind, als Escapesequenzen.</span><span class="sxs-lookup"><span data-stu-id="6ef04-139">PowerShell doesn't interpret any characters enclosed in single quotation marks as escape sequences.</span></span>

```yaml
Type: System.String
Parameter Sets: NameAndLiteralPathParameterSet, InputObjectAndLiteralPathParameterSet
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="6ef04-140">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="6ef04-140">-MaximumVersion</span></span>

<span data-ttu-id="6ef04-141">Gibt die maximale oder neueste Version des zu speichernden Skripts an.</span><span class="sxs-lookup"><span data-stu-id="6ef04-141">Specifies the maximum, or newest version of the script to save.</span></span> <span data-ttu-id="6ef04-142">Die Parameter **MaximumVersion** und Requirements **dversion** können nicht im selben Befehl verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6ef04-142">The **MaximumVersion** and **RequiredVersion** parameters can't be used in the same command.</span></span>

```yaml
Type: System.String
Parameter Sets: NameAndPathParameterSet, NameAndLiteralPathParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="6ef04-143">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="6ef04-143">-MinimumVersion</span></span>

<span data-ttu-id="6ef04-144">Gibt die Mindestversion eines zu speichernden Skripts an.</span><span class="sxs-lookup"><span data-stu-id="6ef04-144">Specifies the minimum version of a script to save.</span></span> <span data-ttu-id="6ef04-145">Die Parameter **MinimumVersion** und Requirements **dversion** können nicht im selben Befehl verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6ef04-145">The **MinimumVersion** and **RequiredVersion** parameters can't be used in the same command.</span></span>

```yaml
Type: System.String
Parameter Sets: NameAndPathParameterSet, NameAndLiteralPathParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="6ef04-146">-Name</span><span class="sxs-lookup"><span data-stu-id="6ef04-146">-Name</span></span>

<span data-ttu-id="6ef04-147">Gibt ein Array von Skriptnamen an, die gespeichert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="6ef04-147">Specifies an array of script names to save.</span></span>

```yaml
Type: System.String[]
Parameter Sets: NameAndPathParameterSet, NameAndLiteralPathParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="6ef04-148">-Path</span><span class="sxs-lookup"><span data-stu-id="6ef04-148">-Path</span></span>

<span data-ttu-id="6ef04-149">Gibt den Speicherort auf dem lokalen Computer zum Speichern eines gespeicherten Moduls an.</span><span class="sxs-lookup"><span data-stu-id="6ef04-149">Specifies the location on the local computer to store a saved module.</span></span> <span data-ttu-id="6ef04-150">Akzeptiert Platzhalter Zeichen.</span><span class="sxs-lookup"><span data-stu-id="6ef04-150">Accepts wildcard characters.</span></span>

```yaml
Type: System.String
Parameter Sets: NameAndPathParameterSet, InputObjectAndPathParameterSet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="6ef04-151">-Proxy</span><span class="sxs-lookup"><span data-stu-id="6ef04-151">-Proxy</span></span>

<span data-ttu-id="6ef04-152">Gibt einen Proxy Server für die Anforderung an, anstatt eine direkte Verbindung mit einer Internet Ressource herzustellen.</span><span class="sxs-lookup"><span data-stu-id="6ef04-152">Specifies a proxy server for the request, rather than connecting directly to an internet resource.</span></span>

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

### <span data-ttu-id="6ef04-153">-Proxy Credential</span><span class="sxs-lookup"><span data-stu-id="6ef04-153">-ProxyCredential</span></span>

<span data-ttu-id="6ef04-154">Gibt ein Benutzerkonto an, das über die Berechtigung zum Verwenden des Proxy Servers verfügt, der durch den **Proxy** Parameter angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="6ef04-154">Specifies a user account that has permission to use the proxy server specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="6ef04-155">-Repository</span><span class="sxs-lookup"><span data-stu-id="6ef04-155">-Repository</span></span>

<span data-ttu-id="6ef04-156">Gibt den anzeigen Amen eines Repository an, das durch Ausführen von registriert wurde `Register-PSRepository` .</span><span class="sxs-lookup"><span data-stu-id="6ef04-156">Specifies the friendly name of a repository that has been registered by running `Register-PSRepository`.</span></span> <span data-ttu-id="6ef04-157">Verwenden `Get-PSRepository` Sie, um registrierte Depots anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="6ef04-157">Use `Get-PSRepository` to display registered repositories.</span></span>

```yaml
Type: System.String[]
Parameter Sets: NameAndPathParameterSet, NameAndLiteralPathParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="6ef04-158">-Requirements dversion</span><span class="sxs-lookup"><span data-stu-id="6ef04-158">-RequiredVersion</span></span>

<span data-ttu-id="6ef04-159">Gibt die genaue Versionsnummer des zu speichernden Skripts an.</span><span class="sxs-lookup"><span data-stu-id="6ef04-159">Specifies the exact version number of the script to save.</span></span>

```yaml
Type: System.String
Parameter Sets: NameAndPathParameterSet, NameAndLiteralPathParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="6ef04-160">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="6ef04-160">-WhatIf</span></span>

<span data-ttu-id="6ef04-161">Zeigt, was geschieht, wenn ausgeführt wird `Save-Script` .</span><span class="sxs-lookup"><span data-stu-id="6ef04-161">Shows what would happen if `Save-Script` runs.</span></span> <span data-ttu-id="6ef04-162">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="6ef04-162">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="6ef04-163">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="6ef04-163">CommonParameters</span></span>

<span data-ttu-id="6ef04-164">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="6ef04-164">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="6ef04-165">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="6ef04-165">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="6ef04-166">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="6ef04-166">INPUTS</span></span>

### <span data-ttu-id="6ef04-167">System.String[]</span><span class="sxs-lookup"><span data-stu-id="6ef04-167">System.String[]</span></span>

### <span data-ttu-id="6ef04-168">System. Management. Automation. psobject []</span><span class="sxs-lookup"><span data-stu-id="6ef04-168">System.Management.Automation.PSObject[]</span></span>

### <span data-ttu-id="6ef04-169">System.String</span><span class="sxs-lookup"><span data-stu-id="6ef04-169">System.String</span></span>

### <span data-ttu-id="6ef04-170">System.Uri</span><span class="sxs-lookup"><span data-stu-id="6ef04-170">System.Uri</span></span>

### <span data-ttu-id="6ef04-171">System. Management. Automation. PSCredential</span><span class="sxs-lookup"><span data-stu-id="6ef04-171">System.Management.Automation.PSCredential</span></span>

## <span data-ttu-id="6ef04-172">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="6ef04-172">OUTPUTS</span></span>

### <span data-ttu-id="6ef04-173">System.Object</span><span class="sxs-lookup"><span data-stu-id="6ef04-173">System.Object</span></span>

## <span data-ttu-id="6ef04-174">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="6ef04-174">NOTES</span></span>

## <span data-ttu-id="6ef04-175">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="6ef04-175">RELATED LINKS</span></span>

[<span data-ttu-id="6ef04-176">Find-Script</span><span class="sxs-lookup"><span data-stu-id="6ef04-176">Find-Script</span></span>](Find-Script.md)

[<span data-ttu-id="6ef04-177">Install-Script</span><span class="sxs-lookup"><span data-stu-id="6ef04-177">Install-Script</span></span>](Install-Script.md)

[<span data-ttu-id="6ef04-178">Publish-Script</span><span class="sxs-lookup"><span data-stu-id="6ef04-178">Publish-Script</span></span>](Publish-Script.md)

[<span data-ttu-id="6ef04-179">Test-ScriptFileInfo</span><span class="sxs-lookup"><span data-stu-id="6ef04-179">Test-ScriptFileInfo</span></span>](Test-ScriptFileInfo.md)

[<span data-ttu-id="6ef04-180">Uninstall-Script</span><span class="sxs-lookup"><span data-stu-id="6ef04-180">Uninstall-Script</span></span>](Uninstall-Script.md)

[<span data-ttu-id="6ef04-181">Update-Script</span><span class="sxs-lookup"><span data-stu-id="6ef04-181">Update-Script</span></span>](Update-Script.md)
