---
external help file: PSModule-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PowerShellGet
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/powershellget/install-script?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Install-Script
ms.openlocfilehash: c8191f8b5bbf6337fdc11dc3d15774991029151b
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/19/2020
ms.locfileid: "94891191"
---
# <span data-ttu-id="d8772-103">Install-Script</span><span class="sxs-lookup"><span data-stu-id="d8772-103">Install-Script</span></span>

## <span data-ttu-id="d8772-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="d8772-104">SYNOPSIS</span></span>
<span data-ttu-id="d8772-105">Installiert ein Skript.</span><span class="sxs-lookup"><span data-stu-id="d8772-105">Installs a script.</span></span>

## <span data-ttu-id="d8772-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d8772-106">SYNTAX</span></span>

### <span data-ttu-id="d8772-107">Nameparameterset (Standard)</span><span class="sxs-lookup"><span data-stu-id="d8772-107">NameParameterSet (Default)</span></span>

```
Install-Script [-Name] <String[]> [-MinimumVersion <String>] [-MaximumVersion <String>]
 [-RequiredVersion <String>] [-Repository <String[]>] [-Scope <String>] [-NoPathUpdate]
 [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-Credential <PSCredential>] [-Force]
 [-AllowPrerelease] [-AcceptLicense] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="d8772-108">InputObject</span><span class="sxs-lookup"><span data-stu-id="d8772-108">InputObject</span></span>

```
Install-Script [-InputObject] <PSObject[]> [-Scope <String>] [-NoPathUpdate] [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-Credential <PSCredential>] [-Force] [-AcceptLicense]
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="d8772-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d8772-109">DESCRIPTION</span></span>

<span data-ttu-id="d8772-110">Das- `Install-Script` Cmdlet ruft eine Skript Nutzlast aus einem Repository ab, überprüft, ob die Nutzlast ein gültiges PowerShell-Skript ist, und kopiert die Skriptdatei an einen angegebenen Installations Speicherort.</span><span class="sxs-lookup"><span data-stu-id="d8772-110">The `Install-Script` cmdlet acquires a script payload from a repository, verifies that the payload is a valid PowerShell script, and copies the script file to a specified installation location.</span></span>

<span data-ttu-id="d8772-111">Die standardrepositorys `Install-Script` können mit den `Register-PSRepository` `Set-PSRepository` `Unregister-PSRepository` Cmdlets,, und konfiguriert werden `Get-PSRepository` .</span><span class="sxs-lookup"><span data-stu-id="d8772-111">The default repositories `Install-Script` operates against are configurable through the `Register-PSRepository`, `Set-PSRepository`, `Unregister-PSRepository`, and `Get-PSRepository` cmdlets.</span></span> <span data-ttu-id="d8772-112">Wenn Sie mit mehreren Depots arbeiten, wird `Install-Script` das erste Skript, das den angegebenen Suchkriterien (**Name**, **MinimumVersion** oder **MaximumVersion**) entspricht, aus dem ersten Repository ohne Fehler installiert.</span><span class="sxs-lookup"><span data-stu-id="d8772-112">When operating against multiple repositories, `Install-Script` installs the first script that matches the specified search criteria (**Name**, **MinimumVersion**, or **MaximumVersion**) from the first repository without any error.</span></span>

## <span data-ttu-id="d8772-113">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="d8772-113">EXAMPLES</span></span>

### <span data-ttu-id="d8772-114">Beispiel 1: Suchen eines Skripts und Installieren des Skripts</span><span class="sxs-lookup"><span data-stu-id="d8772-114">Example 1: Find a script and install it</span></span>

