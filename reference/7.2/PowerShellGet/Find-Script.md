---
external help file: PSModule-help.xml
Locale: en-US
Module Name: PowerShellGet
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/powershellget/find-script?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Find-Script
ms.openlocfilehash: 8095c895f2c9645647f27e72cc95a502684950bf
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/19/2020
ms.locfileid: "99599833"
---
# <span data-ttu-id="4d179-102">Find-Script</span><span class="sxs-lookup"><span data-stu-id="4d179-102">Find-Script</span></span>

## <span data-ttu-id="4d179-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="4d179-103">SYNOPSIS</span></span>
<span data-ttu-id="4d179-104">Sucht nach einem Skript.</span><span class="sxs-lookup"><span data-stu-id="4d179-104">Finds a script.</span></span>

## <span data-ttu-id="4d179-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="4d179-105">SYNTAX</span></span>

```
Find-Script [[-Name] <String[]>] [-MinimumVersion <String>] [-MaximumVersion <String>]
 [-RequiredVersion <String>] [-AllVersions] [-IncludeDependencies] [-Filter <String>] [-Tag <String[]>]
 [-Includes <String[]>] [-Command <String[]>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-Repository <String[]>] [-Credential <PSCredential>] [-AllowPrerelease] [<CommonParameters>]
```

## <span data-ttu-id="4d179-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="4d179-106">DESCRIPTION</span></span>

<span data-ttu-id="4d179-107">Das Cmdlet " **Find-Script** " findet ein bestimmtes Skript in registrierten Depots.</span><span class="sxs-lookup"><span data-stu-id="4d179-107">The **Find-Script** cmdlet finds a specified script in registered repositories.</span></span>

## <span data-ttu-id="4d179-108">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="4d179-108">EXAMPLES</span></span>

### <span data-ttu-id="4d179-109">Beispiel 1: Suchen aller verfügbaren Skripts</span><span class="sxs-lookup"><span data-stu-id="4d179-109">Example 1: Find all available scripts</span></span>

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

<span data-ttu-id="4d179-110">Dieser Befehl sucht nach allen verfügbaren Skripts.</span><span class="sxs-lookup"><span data-stu-id="4d179-110">This command finds all available scripts.</span></span>

### <span data-ttu-id="4d179-111">Beispiel 2: Suchen eines Skripts anhand des Namens</span><span class="sxs-lookup"><span data-stu-id="4d179-111">Example 2: Find a script by name</span></span>

```
PS C:\> Find-Script -Name "Start-WFContosoServer"
Version    Name                                Type       Repository           Description
-------    ----                                ----       ----------           -----------
2.0        Start-WFContosoServer               Script     LocalRepo1           Start-WFContosoServer Script example
```

<span data-ttu-id="4d179-112">Mit diesem Befehl wird das Skript "Start-WF condesoserver" gefunden.</span><span class="sxs-lookup"><span data-stu-id="4d179-112">This command find the script named Start-WFContosoServer.</span></span>

### <span data-ttu-id="4d179-113">Beispiel 3: Suchen eines Skripts anhand des Namens, der erforderlichen Version und aus einem angegebenen Repository</span><span class="sxs-lookup"><span data-stu-id="4d179-113">Example 3: Find a script by name, required version, and from a specified repository</span></span>

```
PS C:\> Find-Script -Name "Required-Script2" -RequiredVersion 2.0 -Repository "LocalRepo01"
```

<span data-ttu-id="4d179-114">Mit diesem Befehl wird ein Skript mit dem Namen und der erforderlichen Version im LocalRepo01-Repository gefunden.</span><span class="sxs-lookup"><span data-stu-id="4d179-114">This command finds a script by name and required version in the LocalRepo01 repository.</span></span>

### <span data-ttu-id="4d179-115">Beispiel 4: Suchen eines Skripts und Formatieren der Ausgabe als Liste</span><span class="sxs-lookup"><span data-stu-id="4d179-115">Example 4: Find a script and format the output as a list</span></span>

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

<span data-ttu-id="4d179-116">Dieser Befehl sucht nach Required-Script2 im Repository LocalRepo1 und übergibt dann das resultierende **PSRepositoryItemInfo** -Objekt an das Format-List-Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="4d179-116">This command finds Required-Script2 in the LocalRepo1 repository, and then passes the resulting **PSRepositoryItemInfo** object to the Format-List cmdlet.</span></span>

