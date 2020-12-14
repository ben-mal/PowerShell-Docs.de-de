---
external help file: PSModule-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PowerShellGet
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/powershellget/find-script?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Find-Script
ms.openlocfilehash: 443795160fcf5b11ffdc2d7d4e6f5d265b160002
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/19/2020
ms.locfileid: "94892418"
---
# <span data-ttu-id="c9c69-103">Find-Script</span><span class="sxs-lookup"><span data-stu-id="c9c69-103">Find-Script</span></span>

## <span data-ttu-id="c9c69-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="c9c69-104">SYNOPSIS</span></span>
<span data-ttu-id="c9c69-105">Sucht nach einem Skript.</span><span class="sxs-lookup"><span data-stu-id="c9c69-105">Finds a script.</span></span>

## <span data-ttu-id="c9c69-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c9c69-106">SYNTAX</span></span>

```
Find-Script [[-Name] <String[]>] [-MinimumVersion <String>] [-MaximumVersion <String>]
 [-RequiredVersion <String>] [-AllVersions] [-IncludeDependencies] [-Filter <String>] [-Tag <String[]>]
 [-Includes <String[]>] [-Command <String[]>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-Repository <String[]>] [-Credential <PSCredential>] [-AllowPrerelease] [<CommonParameters>]
```

## <span data-ttu-id="c9c69-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="c9c69-107">DESCRIPTION</span></span>

<span data-ttu-id="c9c69-108">Das Cmdlet " **Find-Script** " findet ein bestimmtes Skript in registrierten Depots.</span><span class="sxs-lookup"><span data-stu-id="c9c69-108">The **Find-Script** cmdlet finds a specified script in registered repositories.</span></span>

## <span data-ttu-id="c9c69-109">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="c9c69-109">EXAMPLES</span></span>

### <span data-ttu-id="c9c69-110">Beispiel 1: Suchen aller verfügbaren Skripts</span><span class="sxs-lookup"><span data-stu-id="c9c69-110">Example 1: Find all available scripts</span></span>

```
PS C:\> Find-Script
Version    Name                                Type       Repository           Description
-------    ----                                ----       ----------           -----------
2.5        Fabrikam-ClientScript               Script     LocalRepo1           Description for the Fabrikam-ClientScript script
2.5        Fabrikam-Script                     Script     LocalRepo1           Description for the Fabrikam-Script script
2.5        Fabrikam-ServerScript               Script     LocalRepo1           Description for the Fabrikam-ServerScript script
2.5        Required-Script1                    Script     LocalRepo1           Description for the Required-Script1 script
2.5        Required-Script2                    Script     LocalRepo1           Description for the Required-Script2 script
2.5        Required-Script3                    Script     LocalRepo1           Description for the Required-Script3 script
2.0        Script-WithDependencies1            Script     LocalRepo1           Description for the Script-WithDependencies1 script
2.0        Script-WithDependencies2            Script     LocalRepo1           Description for the Script-WithDependencies2 script
2.0        Start-WFContosoServer               Script     LocalRepo1           Start-WFContosoServer Script example
2.1        Test-Script1                        Script     LocalRepo1           Test-Script1 Script example
2.0        Test-Script2                        Script     LocalRepo1           Test-Script2 Script example
1.0        TestRunbook                         Script     LocalRepo1           Contoso Script example
```

<span data-ttu-id="c9c69-111">Dieser Befehl sucht nach allen verfügbaren Skripts.</span><span class="sxs-lookup"><span data-stu-id="c9c69-111">This command finds all available scripts.</span></span>

### <span data-ttu-id="c9c69-112">Beispiel 2: Suchen eines Skripts anhand des Namens</span><span class="sxs-lookup"><span data-stu-id="c9c69-112">Example 2: Find a script by name</span></span>

```
PS C:\> Find-Script -Name "Start-WFContosoServer"
Version    Name                                Type       Repository           Description
-------    ----                                ----       ----------           -----------
2.0        Start-WFContosoServer               Script     LocalRepo1           Start-WFContosoServer Script example
```