```
PS C:\> Find-Script -Repository "Local1" -Name "Required-Script2"
Version    Name                           Type       Repository           Description
-------    ----                           ----       ----------           -----------
2.5        Required-Script2               Script     local1               Description for the Required-Script2 script

PS C:\> Find-Script -Repository "Local1" -Name "Required-Script2" | Install-Script
PS C:\> Get-Command -Name "Required-Script2"
CommandType     Name                      Version    Source
-----------     ----                      -------    ------
ExternalScript  Required-Script2.ps1      2.0       C:\Users\pattif\Documents\WindowsPowerShell\Scripts\Required-Script2.ps1

PS C:\> Get-InstalledScript -Name "Required-Script2"
Version    Name                  Type     Repository           Description
-------    ----                  ----     ----------           -----------
2.5        Required-Script2      Script   local1               Description for the Required-Script2 script

PS C:\> Get-InstalledScript -Name "Required-Script2" | Format-List *
Name                       : Required-Script2
Version                    : 2.5
Type                       : Script
Description                : Description for the Required-Script2 script
Author                     : pattif
CompanyName                :
Copyright                  : 2015 Microsoft Corporation. All rights reserved.
PublishedDate              : 8/15/2015 12:42:39 AM
LicenseUri                 : http://required-script2.com/license
ProjectUri                 : http://required-script2.com/
IconUri                    : http://required-script2.com/icon
Tags                       : {Tag1, Tag2, Tag-Required-Script2-2.5, PSScript...}
Includes                   : {Function, DscResource, Cmdlet, Command}
PowerShellGetFormatVersion :
ReleaseNotes               : Required-Script2 release notes
Dependencies               : {}
RepositorySourceLocation   : http://pattif-dev:8765/api/v2/
Repository                 : local1
PackageManagementProvider  : NuGet
InstalledLocation          : C:\Users\pattif\Documents\WindowsPowerShell\Scripts
```

<span data-ttu-id="d8772-115">Der erste Befehl sucht das Skript `Required-Script2` aus dem local1-Repository und zeigt die Ergebnisse an.</span><span class="sxs-lookup"><span data-stu-id="d8772-115">The first command finds the script named `Required-Script2` from the Local1 repository and displays the results.</span></span>

<span data-ttu-id="d8772-116">Mit dem zweiten Befehl `Required-Script2` wird das Skript gefunden und dann mithilfe des Pipeline Operators an das `Install-Script` Cmdlet übergeben, um es zu installieren.</span><span class="sxs-lookup"><span data-stu-id="d8772-116">The second command finds the `Required-Script2` script, and then uses the pipeline operator to pass it to the `Install-Script` cmdlet to install it.</span></span>

<span data-ttu-id="d8772-117">Der dritte Befehl verwendet das `Get-Command` Cmdlet, um die Ergebnisse zu erhalten `Required-Script2` , und zeigt dann die Ergebnisse an.</span><span class="sxs-lookup"><span data-stu-id="d8772-117">The third command uses the `Get-Command` cmdlet to get `Required-Script2`, and then displays the results.</span></span>

<span data-ttu-id="d8772-118">Der vierte Befehl verwendet das `Get-InstalledScript` Cmdlet, um `Required-Script2` die Ergebnisse zu erhalten und anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="d8772-118">The fourth command uses the `Get-InstalledScript` cmdlet to get `Required-Script2` and display the results.</span></span>

<span data-ttu-id="d8772-119">Mit dem fünften Befehl wird `Required-Script2` der Pipeline Operator abgerufen und verwendet, um ihn an das `Format-List` Cmdlet zu übergeben, um die Ausgabe zu formatieren.</span><span class="sxs-lookup"><span data-stu-id="d8772-119">The fifth command gets `Required-Script2` and uses the pipeline operator to pass it to the `Format-List` cmdlet to format the output.</span></span>

### <span data-ttu-id="d8772-120">Beispiel 2: Installieren eines Skripts mit dem Bereich "ALLUSERS"</span><span class="sxs-lookup"><span data-stu-id="d8772-120">Example 2: Install a script with AllUsers scope</span></span>