### <span data-ttu-id="4d179-117">Beispiel 5: Suchen eines Skripts im angegebenen Versions Bereich</span><span class="sxs-lookup"><span data-stu-id="4d179-117">Example 5: Find a script in the specified version range</span></span>

```
PS C:\> Find-Script -Name "Required-Script2" -MinimumVersion 2.1 -MaximumVersion 2.5 -Repository "LocalRepo1"
Version    Name                                Type       Repository           Description
-------    ----                                ----       ----------           -----------
2.5        Required-Script2                    Script     LocalRepo1           Description for the Required-Script2 script
```

<span data-ttu-id="4d179-118">Dieser Befehl sucht alle Versionen von RequiredScript2 zwischen den Versionen 2,1 und 2,5 im LocalRepo1-Respository.</span><span class="sxs-lookup"><span data-stu-id="4d179-118">This command finds all versions of RequiredScript2 between versions 2.1 and 2.5 in the LocalRepo1 respository.</span></span>

### <span data-ttu-id="4d179-119">Beispiel 6: Suchen aller Versionen eines Skripts</span><span class="sxs-lookup"><span data-stu-id="4d179-119">Example 6: Find all versions of a script</span></span>

```
PS C:\> Find-Script -Name "Required-Script02" -AllVersions
Version    Name                                Type       Repository           Description
-------    ----                                ----       ----------           -----------
1.0        Required-Script2                    Script     LocalRepo1           Description for the Required-Script2 script
1.5        Required-Script2                    Script     LocalRepo1           Description for the Required-Script2 script
2.0        Required-Script2                    Script     LocalRepo1           Description for the Required-Script2 script
2.5        Required-Script2                    Script     LocalRepo1           Description for the Required-Script2 script
```

<span data-ttu-id="4d179-120">Mit diesem Befehl werden alle Versionen von required-Script02 gefunden.</span><span class="sxs-lookup"><span data-stu-id="4d179-120">This command finds all versions of Required-Script02.</span></span>

### <span data-ttu-id="4d179-121">Beispiel 7: Suchen eines Skripts und seiner Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="4d179-121">Example 7: Find a script and its dependencies</span></span>

```
PS C:\> Find-Script -Name "Script-WithDependencies1" -IncludeDependencies -Repository "LocalRepo1"
Version    Name                                Type       Repository           Description
-------    ----                                ----       ----------           -----------
1.0        Script-WithDependencies1            Script     LocalRepo1           Description for the Script-WithDependencies1 script
2.0        RequiredModule3                     Script     LocalRepo1           RequiredModule3 module
2.5        Required-Script1                    Script     LocalRepo1           Description for the Required-Script1 script
2.5        Required-Script2                    Script     LocalRepo1           Description for the Required-Script2 script
```

<span data-ttu-id="4d179-122">Mit diesem Befehl wird ein Skript und seine Abhängigkeiten gefunden.</span><span class="sxs-lookup"><span data-stu-id="4d179-122">This command finds a script and its dependencies.</span></span>

### <span data-ttu-id="4d179-123">Beispiel 8: Suchen nach Skripts mit dem angegebenen Tag</span><span class="sxs-lookup"><span data-stu-id="4d179-123">Example 8: Find scripts with the specified tag</span></span>

```
PS C:\> Find-Script -Tag "Tag1" -Repository "LocalRepo1"
Version    Name                                Type       Repository           Description
-------    ----                                ----       ----------           -----------
1.0        Fabrikam-ClientScript               Script     LocalRepo1           Description for the Fabrikam-ClientScript script
```

<span data-ttu-id="4d179-124">Dieser Befehl findet Skripts, die das Tag Tag1 im LocalRepo1-Repository enthalten.</span><span class="sxs-lookup"><span data-stu-id="4d179-124">This command finds scripts that have the tag Tag1 in the LocalRepo1 repository</span></span>

### <span data-ttu-id="4d179-125">Beispiel 9: Suchen nach Skripts mit dem angegebenen Befehlsnamen</span><span class="sxs-lookup"><span data-stu-id="4d179-125">Example 9: Find scripts with specified command name</span></span>