<span data-ttu-id="c9c69-113">Mit diesem Befehl wird das Skript "Start-WF condesoserver" gefunden.</span><span class="sxs-lookup"><span data-stu-id="c9c69-113">This command find the script named Start-WFContosoServer.</span></span>

### <span data-ttu-id="c9c69-114">Beispiel 3: Suchen eines Skripts anhand des Namens, der erforderlichen Version und aus einem angegebenen Repository</span><span class="sxs-lookup"><span data-stu-id="c9c69-114">Example 3: Find a script by name, required version, and from a specified repository</span></span>

```
PS C:\> Find-Script -Name "Required-Script2" -RequiredVersion 2.0 -Repository "LocalRepo01"
```

<span data-ttu-id="c9c69-115">Mit diesem Befehl wird ein Skript mit dem Namen und der erforderlichen Version im LocalRepo01-Repository gefunden.</span><span class="sxs-lookup"><span data-stu-id="c9c69-115">This command finds a script by name and required version in the LocalRepo01 repository.</span></span>

### <span data-ttu-id="c9c69-116">Beispiel 4: Suchen eines Skripts und Formatieren der Ausgabe als Liste</span><span class="sxs-lookup"><span data-stu-id="c9c69-116">Example 4: Find a script and format the output as a list</span></span>

```
PS C:\> Find-Script -Name "Required-Script2" -RequiredVersion 2.0 -Repository "LocalRepo1" | Format-List * -Force
Name                       : Required-Script2
Version                    : 2.0
Type                       : Script
Description                : Description for the Required-Script2 script
Author                     : pattif
CompanyName                : Microsoft Corporation
Copyright                  : 2015 Microsoft Corporation. All rights reserved.
PublishedDate              : 8/14/2015 2:37:01 PM
LicenseUri                 : http://required-script2.com/license
ProjectUri                 : http://required-script2.com/
IconUri                    : http://required-script2.com/icon
Tags                       : {, Tag1, Tag2, Tag-Required-Script2-2.0...}
Includes                   : {Function, DscResource, Cmdlet, Command}
PowerShellGetFormatVersion :
ReleaseNotes               : Required-Script2 release notes
Dependencies               : {}
RepositorySourceLocation   : C:\MyLocalRepo
Repository                 : LocalRepo01
PackageManagementProvider  : NuGet
```

<span data-ttu-id="c9c69-117">Dieser Befehl sucht nach Required-Script2 im Repository LocalRepo1 und übergibt dann das resultierende **PSRepositoryItemInfo** -Objekt an das Format-List-Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="c9c69-117">This command finds Required-Script2 in the LocalRepo1 repository, and then passes the resulting **PSRepositoryItemInfo** object to the Format-List cmdlet.</span></span>

### <span data-ttu-id="c9c69-118">Beispiel 5: Suchen eines Skripts im angegebenen Versions Bereich</span><span class="sxs-lookup"><span data-stu-id="c9c69-118">Example 5: Find a script in the specified version range</span></span>

```
PS C:\> Find-Script -Name "Required-Script2" -MinimumVersion 2.1 -MaximumVersion 2.5 -Repository "LocalRepo1"
Version    Name                                Type       Repository           Description
-------    ----                                ----       ----------           -----------
2.5        Required-Script2                    Script     LocalRepo1           Description for the Required-Script2 script
```

<span data-ttu-id="c9c69-119">Dieser Befehl sucht alle Versionen von RequiredScript2 zwischen den Versionen 2,1 und 2,5 im LocalRepo1-Respository.</span><span class="sxs-lookup"><span data-stu-id="c9c69-119">This command finds all versions of RequiredScript2 between versions 2.1 and 2.5 in the LocalRepo1 respository.</span></span>

### <span data-ttu-id="c9c69-120">Beispiel 6: Suchen aller Versionen eines Skripts</span><span class="sxs-lookup"><span data-stu-id="c9c69-120">Example 6: Find all versions of a script</span></span>