```
PS C:\> Install-Script -Repository "Local1" -Name "Required-Script3" -Scope "AllUsers"
PS C:\> Get-InstalledScript -Name "Required-Script3"
Version    Name                  Type       Repository    Description
-------    ----                  ----       ----------    -----------
2.5        Required-Script3      Script     local1        Description for the Required-Script3 script

PS C:\> Get-InstalledScript -Name "Required-Script3" | Format-List *
Name                       : Required-Script3
Version                    : 2.5
Type                       : Script
Description                : Description for the Required-Script3 script
Author                     : pattif
CompanyName                :
Copyright                  : 2015 Microsoft Corporation. All rights reserved.
PublishedDate              : 8/15/2015 12:42:45 AM
LicenseUri                 : http://required-script3.com/license
ProjectUri                 : http://required-script3.com/
IconUri                    : http://required-script3.com/icon
Tags                       : {Tag1, Tag2, Tag-Required-Script3-2.5, PSScript...}
Includes                   : {Function, DscResource, Cmdlet, Command}
PowerShellGetFormatVersion :
ReleaseNotes               : Required-Script3 release notes
Dependencies               : {}
RepositorySourceLocation   : http://pattif-dev:8765/api/v2/
Repository                 : local1
PackageManagementProvider  : NuGet
InstalledLocation          : C:\Program Files\WindowsPowerShell\Scripts
```

<span data-ttu-id="d8772-121">Der erste Befehl installiert das Skript mit dem Namen `Required-Script3` und weist es dem Bereich "ALLUSERS" zu.</span><span class="sxs-lookup"><span data-stu-id="d8772-121">The first command installs the script named `Required-Script3` and assigns it AllUsers scope.</span></span>

<span data-ttu-id="d8772-122">Mit dem zweiten Befehl wird das installierte Skript abgerufen `Required-Script3` und Informationen darüber angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d8772-122">The second command gets the installed script `Required-Script3` and displays information about it.</span></span>

<span data-ttu-id="d8772-123">Der dritte Befehl ruft `Required-Script3` den Pipeline Operator ab und verwendet ihn, um ihn an das `Format-List` Cmdlet zu übergeben, um die Ausgabe zu formatieren.</span><span class="sxs-lookup"><span data-stu-id="d8772-123">The third command gets `Required-Script3` and uses the pipeline operator to pass it to the `Format-List` cmdlet to format the output.</span></span>

### <span data-ttu-id="d8772-124">Beispiel 3: Installieren eines Skripts und seiner Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="d8772-124">Example 3: Install a script and its dependencies</span></span>

```
PS C:\> Find-Script -Repository "Local1" -Name "Script-WithDependencies2" -IncludeDependencies
Version    Name                        Type       Repository    Description
-------    ----                        ----       ----------    -----------
2.0        Script-WithDependencies2    Script     local1        Description for the Script-WithDependencies2 script
2.5        RequiredModule1             Module     local1        RequiredModule1 module
2.5        RequiredModule2             Module     local1        RequiredModule2 module
2.5        RequiredModule3             Module     local1        RequiredModule3 module
2.5        Required-Script1            Script     local1        Description for the Required-Script1 script
2.5        Required-Script2            Script     local1        Description for the Required-Script2 script
2.5        Required-Script3            Script     local1        Description for the Required-Script3 script

PS C:\> Install-Script -Repository "Local1" -Name "Script-WithDependencies2"
PS C:\> Get-InstalledScript
Version    Name                        Type       Repository    Description
-------    ----                        ----       ----------    -----------
2.5        Required-Script1            Script     local1        Description for the Required-Script1 script
2.5        Required-Script2            Script     local1        Description for the Required-Script2 script
2.5        Required-Script3            Script     local1        Description for the Required-Script3 script
2.0        Script-WithDependencies2    Script     local1        Description for the Script-WithDependencies2 script

PS C:\> Get-InstalledModule
Version    Name                        Type       Repository    Description
-------    ----                        ----       ----------    -----------
2.5        RequiredModule1             Module     local1        RequiredModule1 module
2.5        RequiredModule2             Module     local1        RequiredModule2 module
2.5        RequiredModule3             Module     local1        RequiredModule3 module

PS C:\> Find-Script -Repository "Local1" -Name "Required-Script*"
Version    Name                        Type       Repository    Description
-------    ----                        ----       ----------    -----------
2.5        Required-Script1            Script     local1        Description for the Required-Script1 script
2.5        Required-Script2            Script     local1        Description for the Required-Script2 script
2.5        Required-Script3            Script     local1        Description for the Required-Script3 script

PS C:\> Install-Script -Repository "Local1" -Name "Required-Script*"
PS C:\> Get-InstalledScript
Version    Name                        Type       Repository    Description
-------    ----                        ----       ----------    -----------
2.5        Required-Script1            Script     local1        Description for the Required-Script1 script
2.5        Required-Script2            Script     local1        Description for the Required-Script2 script
2.5        Required-Script3            Script     local1        Description for the Required-Script3 script
```