```
PS C:\> Find-Script -Command Test-FunctionFromScript_Required-Script3 -Repository "LocalRepo1"
Version    Name                                Type       Repository           Description
-------    ----                                ----       ----------           -----------
2.5        Required-Script3                    Script     LocalRepo1           Description for the Required-Script3 script
```

<span data-ttu-id="4d179-126">Mit diesem Befehl wird ein Skript gefunden, das den angegebenen Befehlsnamen enthält.</span><span class="sxs-lookup"><span data-stu-id="4d179-126">This command finds a script that contains the specified command name.</span></span>

### <span data-ttu-id="4d179-127">Beispiel 10: Suchen nach Skripts mit Workflows</span><span class="sxs-lookup"><span data-stu-id="4d179-127">Example 10: Find scripts with workflows</span></span>

```
PS C:\> Find-Script -Includes "Workflow" -Repository "LocalRepo1"
Version    Name                                Type       Repository           Description
-------    ----                                ----       ----------           -----------
2.5        Fabrikam-ClientScript               Script     LocalRepo1           Description for the Fabrikam-ClientScript script
1.0        Fabrikam-Script                     Script     LocalRepo1           Description for the Fabrikam-Script script
```

<span data-ttu-id="4d179-128">Dieser Befehl findet Workflow Skripts im LocalRepo1-Repository.</span><span class="sxs-lookup"><span data-stu-id="4d179-128">This command finds workflow scripts in the LocalRepo1 repository.</span></span>

### <span data-ttu-id="4d179-129">Beispiel 11: Suchen nach Skripts mit Platzhaltern</span><span class="sxs-lookup"><span data-stu-id="4d179-129">Example 11: Find scripts using wildcards</span></span>

```
PS C:\> Find-Script -Name "Required-Script*" -Repository "LocalRepo1"
Version    Name                                Type       Repository           Description
-------    ----                                ----       ----------           -----------
2.5        Required-Script1                    Script     local1               Description for the Required-Script1 script
2.5        Required-Script2                    Script     local1               Description for the Required-Script2 script
2.5        Required-Script3                    Script     local1               Description for the Required-Script3 script
```

<span data-ttu-id="4d179-130">Dieser Befehl verwendet das Platzhalter Zeichen (\*), um nach Skripts zu suchen, die mit "required-Script" beginnen.</span><span class="sxs-lookup"><span data-stu-id="4d179-130">This command uses the wildcard character (\*) to find scripts that begin with Required-Script.</span></span>

## <span data-ttu-id="4d179-131">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="4d179-131">PARAMETERS</span></span>

### <span data-ttu-id="4d179-132">-Allowprerelease</span><span class="sxs-lookup"><span data-stu-id="4d179-132">-AllowPrerelease</span></span>

<span data-ttu-id="4d179-133">Schließt in die als Vorabversion markierten Ergebnisskripts ein.</span><span class="sxs-lookup"><span data-stu-id="4d179-133">Includes in the results scripts marked as a prerelease.</span></span>

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

### <span data-ttu-id="4d179-134">-Allversions</span><span class="sxs-lookup"><span data-stu-id="4d179-134">-AllVersions</span></span>

<span data-ttu-id="4d179-135">Gibt an, dass dieser Vorgang alle Skript Versionen findet.</span><span class="sxs-lookup"><span data-stu-id="4d179-135">Indicates that this operation finds all script versions.</span></span>

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

### <span data-ttu-id="4d179-136">-Command</span><span class="sxs-lookup"><span data-stu-id="4d179-136">-Command</span></span>

<span data-ttu-id="4d179-137">Gibt ein Array von Befehlen an, die in Skripts zu finden sind.</span><span class="sxs-lookup"><span data-stu-id="4d179-137">Specifies an array of commands to find in scripts.</span></span>
<span data-ttu-id="4d179-138">Bei einem Befehl kann es sich um eine Funktion oder einen Workflow handeln.</span><span class="sxs-lookup"><span data-stu-id="4d179-138">A command can be a function or workflow.</span></span>

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

### <span data-ttu-id="4d179-139">-Credential</span><span class="sxs-lookup"><span data-stu-id="4d179-139">-Credential</span></span>

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

