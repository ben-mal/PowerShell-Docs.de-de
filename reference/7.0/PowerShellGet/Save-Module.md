---
external help file: PSModule-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PowerShellGet
ms.date: 11/11/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/save-module?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Save-Module
ms.openlocfilehash: fe737a8e248c95a39a430f59ae76d7981aa9c33a
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/19/2020
ms.locfileid: "94890432"
---
# <span data-ttu-id="840c1-103">Save-Module</span><span class="sxs-lookup"><span data-stu-id="840c1-103">Save-Module</span></span>

## <span data-ttu-id="840c1-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="840c1-104">SYNOPSIS</span></span>
<span data-ttu-id="840c1-105">Speichert ein Modul und seine Abhängigkeiten auf dem lokalen Computer, installiert das Modul jedoch nicht.</span><span class="sxs-lookup"><span data-stu-id="840c1-105">Saves a module and its dependencies on the local computer but doesn't install the module.</span></span>

## <span data-ttu-id="840c1-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="840c1-106">SYNTAX</span></span>

### <span data-ttu-id="840c1-107">Nameandpathparameterset (Standard)</span><span class="sxs-lookup"><span data-stu-id="840c1-107">NameAndPathParameterSet (Default)</span></span>

```
Save-Module [-Name] <String[]> [-MinimumVersion <String>] [-MaximumVersion <String>]
 [-RequiredVersion <String>] [-Repository <String[]>] [-Path] <String> [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-Credential <PSCredential>] [-Force] [-AllowPrerelease]
 [-AcceptLicense] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="840c1-108">Nameandliteralpathparameterset</span><span class="sxs-lookup"><span data-stu-id="840c1-108">NameAndLiteralPathParameterSet</span></span>

```
Save-Module [-Name] <String[]> [-MinimumVersion <String>] [-MaximumVersion <String>]
 [-RequiredVersion <String>] [-Repository <String[]>] -LiteralPath <String> [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-Credential <PSCredential>] [-Force] [-AllowPrerelease]
 [-AcceptLicense] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="840c1-109">Inputobjectandliteralpathparameterset</span><span class="sxs-lookup"><span data-stu-id="840c1-109">InputObjectAndLiteralPathParameterSet</span></span>

```
Save-Module [-InputObject] <PSObject[]> -LiteralPath <String> [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-Credential <PSCredential>] [-Force] [-AcceptLicense] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="840c1-110">Inputobjectandpathparameterset</span><span class="sxs-lookup"><span data-stu-id="840c1-110">InputObjectAndPathParameterSet</span></span>

```
Save-Module [-InputObject] <PSObject[]> [-Path] <String> [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-Credential <PSCredential>] [-Force] [-AcceptLicense] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="840c1-111">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="840c1-111">DESCRIPTION</span></span>

<span data-ttu-id="840c1-112">Mit dem `Save-Module` -Cmdlet werden ein Modul und alle Abhängigkeiten von einem registrierten Repository heruntergeladen.</span><span class="sxs-lookup"><span data-stu-id="840c1-112">The `Save-Module` cmdlet downloads a module and any dependencies from a registered repository.</span></span>
<span data-ttu-id="840c1-113">`Save-Module` Hiermit wird die aktuellste Version eines Moduls heruntergeladen und gespeichert.</span><span class="sxs-lookup"><span data-stu-id="840c1-113">`Save-Module` downloads and saves the most current version of a module.</span></span> <span data-ttu-id="840c1-114">Die Dateien werden in einem angegebenen Pfad auf dem lokalen Computer gespeichert.</span><span class="sxs-lookup"><span data-stu-id="840c1-114">The files are saved to a specified path on the local computer.</span></span> <span data-ttu-id="840c1-115">Das Modul ist nicht installiert, aber der Inhalt kann von einem Administrator überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="840c1-115">The module isn't installed, but the contents are available for inspection by an administrator.</span></span> <span data-ttu-id="840c1-116">Das gespeicherte Modul kann dann an den entsprechenden `$env:PSModulePath` Speicherort des Offline Computers kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="840c1-116">The saved module can then be copied into the appropriate `$env:PSModulePath` location of the offline machine.</span></span>

<span data-ttu-id="840c1-117">`Get-PSRepository` zeigt die registrierten Depots des lokalen Computers an.</span><span class="sxs-lookup"><span data-stu-id="840c1-117">`Get-PSRepository` displays the local computer's registered repositories.</span></span> <span data-ttu-id="840c1-118">Sie können mit dem `Find-Module` Cmdlet registrierte Depots durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="840c1-118">You can use the `Find-Module` cmdlet to search registered repositories.</span></span>