<span data-ttu-id="d8772-125">Der erste Befehl sucht das Skript `Script-WithDependencies2` und seine Abhängigkeiten im Repository local1 und zeigt die Ergebnisse an.</span><span class="sxs-lookup"><span data-stu-id="d8772-125">The first command finds the script named `Script-WithDependencies2` and its dependencies in the Local1 repository and displays the results.</span></span>

<span data-ttu-id="d8772-126">Mit dem zweiten Befehl wird installiert `Script-WithDependencies2` .</span><span class="sxs-lookup"><span data-stu-id="d8772-126">The second command installs `Script-WithDependencies2`.</span></span>

<span data-ttu-id="d8772-127">Der dritte Befehl verwendet das `Get-InstalledScript` Script-Cmdlet, um installierte Skripts zu erhalten und die Ergebnisse anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="d8772-127">The third command uses the `Get-InstalledScript` script cmdlet to get installed scripts and display the results.</span></span>

<span data-ttu-id="d8772-128">Der vierte Befehl verwendet das `Get-InstalledModule` Cmdlet, um installierte Module zu erhalten und die Ergebnisse anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="d8772-128">The fourth command uses the `Get-InstalledModule` cmdlet to get installed modules and display the results.</span></span>

<span data-ttu-id="d8772-129">Der fünfte Befehl verwendet das `Find-Script` Cmdlet, um Skripts zu suchen, bei denen der Name mit beginnt, `Required-Script` und zeigt die Ergebnisse an.</span><span class="sxs-lookup"><span data-stu-id="d8772-129">The fifth command uses the `Find-Script` cmdlet to find scripts where the name begins with `Required-Script` and display the results.</span></span>

<span data-ttu-id="d8772-130">Der sechste Befehl installiert die Skripts, bei denen der Name mit beginnt, `Required-Script` im local1-Repository.</span><span class="sxs-lookup"><span data-stu-id="d8772-130">The sixth command installs the scripts where the name begins with `Required-Script` in the Local1 repository.</span></span>

<span data-ttu-id="d8772-131">Der letzte Befehl ruft installierte Skripts ab und zeigt die Ergebnisse an.</span><span class="sxs-lookup"><span data-stu-id="d8772-131">The final command gets installed scripts and displays the results.</span></span>

## <span data-ttu-id="d8772-132">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d8772-132">PARAMETERS</span></span>

### <span data-ttu-id="d8772-133">-AcceptLicense</span><span class="sxs-lookup"><span data-stu-id="d8772-133">-AcceptLicense</span></span>

<span data-ttu-id="d8772-134">Akzeptieren Sie den Lizenzvertrag während der Installation automatisch, wenn dies für das Modul erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="d8772-134">Automatically accept the license agreement during installation if the module requires it.</span></span>

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

### <span data-ttu-id="d8772-135">-Allowprerelease</span><span class="sxs-lookup"><span data-stu-id="d8772-135">-AllowPrerelease</span></span>

<span data-ttu-id="d8772-136">Ermöglicht das Installieren eines als Vorabversion markierten Skripts.</span><span class="sxs-lookup"><span data-stu-id="d8772-136">Allows you to install a script marked as a prerelease.</span></span>

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

### <span data-ttu-id="d8772-137">-Confirm</span><span class="sxs-lookup"><span data-stu-id="d8772-137">-Confirm</span></span>

<span data-ttu-id="d8772-138">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="d8772-138">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="d8772-139">-Credential</span><span class="sxs-lookup"><span data-stu-id="d8772-139">-Credential</span></span>