### <span data-ttu-id="4d179-140">-Filter</span><span class="sxs-lookup"><span data-stu-id="4d179-140">-Filter</span></span>

<span data-ttu-id="4d179-141">Findet Skripts basierend auf der anbieterspezifischen Such Syntax packagemanagement.</span><span class="sxs-lookup"><span data-stu-id="4d179-141">Finds scripts based on the PackageManagement provider-specific search syntax.</span></span>

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

### <span data-ttu-id="4d179-142">-Includababhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="4d179-142">-IncludeDependencies</span></span>

<span data-ttu-id="4d179-143">Gibt an, dass mit diesem Vorgang alle Skripts abgerufen werden, die von dem im *Name* -Parameter angegebenen Skript abhängig sind.</span><span class="sxs-lookup"><span data-stu-id="4d179-143">Indicates that this operation gets all scripts that are dependent upon the script specified in the *Name* parameter.</span></span>

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

### <span data-ttu-id="4d179-144">-Includes</span><span class="sxs-lookup"><span data-stu-id="4d179-144">-Includes</span></span>

<span data-ttu-id="4d179-145">Gibt den Typ des Get-Skripts an.</span><span class="sxs-lookup"><span data-stu-id="4d179-145">Specifies type of script to get.</span></span>
<span data-ttu-id="4d179-146">Die zulässigen Werte für diesen Parameter sind: function, Workflow.</span><span class="sxs-lookup"><span data-stu-id="4d179-146">The acceptable values for this parameter are: Function, Workflow.</span></span>

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

### <span data-ttu-id="4d179-147">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="4d179-147">-MaximumVersion</span></span>

<span data-ttu-id="4d179-148">Gibt die maximale oder neueste Version des zu suchenden Skripts an.</span><span class="sxs-lookup"><span data-stu-id="4d179-148">Specifies the maximum, or newest, version of the script to find.</span></span>
<span data-ttu-id="4d179-149">Die Parameter " *MaximumVersion* " und "Requirements *dversion* " schließen sich gegenseitig aus. beide Parameter können nicht im selben Befehl verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4d179-149">The *MaximumVersion* and *RequiredVersion* parameters are mutually exclusive; you cannot use both parameters in the same command.</span></span>

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

### <span data-ttu-id="4d179-150">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="4d179-150">-MinimumVersion</span></span>

<span data-ttu-id="4d179-151">Gibt die Mindestversion des zu suchenden Skripts an.</span><span class="sxs-lookup"><span data-stu-id="4d179-151">Specifies the minimum version of the script to find.</span></span>
<span data-ttu-id="4d179-152">Die Parameter *MinimumVersion* und Requirements *dversion* schließen sich gegenseitig aus. beide Parameter können nicht im selben Befehl verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4d179-152">The *MinimumVersion* and *RequiredVersion* parameters are mutually exclusive; you cannot use both parameters in the same command.</span></span>

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

### <span data-ttu-id="4d179-153">-Name</span><span class="sxs-lookup"><span data-stu-id="4d179-153">-Name</span></span>

<span data-ttu-id="4d179-154">Gibt ein Array von Namen von Skripts an, die gesucht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="4d179-154">Specifies an array of names of scripts to find.</span></span>

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

### <span data-ttu-id="4d179-155">-Proxy</span><span class="sxs-lookup"><span data-stu-id="4d179-155">-Proxy</span></span>

<span data-ttu-id="4d179-156">Gibt einen Proxy Server für die Anforderung an, anstatt eine direkte Verbindung mit der Internet Ressource herzustellen.</span><span class="sxs-lookup"><span data-stu-id="4d179-156">Specifies a proxy server for the request, rather than connecting directly to the Internet resource.</span></span>

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

### <span data-ttu-id="4d179-157">-Proxy Credential</span><span class="sxs-lookup"><span data-stu-id="4d179-157">-ProxyCredential</span></span>

<span data-ttu-id="4d179-158">Gibt ein Benutzerkonto an, das über die Berechtigung zur Verwendung des Proxyservers verfügt, der durch den **Proxy**-Parameter angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="4d179-158">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="4d179-159">-Repository</span><span class="sxs-lookup"><span data-stu-id="4d179-159">-Repository</span></span>