```
PS C:\> Find-Script -Name "Required-Script02" -AllVersions
Version    Name                                Type       Repository           Description
-------    ----                                ----       ----------           -----------
1.0        Required-Script2                    Script     LocalRepo1           Description for the Required-Script2 script
1.5        Required-Script2                    Script     LocalRepo1           Description for the Required-Script2 script
2.0        Required-Script2                    Script     LocalRepo1           Description for the Required-Script2 script
2.5        Required-Script2                    Script     LocalRepo1           Description for the Required-Script2 script
```

<span data-ttu-id="c9c69-121">Mit diesem Befehl werden alle Versionen von required-Script02 gefunden.</span><span class="sxs-lookup"><span data-stu-id="c9c69-121">This command finds all versions of Required-Script02.</span></span>

### <span data-ttu-id="c9c69-122">Beispiel 7: Suchen eines Skripts und seiner Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="c9c69-122">Example 7: Find a script and its dependencies</span></span>

```
PS C:\> Find-Script -Name "Script-WithDependencies1" -IncludeDependencies -Repository "LocalRepo1"
Version    Name                                Type       Repository           Description
-------    ----                                ----       ----------           -----------
1.0        Script-WithDependencies1            Script     LocalRepo1           Description for the Script-WithDependencies1 script
2.0        RequiredModule3                     Script     LocalRepo1           RequiredModule3 module
2.5        Required-Script1                    Script     LocalRepo1           Description for the Required-Script1 script
2.5        Required-Script2                    Script     LocalRepo1           Description for the Required-Script2 script
```

<span data-ttu-id="c9c69-123">Mit diesem Befehl wird ein Skript und seine Abhängigkeiten gefunden.</span><span class="sxs-lookup"><span data-stu-id="c9c69-123">This command finds a script and its dependencies.</span></span>

### <span data-ttu-id="c9c69-124">Beispiel 8: Suchen nach Skripts mit dem angegebenen Tag</span><span class="sxs-lookup"><span data-stu-id="c9c69-124">Example 8: Find scripts with the specified tag</span></span>

```
PS C:\> Find-Script -Tag "Tag1" -Repository "LocalRepo1"
Version    Name                                Type       Repository           Description
-------    ----                                ----       ----------           -----------
1.0        Fabrikam-ClientScript               Script     LocalRepo1           Description for the Fabrikam-ClientScript script
```

<span data-ttu-id="c9c69-125">Dieser Befehl findet Skripts, die das Tag Tag1 im LocalRepo1-Repository enthalten.</span><span class="sxs-lookup"><span data-stu-id="c9c69-125">This command finds scripts that have the tag Tag1 in the LocalRepo1 repository</span></span>

### <span data-ttu-id="c9c69-126">Beispiel 9: Suchen nach Skripts mit dem angegebenen Befehlsnamen</span><span class="sxs-lookup"><span data-stu-id="c9c69-126">Example 9: Find scripts with specified command name</span></span>

```
PS C:\> Find-Script -Command Test-FunctionFromScript_Required-Script3 -Repository "LocalRepo1"
Version    Name                                Type       Repository           Description
-------    ----                                ----       ----------           -----------
2.5        Required-Script3                    Script     LocalRepo1           Description for the Required-Script3 script
```

<span data-ttu-id="c9c69-127">Mit diesem Befehl wird ein Skript gefunden, das den angegebenen Befehlsnamen enthält.</span><span class="sxs-lookup"><span data-stu-id="c9c69-127">This command finds a script that contains the specified command name.</span></span>

### <span data-ttu-id="c9c69-128">Beispiel 10: Suchen nach Skripts mit Workflows</span><span class="sxs-lookup"><span data-stu-id="c9c69-128">Example 10: Find scripts with workflows</span></span>