<span data-ttu-id="d8772-140">Gibt ein Benutzerkonto an, das über Rechte zum Installieren eines Skripts für einen angegebenen Paketanbieter oder eine angegebene Quelle verfügt.</span><span class="sxs-lookup"><span data-stu-id="d8772-140">Specifies a user account that has rights to install a script for a specified package provider or source.</span></span>

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

### <span data-ttu-id="d8772-141">-Force</span><span class="sxs-lookup"><span data-stu-id="d8772-141">-Force</span></span>

<span data-ttu-id="d8772-142">Erzwingt die Ausführung des Befehls ohne Aufforderung zur Bestätigung durch den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="d8772-142">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="d8772-143">-InputObject</span><span class="sxs-lookup"><span data-stu-id="d8772-143">-InputObject</span></span>

<span data-ttu-id="d8772-144">Wird für Pipeline Eingaben verwendet.</span><span class="sxs-lookup"><span data-stu-id="d8772-144">Used for pipeline input.</span></span>

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

### <span data-ttu-id="d8772-145">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="d8772-145">-MaximumVersion</span></span>

<span data-ttu-id="d8772-146">Gibt die maximale Version eines einzelnen Skripts an, das installiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="d8772-146">Specifies the maximum version of a single scripts to install.</span></span> <span data-ttu-id="d8772-147">Sie können diesen Parameter nicht hinzufügen, wenn Sie versuchen, mehrere Skripts zu installieren.</span><span class="sxs-lookup"><span data-stu-id="d8772-147">You cannot add this parameter if you are attempting to install multiple scripts.</span></span> <span data-ttu-id="d8772-148">Die Parameter " **MaximumVersion** " und "Requirements **dversion** " schließen sich gegenseitig aus. beide Parameter können nicht im selben Befehl verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d8772-148">The **MaximumVersion** and the **RequiredVersion** parameters are mutually exclusive; you cannot use both parameters in the same command.</span></span>

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

### <span data-ttu-id="d8772-149">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="d8772-149">-MinimumVersion</span></span>

<span data-ttu-id="d8772-150">Gibt die Mindestversion eines einzelnen Skripts an, das installiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="d8772-150">Specifies the minimum version of a single script to install.</span></span> <span data-ttu-id="d8772-151">Sie können diesen Parameter nicht hinzufügen, wenn Sie versuchen, mehrere Skripts zu installieren.</span><span class="sxs-lookup"><span data-stu-id="d8772-151">You cannot add this parameter if you are attempting to install multiple scripts.</span></span> <span data-ttu-id="d8772-152">Der **MinimumVersion** -Parameter und der Requirements- **Version** -Parameter schließen sich gegenseitig aus. beide Parameter können nicht im selben Befehl verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d8772-152">The **MinimumVersion** and the **RequiredVersion** parameters are mutually exclusive; you cannot use both parameters in the same command.</span></span>

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

### <span data-ttu-id="d8772-153">-Name</span><span class="sxs-lookup"><span data-stu-id="d8772-153">-Name</span></span>

<span data-ttu-id="d8772-154">Gibt ein Array von Namen von Skripts an, die installiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="d8772-154">Specifies an array of names of scripts to install.</span></span>

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

### <span data-ttu-id="d8772-155">-Nopathupdate</span><span class="sxs-lookup"><span data-stu-id="d8772-155">-NoPathUpdate</span></span>

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

### <span data-ttu-id="d8772-156">-PassThru</span><span class="sxs-lookup"><span data-stu-id="d8772-156">-PassThru</span></span>

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

### <span data-ttu-id="d8772-157">-Proxy</span><span class="sxs-lookup"><span data-stu-id="d8772-157">-Proxy</span></span>

<span data-ttu-id="d8772-158">Gibt einen Proxy Server für die Anforderung an, anstatt eine direkte Verbindung mit der Internet Ressource herzustellen.</span><span class="sxs-lookup"><span data-stu-id="d8772-158">Specifies a proxy server for the request, rather than connecting directly to the Internet resource.</span></span>

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