## <span data-ttu-id="840c1-119">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="840c1-119">EXAMPLES</span></span>

### <span data-ttu-id="840c1-120">Beispiel 1: Speichern eines Moduls</span><span class="sxs-lookup"><span data-stu-id="840c1-120">Example 1: Save a module</span></span>

<span data-ttu-id="840c1-121">In diesem Beispiel werden ein Modul und seine Abhängigkeiten auf dem lokalen Computer gespeichert.</span><span class="sxs-lookup"><span data-stu-id="840c1-121">In this example, a module and its dependencies are saved to the local computer.</span></span>

```powershell
Save-Module -Name PowerShellGet -Path C:\Test\Modules -Repository PSGallery
Get-ChildItem -Path C:\Test\Modules
```

```Output
    Directory: C:\Test\Modules

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----         7/1/2019     13:31                PackageManagement
d-----         7/1/2019     13:31                PowerShellGet
```

<span data-ttu-id="840c1-122">`Save-Module` verwendet den **Name** -Parameter, um das Modul " **PowerShellGet**" anzugeben.</span><span class="sxs-lookup"><span data-stu-id="840c1-122">`Save-Module` uses the **Name** parameter to specify the module, **PowerShellGet**.</span></span> <span data-ttu-id="840c1-123">Der **path** -Parameter gibt an, wo das heruntergeladene Modul gespeichert werden soll.</span><span class="sxs-lookup"><span data-stu-id="840c1-123">The **Path** parameter specifies where to store the downloaded module.</span></span> <span data-ttu-id="840c1-124">Der **Repository** -Parameter gibt ein registriertes Repository, **psgallery**, an.</span><span class="sxs-lookup"><span data-stu-id="840c1-124">The **Repository** parameter specifies a registered repository, **PSGallery**.</span></span> <span data-ttu-id="840c1-125">Nachdem der Download abgeschlossen ist, `Get-ChildItem` zeigt den Inhalt des **Pfads** an, in dem die Dateien gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="840c1-125">After the download is finished, `Get-ChildItem` displays the contents of **Path** where the files are stored.</span></span>

### <span data-ttu-id="840c1-126">Beispiel 2: Speichern einer bestimmten Version eines Moduls</span><span class="sxs-lookup"><span data-stu-id="840c1-126">Example 2: Save a specific version of a module</span></span>

<span data-ttu-id="840c1-127">In diesem Beispiel wird gezeigt, wie ein Parameter wie **MaximumVersion** oder Requirements **dversion** verwendet wird, um eine Modulversion anzugeben.</span><span class="sxs-lookup"><span data-stu-id="840c1-127">This example shows how to use a parameter such as **MaximumVersion**, or **RequiredVersion** to specify a module version.</span></span>

```powershell
Save-Module -Name PowerShellGet -Path C:\Test\Modules -Repository PSGallery -MaximumVersion 2.1.0
Get-ChildItem -Path C:\Test\Modules\PowerShellGet\
```

```Output
    Directory: C:\Test\Modules\PowerShellGet

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----         7/1/2019     13:40                2.1.0
```

<span data-ttu-id="840c1-128">`Save-Module` verwendet den **Name** -Parameter, um das Modul " **PowerShellGet**" anzugeben.</span><span class="sxs-lookup"><span data-stu-id="840c1-128">`Save-Module` uses the **Name** parameter to specify the module, **PowerShellGet**.</span></span> <span data-ttu-id="840c1-129">Der **path** -Parameter gibt an, wo das heruntergeladene Modul gespeichert werden soll.</span><span class="sxs-lookup"><span data-stu-id="840c1-129">The **Path** parameter specifies where to store the downloaded module.</span></span> <span data-ttu-id="840c1-130">Der **Repository** -Parameter gibt ein registriertes Repository, **psgallery**, an.</span><span class="sxs-lookup"><span data-stu-id="840c1-130">The **Repository** parameter specifies a registered repository, **PSGallery**.</span></span> <span data-ttu-id="840c1-131">**MaximumVersion** gibt an, dass Version **2.1.0** heruntergeladen und gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="840c1-131">**MaximumVersion** specifies that version **2.1.0** is downloaded and saved.</span></span> <span data-ttu-id="840c1-132">Nachdem der Download abgeschlossen ist, `Get-ChildItem` zeigt den Inhalt des **Pfads** an, in dem die Dateien gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="840c1-132">After the download is finished, `Get-ChildItem` displays the contents of **Path** where the files are stored.</span></span>