<span data-ttu-id="4d179-160">Gibt den anzeigen Amen eines Repository an, das durch Ausführen von "Register-psrepository" registriert wurde.</span><span class="sxs-lookup"><span data-stu-id="4d179-160">Specifies the friendly name of a repository that has been registered by running Register-PSRepository.</span></span>

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

### <span data-ttu-id="4d179-161">-Requirements dversion</span><span class="sxs-lookup"><span data-stu-id="4d179-161">-RequiredVersion</span></span>

<span data-ttu-id="4d179-162">Gibt die genaue Versionsnummer des zu suchenden Skripts an.</span><span class="sxs-lookup"><span data-stu-id="4d179-162">Specifies the exact version number of the script to find.</span></span>

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

### <span data-ttu-id="4d179-163">-Tag</span><span class="sxs-lookup"><span data-stu-id="4d179-163">-Tag</span></span>

<span data-ttu-id="4d179-164">Gibt ein Array von-Tags an.</span><span class="sxs-lookup"><span data-stu-id="4d179-164">Specifies an array of tags.</span></span>

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

### <span data-ttu-id="4d179-165">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="4d179-165">CommonParameters</span></span>

<span data-ttu-id="4d179-166">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="4d179-166">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="4d179-167">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="4d179-167">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="4d179-168">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="4d179-168">INPUTS</span></span>

### <span data-ttu-id="4d179-169">System.String[]</span><span class="sxs-lookup"><span data-stu-id="4d179-169">System.String[]</span></span>

### <span data-ttu-id="4d179-170">System.String</span><span class="sxs-lookup"><span data-stu-id="4d179-170">System.String</span></span>

### <span data-ttu-id="4d179-171">System.Uri</span><span class="sxs-lookup"><span data-stu-id="4d179-171">System.Uri</span></span>

### <span data-ttu-id="4d179-172">System. Management. Automation. PSCredential</span><span class="sxs-lookup"><span data-stu-id="4d179-172">System.Management.Automation.PSCredential</span></span>

## <span data-ttu-id="4d179-173">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="4d179-173">OUTPUTS</span></span>

### <span data-ttu-id="4d179-174">PSRepositoryItemInfo</span><span class="sxs-lookup"><span data-stu-id="4d179-174">PSRepositoryItemInfo</span></span>

## <span data-ttu-id="4d179-175">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="4d179-175">NOTES</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4d179-176">Ab April 2020 unterstützt der PowerShell-Katalog die TLS-Versionen (Transport Layer Security) 1.0 und 1.1 nicht mehr.</span><span class="sxs-lookup"><span data-stu-id="4d179-176">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="4d179-177">Wenn Sie nicht TLS 1.2 oder höher verwenden, erhalten Sie beim Versuch des Zugriffs auf den PowerShell-Katalog eine Fehlermeldung.</span><span class="sxs-lookup"><span data-stu-id="4d179-177">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="4d179-178">Mit dem folgenden Befehl können Sie sicherstellen, dass Sie TLS 1.2 verwenden:</span><span class="sxs-lookup"><span data-stu-id="4d179-178">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="4d179-179">Weitere Informationen finden Sie im PowerShell-Blog in der [Ankündigung](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/).</span><span class="sxs-lookup"><span data-stu-id="4d179-179">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="4d179-180">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="4d179-180">RELATED LINKS</span></span>

[<span data-ttu-id="4d179-181">Install-Script</span><span class="sxs-lookup"><span data-stu-id="4d179-181">Install-Script</span></span>](Install-Script.md)

[<span data-ttu-id="4d179-182">Publish-Script</span><span class="sxs-lookup"><span data-stu-id="4d179-182">Publish-Script</span></span>](Publish-Script.md)

[<span data-ttu-id="4d179-183">Save-Script</span><span class="sxs-lookup"><span data-stu-id="4d179-183">Save-Script</span></span>](Save-Script.md)

[<span data-ttu-id="4d179-184">Uninstall-Script</span><span class="sxs-lookup"><span data-stu-id="4d179-184">Uninstall-Script</span></span>](Uninstall-Script.md)

[<span data-ttu-id="4d179-185">Update-Script</span><span class="sxs-lookup"><span data-stu-id="4d179-185">Update-Script</span></span>](Update-Script.md)