### <span data-ttu-id="d8772-159">-Proxy Credential</span><span class="sxs-lookup"><span data-stu-id="d8772-159">-ProxyCredential</span></span>

<span data-ttu-id="d8772-160">Gibt ein Benutzerkonto an, das über die Berechtigung zur Verwendung des Proxyservers verfügt, der durch den **Proxy**-Parameter angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="d8772-160">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="d8772-161">-Repository</span><span class="sxs-lookup"><span data-stu-id="d8772-161">-Repository</span></span>

<span data-ttu-id="d8772-162">Gibt den anzeigen Amen eines Repository an, das beim `Register-PSRepository` Cmdlet registriert wurde.</span><span class="sxs-lookup"><span data-stu-id="d8772-162">Specifies the friendly name of a repository that has been registered with the `Register-PSRepository` cmdlet.</span></span> <span data-ttu-id="d8772-163">Der Standardwert ist alle registrierten Depots.</span><span class="sxs-lookup"><span data-stu-id="d8772-163">The default is all registered repositories.</span></span>

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

### <span data-ttu-id="d8772-164">-Requirements dversion</span><span class="sxs-lookup"><span data-stu-id="d8772-164">-RequiredVersion</span></span>

<span data-ttu-id="d8772-165">Gibt die genaue Versionsnummer des zu installierenden Skripts an.</span><span class="sxs-lookup"><span data-stu-id="d8772-165">Specifies the exact version number of the script to install.</span></span>

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

### <span data-ttu-id="d8772-166">-Bereich</span><span class="sxs-lookup"><span data-stu-id="d8772-166">-Scope</span></span>

<span data-ttu-id="d8772-167">Gibt den Bereich der Installation des Skripts an.</span><span class="sxs-lookup"><span data-stu-id="d8772-167">Specifies the installation scope of the script.</span></span>
<span data-ttu-id="d8772-168">Gültige Werte sind: AllUsers und CurrentUser.</span><span class="sxs-lookup"><span data-stu-id="d8772-168">Valid values are: AllUsers and CurrentUser.</span></span>

<span data-ttu-id="d8772-169">Mit dem Bereich "ALLUSERS" können Module an einem Speicherort installiert werden, der für alle Benutzer des Computers zugänglich ist, d `$env:ProgramFiles\WindowsPowerShell\Scripts` . h..</span><span class="sxs-lookup"><span data-stu-id="d8772-169">The AllUsers scope lets modules be installed in a location that is accessible to all users of the computer, that is, `$env:ProgramFiles\WindowsPowerShell\Scripts`.</span></span>

<span data-ttu-id="d8772-170">Mit dem Bereich CurrentUser können Module nur für installiert werden `$home\Documents\WindowsPowerShell\Scripts` , damit das Modul nur für den aktuellen Benutzer verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="d8772-170">The CurrentUser scope lets modules be installed only to `$home\Documents\WindowsPowerShell\Scripts`, so that the module is available only to the current user.</span></span>

<span data-ttu-id="d8772-171">Wenn kein **Bereich** definiert ist, wird der Standardwert basierend auf der aktuellen Sitzung festgelegt:</span><span class="sxs-lookup"><span data-stu-id="d8772-171">When no **Scope** is defined, the default will be set based on the current session:</span></span>