```
PS C:\> Find-Script -Includes "Workflow" -Repository "LocalRepo1"
Version    Name                                Type       Repository           Description
-------    ----                                ----       ----------           -----------
2.5        Fabrikam-ClientScript               Script     LocalRepo1           Description for the Fabrikam-ClientScript script
1.0        Fabrikam-Script                     Script     LocalRepo1           Description for the Fabrikam-Script script
```

<span data-ttu-id="c9c69-129">Dieser Befehl findet Workflow Skripts im LocalRepo1-Repository.</span><span class="sxs-lookup"><span data-stu-id="c9c69-129">This command finds workflow scripts in the LocalRepo1 repository.</span></span>

### <span data-ttu-id="c9c69-130">Beispiel 11: Suchen nach Skripts mit Platzhaltern</span><span class="sxs-lookup"><span data-stu-id="c9c69-130">Example 11: Find scripts using wildcards</span></span>

```
PS C:\> Find-Script -Name "Required-Script*" -Repository "LocalRepo1"
Version    Name                                Type       Repository           Description
-------    ----                                ----       ----------           -----------
2.5        Required-Script1                    Script     local1               Description for the Required-Script1 script
2.5        Required-Script2                    Script     local1               Description for the Required-Script2 script
2.5        Required-Script3                    Script     local1               Description for the Required-Script3 script
```

<span data-ttu-id="c9c69-131">Dieser Befehl verwendet das Platzhalter Zeichen (\*), um nach Skripts zu suchen, die mit "required-Script" beginnen.</span><span class="sxs-lookup"><span data-stu-id="c9c69-131">This command uses the wildcard character (\*) to find scripts that begin with Required-Script.</span></span>

## <span data-ttu-id="c9c69-132">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c9c69-132">PARAMETERS</span></span>

### <span data-ttu-id="c9c69-133">-Allowprerelease</span><span class="sxs-lookup"><span data-stu-id="c9c69-133">-AllowPrerelease</span></span>

<span data-ttu-id="c9c69-134">Schließt in die als Vorabversion markierten Ergebnisskripts ein.</span><span class="sxs-lookup"><span data-stu-id="c9c69-134">Includes in the results scripts marked as a prerelease.</span></span>

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

### <span data-ttu-id="c9c69-135">-Allversions</span><span class="sxs-lookup"><span data-stu-id="c9c69-135">-AllVersions</span></span>

<span data-ttu-id="c9c69-136">Gibt an, dass dieser Vorgang alle Skript Versionen findet.</span><span class="sxs-lookup"><span data-stu-id="c9c69-136">Indicates that this operation finds all script versions.</span></span>

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

### <span data-ttu-id="c9c69-137">-Command</span><span class="sxs-lookup"><span data-stu-id="c9c69-137">-Command</span></span>

<span data-ttu-id="c9c69-138">Gibt ein Array von Befehlen an, die in Skripts zu finden sind.</span><span class="sxs-lookup"><span data-stu-id="c9c69-138">Specifies an array of commands to find in scripts.</span></span>
<span data-ttu-id="c9c69-139">Bei einem Befehl kann es sich um eine Funktion oder einen Workflow handeln.</span><span class="sxs-lookup"><span data-stu-id="c9c69-139">A command can be a function or workflow.</span></span>

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

### <span data-ttu-id="c9c69-140">-Credential</span><span class="sxs-lookup"><span data-stu-id="c9c69-140">-Credential</span></span>

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

### <span data-ttu-id="c9c69-141">-Filter</span><span class="sxs-lookup"><span data-stu-id="c9c69-141">-Filter</span></span>

<span data-ttu-id="c9c69-142">Findet Skripts basierend auf der anbieterspezifischen Such Syntax packagemanagement.</span><span class="sxs-lookup"><span data-stu-id="c9c69-142">Finds scripts based on the PackageManagement provider-specific search syntax.</span></span>

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

### <span data-ttu-id="c9c69-143">-Includababhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="c9c69-143">-IncludeDependencies</span></span>