### <span data-ttu-id="840c1-133">Beispiel 3: Suchen und Speichern einer bestimmten Version eines Moduls</span><span class="sxs-lookup"><span data-stu-id="840c1-133">Example 3: Find and save a specific version of a module</span></span>

<span data-ttu-id="840c1-134">In diesem Beispiel wird eine erforderliche Modulversion im Repository gefunden und auf dem lokalen Computer gespeichert.</span><span class="sxs-lookup"><span data-stu-id="840c1-134">In this example, a required module version is found in the repository and saved to the local computer.</span></span>

```powershell
Find-Module -Name PowerShellGet -Repository PSGallery -RequiredVersion 1.6.5 |
  Save-Module -Path C:\Test\Modules
Get-ChildItem -Path C:\Test\Modules\PowerShellGet
```

```Output
    Directory: C:\Test\Modules\PowerShellGet

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----         7/1/2019     14:04                1.6.5
```

<span data-ttu-id="840c1-135">`Find-Module` verwendet den **Name** -Parameter, um das Modul " **PowerShellGet**" anzugeben.</span><span class="sxs-lookup"><span data-stu-id="840c1-135">`Find-Module` uses the **Name** parameter to specify the module, **PowerShellGet**.</span></span> <span data-ttu-id="840c1-136">Der **Repository** -Parameter gibt ein registriertes Repository, **psgallery**, an.</span><span class="sxs-lookup"><span data-stu-id="840c1-136">The **Repository** parameter specifies a registered repository, **PSGallery**.</span></span> <span data-ttu-id="840c1-137">Requirements **dversion** gibt Version **1.6.5** an.</span><span class="sxs-lookup"><span data-stu-id="840c1-137">**RequiredVersion** specifies version **1.6.5**.</span></span>

<span data-ttu-id="840c1-138">Das Objekt wird über die Pipeline an gesendet `Save-Module` .</span><span class="sxs-lookup"><span data-stu-id="840c1-138">The object is sent down the pipeline to `Save-Module`.</span></span> <span data-ttu-id="840c1-139">Der **path** -Parameter gibt an, wo das heruntergeladene Modul gespeichert werden soll.</span><span class="sxs-lookup"><span data-stu-id="840c1-139">The **Path** parameter specifies where to store the downloaded module.</span></span> <span data-ttu-id="840c1-140">Nachdem der Download abgeschlossen ist, `Get-ChildItem` zeigt den Inhalt des **Pfads** an, in dem die Dateien gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="840c1-140">After the download is finished, `Get-ChildItem` displays the contents of **Path** where the files are stored.</span></span>

## <span data-ttu-id="840c1-141">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="840c1-141">PARAMETERS</span></span>

### <span data-ttu-id="840c1-142">-AcceptLicense</span><span class="sxs-lookup"><span data-stu-id="840c1-142">-AcceptLicense</span></span>

<span data-ttu-id="840c1-143">Akzeptieren Sie den Lizenzvertrag automatisch, wenn dies für das Paket erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="840c1-143">Automatically accept the license agreement if the package requires it.</span></span>

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

### <span data-ttu-id="840c1-144">-Allowprerelease</span><span class="sxs-lookup"><span data-stu-id="840c1-144">-AllowPrerelease</span></span>

<span data-ttu-id="840c1-145">Ermöglicht das Speichern eines als Vorabversion markierten Moduls.</span><span class="sxs-lookup"><span data-stu-id="840c1-145">Allows you to save a module marked as a prerelease.</span></span>

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

### <span data-ttu-id="840c1-146">-Confirm</span><span class="sxs-lookup"><span data-stu-id="840c1-146">-Confirm</span></span>

<span data-ttu-id="840c1-147">Fordert Sie zur Bestätigung auf, bevor Sie den ausführen `Save-Module` .</span><span class="sxs-lookup"><span data-stu-id="840c1-147">Prompts you for confirmation before running the `Save-Module`.</span></span>

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

### <span data-ttu-id="840c1-148">-Credential</span><span class="sxs-lookup"><span data-stu-id="840c1-148">-Credential</span></span>

<span data-ttu-id="840c1-149">Gibt ein Benutzerkonto an, das über Rechte zum Speichern eines Moduls verfügt.</span><span class="sxs-lookup"><span data-stu-id="840c1-149">Specifies a user account that has rights to save a module.</span></span>

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

### <span data-ttu-id="840c1-150">-Force</span><span class="sxs-lookup"><span data-stu-id="840c1-150">-Force</span></span>