- <span data-ttu-id="d8772-172">Für eine PowerShell-Sitzung mit erhöhten Rechten wird der Gültigkeits **Bereich** auf ALLUSERS eingestellt.</span><span class="sxs-lookup"><span data-stu-id="d8772-172">For an elevated PowerShell session, **Scope** defaults to AllUsers;</span></span>
- <span data-ttu-id="d8772-173">Für PowerShell-Sitzungen ohne erhöhte Rechte in [PowerShellGet, Version 2.0.0](https://www.powershellgallery.com/packages/PowerShellGet) und höher, liegt der Gültigkeits **Bereich** bei CurrentUser.</span><span class="sxs-lookup"><span data-stu-id="d8772-173">For non-elevated PowerShell sessions in [PowerShellGet versions 2.0.0](https://www.powershellgallery.com/packages/PowerShellGet) and above, **Scope** is CurrentUser;</span></span>
- <span data-ttu-id="d8772-174">Bei nicht erhöhten PowerShell-Sitzungen in PowerShellGet-Versionen 1.6.7 und früher ist der Gültigkeits **Bereich** nicht definiert und `Install-Module` schlägt fehl.</span><span class="sxs-lookup"><span data-stu-id="d8772-174">For non-elevated PowerShell sessions in PowerShellGet versions 1.6.7 and earlier, **Scope** is undefined, and `Install-Module` fails.</span></span>

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

### <span data-ttu-id="d8772-175">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="d8772-175">-WhatIf</span></span>

<span data-ttu-id="d8772-176">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d8772-176">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="d8772-177">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="d8772-177">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="d8772-178">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="d8772-178">CommonParameters</span></span>

<span data-ttu-id="d8772-179">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="d8772-179">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="d8772-180">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="d8772-180">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="d8772-181">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="d8772-181">INPUTS</span></span>

### <span data-ttu-id="d8772-182">System.String[]</span><span class="sxs-lookup"><span data-stu-id="d8772-182">System.String[]</span></span>

### <span data-ttu-id="d8772-183">System. Management. Automation. psobject []</span><span class="sxs-lookup"><span data-stu-id="d8772-183">System.Management.Automation.PSObject[]</span></span>

### <span data-ttu-id="d8772-184">System.String</span><span class="sxs-lookup"><span data-stu-id="d8772-184">System.String</span></span>

### <span data-ttu-id="d8772-185">System.Uri</span><span class="sxs-lookup"><span data-stu-id="d8772-185">System.Uri</span></span>

### <span data-ttu-id="d8772-186">System. Management. Automation. PSCredential</span><span class="sxs-lookup"><span data-stu-id="d8772-186">System.Management.Automation.PSCredential</span></span>

## <span data-ttu-id="d8772-187">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="d8772-187">OUTPUTS</span></span>

### <span data-ttu-id="d8772-188">System.Object</span><span class="sxs-lookup"><span data-stu-id="d8772-188">System.Object</span></span>

## <span data-ttu-id="d8772-189">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="d8772-189">NOTES</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d8772-190">Ab dem 2020 unterstützt die PowerShell-Katalog nicht mehr Transport Layer Security (TLS)-Versionen 1,0 und 1,1.</span><span class="sxs-lookup"><span data-stu-id="d8772-190">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="d8772-191">Wenn Sie TLS 1,2 oder höher nicht verwenden, erhalten Sie eine Fehlermeldung, wenn Sie versuchen, auf die PowerShell-Katalog zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="d8772-191">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="d8772-192">Verwenden Sie den folgenden Befehl, um sicherzustellen, dass Sie TLS 1,2 verwenden:</span><span class="sxs-lookup"><span data-stu-id="d8772-192">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="d8772-193">Weitere Informationen finden Sie in der [Ankündigung](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) im PowerShell-Blog.</span><span class="sxs-lookup"><span data-stu-id="d8772-193">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="d8772-194">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="d8772-194">RELATED LINKS</span></span>

[<span data-ttu-id="d8772-195">Find-Script</span><span class="sxs-lookup"><span data-stu-id="d8772-195">Find-Script</span></span>](Find-Script.md)

[<span data-ttu-id="d8772-196">Publish-Script</span><span class="sxs-lookup"><span data-stu-id="d8772-196">Publish-Script</span></span>](Publish-Script.md)

[<span data-ttu-id="d8772-197">Save-Script</span><span class="sxs-lookup"><span data-stu-id="d8772-197">Save-Script</span></span>](Save-Script.md)

[<span data-ttu-id="d8772-198">Uninstall-Script</span><span class="sxs-lookup"><span data-stu-id="d8772-198">Uninstall-Script</span></span>](Uninstall-Script.md)

[<span data-ttu-id="d8772-199">Update-Script</span><span class="sxs-lookup"><span data-stu-id="d8772-199">Update-Script</span></span>](Update-Script.md)