<span data-ttu-id="c9c69-144">Gibt an, dass mit diesem Vorgang alle Skripts abgerufen werden, die von dem im *Name* -Parameter angegebenen Skript abhängig sind.</span><span class="sxs-lookup"><span data-stu-id="c9c69-144">Indicates that this operation gets all scripts that are dependent upon the script specified in the *Name* parameter.</span></span>

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

### <span data-ttu-id="c9c69-145">-Includes</span><span class="sxs-lookup"><span data-stu-id="c9c69-145">-Includes</span></span>

<span data-ttu-id="c9c69-146">Gibt den Typ des Get-Skripts an.</span><span class="sxs-lookup"><span data-stu-id="c9c69-146">Specifies type of script to get.</span></span>
<span data-ttu-id="c9c69-147">Die zulässigen Werte für diesen Parameter sind: function, Workflow.</span><span class="sxs-lookup"><span data-stu-id="c9c69-147">The acceptable values for this parameter are: Function, Workflow.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:
Accepted values: Function, Workflow

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c9c69-148">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="c9c69-148">-MaximumVersion</span></span>

<span data-ttu-id="c9c69-149">Gibt die maximale oder neueste Version des zu suchenden Skripts an.</span><span class="sxs-lookup"><span data-stu-id="c9c69-149">Specifies the maximum, or newest, version of the script to find.</span></span>
<span data-ttu-id="c9c69-150">Die Parameter " *MaximumVersion* " und "Requirements *dversion* " schließen sich gegenseitig aus. beide Parameter können nicht im selben Befehl verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c9c69-150">The *MaximumVersion* and *RequiredVersion* parameters are mutually exclusive; you cannot use both parameters in the same command.</span></span>

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

### <span data-ttu-id="c9c69-151">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="c9c69-151">-MinimumVersion</span></span>

<span data-ttu-id="c9c69-152">Gibt die Mindestversion des zu suchenden Skripts an.</span><span class="sxs-lookup"><span data-stu-id="c9c69-152">Specifies the minimum version of the script to find.</span></span>
<span data-ttu-id="c9c69-153">Die Parameter *MinimumVersion* und Requirements *dversion* schließen sich gegenseitig aus. beide Parameter können nicht im selben Befehl verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c9c69-153">The *MinimumVersion* and *RequiredVersion* parameters are mutually exclusive; you cannot use both parameters in the same command.</span></span>

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

### <span data-ttu-id="c9c69-154">-Name</span><span class="sxs-lookup"><span data-stu-id="c9c69-154">-Name</span></span>

<span data-ttu-id="c9c69-155">Gibt ein Array von Namen von Skripts an, die gesucht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="c9c69-155">Specifies an array of names of scripts to find.</span></span>

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

### <span data-ttu-id="c9c69-156">-Proxy</span><span class="sxs-lookup"><span data-stu-id="c9c69-156">-Proxy</span></span>

<span data-ttu-id="c9c69-157">Gibt einen Proxy Server für die Anforderung an, anstatt eine direkte Verbindung mit der Internet Ressource herzustellen.</span><span class="sxs-lookup"><span data-stu-id="c9c69-157">Specifies a proxy server for the request, rather than connecting directly to the Internet resource.</span></span>

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

### <span data-ttu-id="c9c69-158">-Proxy Credential</span><span class="sxs-lookup"><span data-stu-id="c9c69-158">-ProxyCredential</span></span>

<span data-ttu-id="c9c69-159">Gibt ein Benutzerkonto an, das über die Berechtigung zur Verwendung des Proxyservers verfügt, der durch den **Proxy**-Parameter angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="c9c69-159">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="c9c69-160">-Repository</span><span class="sxs-lookup"><span data-stu-id="c9c69-160">-Repository</span></span>

<span data-ttu-id="c9c69-161">Gibt den anzeigen Amen eines Repository an, das durch Ausführen von "Register-psrepository" registriert wurde.</span><span class="sxs-lookup"><span data-stu-id="c9c69-161">Specifies the friendly name of a repository that has been registered by running Register-PSRepository.</span></span>

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