<span data-ttu-id="840c1-151">Erzwingt das `Save-Module` Ausführen von, ohne dass eine Benutzer Bestätigung angefordert wird.</span><span class="sxs-lookup"><span data-stu-id="840c1-151">Forces `Save-Module` to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="840c1-152">-InputObject</span><span class="sxs-lookup"><span data-stu-id="840c1-152">-InputObject</span></span>

<span data-ttu-id="840c1-153">Akzeptiert ein **PSRepositoryItemInfo** -Objekt.</span><span class="sxs-lookup"><span data-stu-id="840c1-153">Accepts a **PSRepositoryItemInfo** object.</span></span> <span data-ttu-id="840c1-154">Geben `Find-Module` Sie z. b. eine Ausgabe an eine Variable ein, und verwenden Sie diese Variable als **Inputobject** -Argument.</span><span class="sxs-lookup"><span data-stu-id="840c1-154">For example, output `Find-Module` to a variable and use that variable as the **InputObject** argument.</span></span>

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

### <span data-ttu-id="840c1-155">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="840c1-155">-LiteralPath</span></span>

<span data-ttu-id="840c1-156">Gibt einen Pfad zu einem oder mehreren Speicherorten an.</span><span class="sxs-lookup"><span data-stu-id="840c1-156">Specifies a path to one or more locations.</span></span> <span data-ttu-id="840c1-157">Der Wert des **literalpath** -Parameters wird genau so verwendet, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="840c1-157">The value of the **LiteralPath** parameter is used exactly as entered.</span></span> <span data-ttu-id="840c1-158">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="840c1-158">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="840c1-159">Wenn der Pfad Escapezeichen enthält, schließen Sie Sie in einfache Anführungszeichen ein.</span><span class="sxs-lookup"><span data-stu-id="840c1-159">If the path includes escape characters, enclose them in single quotation marks.</span></span> <span data-ttu-id="840c1-160">PowerShell interpretiert keine Zeichen, die in einfache Anführungszeichen eingeschlossen sind, als Escapesequenzen.</span><span class="sxs-lookup"><span data-stu-id="840c1-160">PowerShell does not interpret any characters enclosed in single quotation marks as escape sequences.</span></span>

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

### <span data-ttu-id="840c1-161">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="840c1-161">-MaximumVersion</span></span>

<span data-ttu-id="840c1-162">Gibt die maximale oder neueste Version des zu speichernden Moduls an.</span><span class="sxs-lookup"><span data-stu-id="840c1-162">Specifies the maximum, or newest, version of the module to save.</span></span> <span data-ttu-id="840c1-163">Die Parameter **MaximumVersion** und Requirements **dversion** können nicht im selben Befehl verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="840c1-163">The **MaximumVersion** and **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="840c1-164">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="840c1-164">-MinimumVersion</span></span>

<span data-ttu-id="840c1-165">Gibt die minimale Version eines einzelnen Moduls an, das gespeichert werden soll.</span><span class="sxs-lookup"><span data-stu-id="840c1-165">Specifies the minimum version of a single module to save.</span></span> <span data-ttu-id="840c1-166">Sie können diesen Parameter nicht hinzufügen, wenn Sie versuchen, mehrere Module zu installieren.</span><span class="sxs-lookup"><span data-stu-id="840c1-166">You cannot add this parameter if you are attempting to install multiple modules.</span></span> <span data-ttu-id="840c1-167">Die Parameter **MinimumVersion** und Requirements **dversion** können nicht im selben Befehl verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="840c1-167">The **MinimumVersion** and **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="840c1-168">-Name</span><span class="sxs-lookup"><span data-stu-id="840c1-168">-Name</span></span>

<span data-ttu-id="840c1-169">Gibt ein Array von Namen von Modulen an, die gespeichert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="840c1-169">Specifies an array of names of modules to save.</span></span>

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

### <span data-ttu-id="840c1-170">-Path</span><span class="sxs-lookup"><span data-stu-id="840c1-170">-Path</span></span>

<span data-ttu-id="840c1-171">Gibt den Speicherort auf dem lokalen Computer zum Speichern eines gespeicherten Moduls an.</span><span class="sxs-lookup"><span data-stu-id="840c1-171">Specifies the location on the local computer to store a saved module.</span></span> <span data-ttu-id="840c1-172">Akzeptiert Platzhalter Zeichen.</span><span class="sxs-lookup"><span data-stu-id="840c1-172">Accepts wildcard characters.</span></span>

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

### <span data-ttu-id="840c1-173">-Proxy</span><span class="sxs-lookup"><span data-stu-id="840c1-173">-Proxy</span></span>