### <span data-ttu-id="c9c69-162">-Requirements dversion</span><span class="sxs-lookup"><span data-stu-id="c9c69-162">-RequiredVersion</span></span>

<span data-ttu-id="c9c69-163">Gibt die genaue Versionsnummer des zu suchenden Skripts an.</span><span class="sxs-lookup"><span data-stu-id="c9c69-163">Specifies the exact version number of the script to find.</span></span>

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

### <span data-ttu-id="c9c69-164">-Tag</span><span class="sxs-lookup"><span data-stu-id="c9c69-164">-Tag</span></span>

<span data-ttu-id="c9c69-165">Gibt ein Array von-Tags an.</span><span class="sxs-lookup"><span data-stu-id="c9c69-165">Specifies an array of tags.</span></span>

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

### <span data-ttu-id="c9c69-166">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="c9c69-166">CommonParameters</span></span>

<span data-ttu-id="c9c69-167">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="c9c69-167">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="c9c69-168">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="c9c69-168">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="c9c69-169">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="c9c69-169">INPUTS</span></span>

### <span data-ttu-id="c9c69-170">System.String[]</span><span class="sxs-lookup"><span data-stu-id="c9c69-170">System.String[]</span></span>

### <span data-ttu-id="c9c69-171">System.String</span><span class="sxs-lookup"><span data-stu-id="c9c69-171">System.String</span></span>

### <span data-ttu-id="c9c69-172">System.Uri</span><span class="sxs-lookup"><span data-stu-id="c9c69-172">System.Uri</span></span>

### <span data-ttu-id="c9c69-173">System. Management. Automation. PSCredential</span><span class="sxs-lookup"><span data-stu-id="c9c69-173">System.Management.Automation.PSCredential</span></span>

## <span data-ttu-id="c9c69-174">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="c9c69-174">OUTPUTS</span></span>

### <span data-ttu-id="c9c69-175">PSRepositoryItemInfo</span><span class="sxs-lookup"><span data-stu-id="c9c69-175">PSRepositoryItemInfo</span></span>

## <span data-ttu-id="c9c69-176">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="c9c69-176">NOTES</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c9c69-177">Ab dem 2020 unterstützt die PowerShell-Katalog nicht mehr Transport Layer Security (TLS)-Versionen 1,0 und 1,1.</span><span class="sxs-lookup"><span data-stu-id="c9c69-177">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="c9c69-178">Wenn Sie TLS 1,2 oder höher nicht verwenden, erhalten Sie eine Fehlermeldung, wenn Sie versuchen, auf die PowerShell-Katalog zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="c9c69-178">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="c9c69-179">Verwenden Sie den folgenden Befehl, um sicherzustellen, dass Sie TLS 1,2 verwenden:</span><span class="sxs-lookup"><span data-stu-id="c9c69-179">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="c9c69-180">Weitere Informationen finden Sie in der [Ankündigung](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) im PowerShell-Blog.</span><span class="sxs-lookup"><span data-stu-id="c9c69-180">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="c9c69-181">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="c9c69-181">RELATED LINKS</span></span>

[<span data-ttu-id="c9c69-182">Install-Script</span><span class="sxs-lookup"><span data-stu-id="c9c69-182">Install-Script</span></span>](Install-Script.md)

[<span data-ttu-id="c9c69-183">Publish-Script</span><span class="sxs-lookup"><span data-stu-id="c9c69-183">Publish-Script</span></span>](Publish-Script.md)

[<span data-ttu-id="c9c69-184">Save-Script</span><span class="sxs-lookup"><span data-stu-id="c9c69-184">Save-Script</span></span>](Save-Script.md)

[<span data-ttu-id="c9c69-185">Uninstall-Script</span><span class="sxs-lookup"><span data-stu-id="c9c69-185">Uninstall-Script</span></span>](Uninstall-Script.md)

[<span data-ttu-id="c9c69-186">Update-Script</span><span class="sxs-lookup"><span data-stu-id="c9c69-186">Update-Script</span></span>](Update-Script.md)