<span data-ttu-id="840c1-174">Gibt einen Proxy Server für die Anforderung an, anstatt eine direkte Verbindung mit der Internet Ressource herzustellen.</span><span class="sxs-lookup"><span data-stu-id="840c1-174">Specifies a proxy server for the request, rather than connecting directly to the internet resource.</span></span>

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

### <span data-ttu-id="840c1-175">-Proxy Credential</span><span class="sxs-lookup"><span data-stu-id="840c1-175">-ProxyCredential</span></span>

<span data-ttu-id="840c1-176">Gibt ein Benutzerkonto an, das über die Berechtigung zur Verwendung des Proxyservers verfügt, der durch den **Proxy**-Parameter angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="840c1-176">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="840c1-177">-Repository</span><span class="sxs-lookup"><span data-stu-id="840c1-177">-Repository</span></span>

<span data-ttu-id="840c1-178">Gibt den anzeigen Amen eines Repository an, das durch Ausführen von registriert wurde `Register-PSRepository` .</span><span class="sxs-lookup"><span data-stu-id="840c1-178">Specifies the friendly name of a repository that has been registered by running `Register-PSRepository`.</span></span> <span data-ttu-id="840c1-179">Verwenden `Get-PSRepository` Sie, um registrierte Depots anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="840c1-179">Use `Get-PSRepository` to display registered repositories.</span></span>

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

### <span data-ttu-id="840c1-180">-Requirements dversion</span><span class="sxs-lookup"><span data-stu-id="840c1-180">-RequiredVersion</span></span>

<span data-ttu-id="840c1-181">Gibt die genaue Versionsnummer des zu speichernden Moduls an.</span><span class="sxs-lookup"><span data-stu-id="840c1-181">Specifies the exact version number of the module to save.</span></span>

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

### <span data-ttu-id="840c1-182">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="840c1-182">-WhatIf</span></span>

<span data-ttu-id="840c1-183">Zeigt, was geschieht, wenn die ausgeführt wird `Save-Module` .</span><span class="sxs-lookup"><span data-stu-id="840c1-183">Shows what would happen if the `Save-Module` runs.</span></span> <span data-ttu-id="840c1-184">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="840c1-184">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="840c1-185">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="840c1-185">CommonParameters</span></span>

<span data-ttu-id="840c1-186">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="840c1-186">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="840c1-187">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="840c1-187">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="840c1-188">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="840c1-188">INPUTS</span></span>

### <span data-ttu-id="840c1-189">System.String[]</span><span class="sxs-lookup"><span data-stu-id="840c1-189">System.String[]</span></span>

### <span data-ttu-id="840c1-190">System. Management. Automation. psobject []</span><span class="sxs-lookup"><span data-stu-id="840c1-190">System.Management.Automation.PSObject[]</span></span>

### <span data-ttu-id="840c1-191">System.String</span><span class="sxs-lookup"><span data-stu-id="840c1-191">System.String</span></span>

### <span data-ttu-id="840c1-192">System.Uri</span><span class="sxs-lookup"><span data-stu-id="840c1-192">System.Uri</span></span>

### <span data-ttu-id="840c1-193">System. Management. Automation. PSCredential</span><span class="sxs-lookup"><span data-stu-id="840c1-193">System.Management.Automation.PSCredential</span></span>

## <span data-ttu-id="840c1-194">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="840c1-194">OUTPUTS</span></span>

### <span data-ttu-id="840c1-195">System.Object</span><span class="sxs-lookup"><span data-stu-id="840c1-195">System.Object</span></span>

## <span data-ttu-id="840c1-196">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="840c1-196">NOTES</span></span>

> [!IMPORTANT]
> <span data-ttu-id="840c1-197">Ab dem 2020 unterstützt die PowerShell-Katalog nicht mehr Transport Layer Security (TLS)-Versionen 1,0 und 1,1.</span><span class="sxs-lookup"><span data-stu-id="840c1-197">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="840c1-198">Wenn Sie TLS 1,2 oder höher nicht verwenden, erhalten Sie eine Fehlermeldung, wenn Sie versuchen, auf die PowerShell-Katalog zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="840c1-198">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="840c1-199">Verwenden Sie den folgenden Befehl, um sicherzustellen, dass Sie TLS 1,2 verwenden:</span><span class="sxs-lookup"><span data-stu-id="840c1-199">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="840c1-200">Weitere Informationen finden Sie in der [Ankündigung](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) im PowerShell-Blog.</span><span class="sxs-lookup"><span data-stu-id="840c1-200">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="840c1-201">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="840c1-201">RELATED LINKS</span></span>
