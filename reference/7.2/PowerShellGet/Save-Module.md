---
external help file: PSModule-help.xml
Locale: en-US
Module Name: PowerShellGet
ms.date: 11/11/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/save-module?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Save-Module
ms.openlocfilehash: df5056b4402664602409388825c8b2b8acd4e02f
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/19/2020
ms.locfileid: "99600289"
---
# <span data-ttu-id="c7167-102">Save-Module</span><span class="sxs-lookup"><span data-stu-id="c7167-102">Save-Module</span></span>

## <span data-ttu-id="c7167-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="c7167-103">SYNOPSIS</span></span>
<span data-ttu-id="c7167-104">Speichert ein Modul und seine Abhängigkeiten auf dem lokalen Computer, installiert das Modul jedoch nicht.</span><span class="sxs-lookup"><span data-stu-id="c7167-104">Saves a module and its dependencies on the local computer but doesn't install the module.</span></span>

## <span data-ttu-id="c7167-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c7167-105">SYNTAX</span></span>

### <span data-ttu-id="c7167-106">Nameandpathparameterset (Standard)</span><span class="sxs-lookup"><span data-stu-id="c7167-106">NameAndPathParameterSet (Default)</span></span>

```
Save-Module [-Name] <String[]> [-MinimumVersion <String>] [-MaximumVersion <String>]
 [-RequiredVersion <String>] [-Repository <String[]>] [-Path] <String> [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-Credential <PSCredential>] [-Force] [-AllowPrerelease]
 [-AcceptLicense] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="c7167-107">Nameandliteralpathparameterset</span><span class="sxs-lookup"><span data-stu-id="c7167-107">NameAndLiteralPathParameterSet</span></span>

```
Save-Module [-Name] <String[]> [-MinimumVersion <String>] [-MaximumVersion <String>]
 [-RequiredVersion <String>] [-Repository <String[]>] -LiteralPath <String> [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-Credential <PSCredential>] [-Force] [-AllowPrerelease]
 [-AcceptLicense] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="c7167-108">Inputobjectandliteralpathparameterset</span><span class="sxs-lookup"><span data-stu-id="c7167-108">InputObjectAndLiteralPathParameterSet</span></span>

```
Save-Module [-InputObject] <PSObject[]> -LiteralPath <String> [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-Credential <PSCredential>] [-Force] [-AcceptLicense] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="c7167-109">Inputobjectandpathparameterset</span><span class="sxs-lookup"><span data-stu-id="c7167-109">InputObjectAndPathParameterSet</span></span>

```
Save-Module [-InputObject] <PSObject[]> [-Path] <String> [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-Credential <PSCredential>] [-Force] [-AcceptLicense] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="c7167-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="c7167-110">DESCRIPTION</span></span>

<span data-ttu-id="c7167-111">Mit dem `Save-Module` -Cmdlet werden ein Modul und alle Abhängigkeiten von einem registrierten Repository heruntergeladen.</span><span class="sxs-lookup"><span data-stu-id="c7167-111">The `Save-Module` cmdlet downloads a module and any dependencies from a registered repository.</span></span>
<span data-ttu-id="c7167-112">`Save-Module` Hiermit wird die aktuellste Version eines Moduls heruntergeladen und gespeichert.</span><span class="sxs-lookup"><span data-stu-id="c7167-112">`Save-Module` downloads and saves the most current version of a module.</span></span> <span data-ttu-id="c7167-113">Die Dateien werden in einem angegebenen Pfad auf dem lokalen Computer gespeichert.</span><span class="sxs-lookup"><span data-stu-id="c7167-113">The files are saved to a specified path on the local computer.</span></span> <span data-ttu-id="c7167-114">Das Modul ist nicht installiert, aber der Inhalt kann von einem Administrator überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="c7167-114">The module isn't installed, but the contents are available for inspection by an administrator.</span></span> <span data-ttu-id="c7167-115">Das gespeicherte Modul kann dann an den entsprechenden `$env:PSModulePath` Speicherort des Offline Computers kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="c7167-115">The saved module can then be copied into the appropriate `$env:PSModulePath` location of the offline machine.</span></span>

<span data-ttu-id="c7167-116">`Get-PSRepository` zeigt die registrierten Depots des lokalen Computers an.</span><span class="sxs-lookup"><span data-stu-id="c7167-116">`Get-PSRepository` displays the local computer's registered repositories.</span></span> <span data-ttu-id="c7167-117">Sie können mit dem `Find-Module` Cmdlet registrierte Depots durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="c7167-117">You can use the `Find-Module` cmdlet to search registered repositories.</span></span>

## <span data-ttu-id="c7167-118">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="c7167-118">EXAMPLES</span></span>

### <span data-ttu-id="c7167-119">Beispiel 1: Speichern eines Moduls</span><span class="sxs-lookup"><span data-stu-id="c7167-119">Example 1: Save a module</span></span>

<span data-ttu-id="c7167-120">In diesem Beispiel werden ein Modul und seine Abhängigkeiten auf dem lokalen Computer gespeichert.</span><span class="sxs-lookup"><span data-stu-id="c7167-120">In this example, a module and its dependencies are saved to the local computer.</span></span>

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

<span data-ttu-id="c7167-121">`Save-Module` verwendet den **Name** -Parameter, um das Modul " **PowerShellGet**" anzugeben.</span><span class="sxs-lookup"><span data-stu-id="c7167-121">`Save-Module` uses the **Name** parameter to specify the module, **PowerShellGet**.</span></span> <span data-ttu-id="c7167-122">Der **path** -Parameter gibt an, wo das heruntergeladene Modul gespeichert werden soll.</span><span class="sxs-lookup"><span data-stu-id="c7167-122">The **Path** parameter specifies where to store the downloaded module.</span></span> <span data-ttu-id="c7167-123">Der **Repository** -Parameter gibt ein registriertes Repository, **psgallery**, an.</span><span class="sxs-lookup"><span data-stu-id="c7167-123">The **Repository** parameter specifies a registered repository, **PSGallery**.</span></span> <span data-ttu-id="c7167-124">Nachdem der Download abgeschlossen ist, `Get-ChildItem` zeigt den Inhalt des **Pfads** an, in dem die Dateien gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="c7167-124">After the download is finished, `Get-ChildItem` displays the contents of **Path** where the files are stored.</span></span>

### <span data-ttu-id="c7167-125">Beispiel 2: Speichern einer bestimmten Version eines Moduls</span><span class="sxs-lookup"><span data-stu-id="c7167-125">Example 2: Save a specific version of a module</span></span>

<span data-ttu-id="c7167-126">In diesem Beispiel wird gezeigt, wie ein Parameter wie **MaximumVersion** oder Requirements **dversion** verwendet wird, um eine Modulversion anzugeben.</span><span class="sxs-lookup"><span data-stu-id="c7167-126">This example shows how to use a parameter such as **MaximumVersion**, or **RequiredVersion** to specify a module version.</span></span>

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

<span data-ttu-id="c7167-127">`Save-Module` verwendet den **Name** -Parameter, um das Modul " **PowerShellGet**" anzugeben.</span><span class="sxs-lookup"><span data-stu-id="c7167-127">`Save-Module` uses the **Name** parameter to specify the module, **PowerShellGet**.</span></span> <span data-ttu-id="c7167-128">Der **path** -Parameter gibt an, wo das heruntergeladene Modul gespeichert werden soll.</span><span class="sxs-lookup"><span data-stu-id="c7167-128">The **Path** parameter specifies where to store the downloaded module.</span></span> <span data-ttu-id="c7167-129">Der **Repository** -Parameter gibt ein registriertes Repository, **psgallery**, an.</span><span class="sxs-lookup"><span data-stu-id="c7167-129">The **Repository** parameter specifies a registered repository, **PSGallery**.</span></span> <span data-ttu-id="c7167-130">**MaximumVersion** gibt an, dass Version **2.1.0** heruntergeladen und gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="c7167-130">**MaximumVersion** specifies that version **2.1.0** is downloaded and saved.</span></span> <span data-ttu-id="c7167-131">Nachdem der Download abgeschlossen ist, `Get-ChildItem` zeigt den Inhalt des **Pfads** an, in dem die Dateien gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="c7167-131">After the download is finished, `Get-ChildItem` displays the contents of **Path** where the files are stored.</span></span>

### <span data-ttu-id="c7167-132">Beispiel 3: Suchen und Speichern einer bestimmten Version eines Moduls</span><span class="sxs-lookup"><span data-stu-id="c7167-132">Example 3: Find and save a specific version of a module</span></span>

<span data-ttu-id="c7167-133">In diesem Beispiel wird eine erforderliche Modulversion im Repository gefunden und auf dem lokalen Computer gespeichert.</span><span class="sxs-lookup"><span data-stu-id="c7167-133">In this example, a required module version is found in the repository and saved to the local computer.</span></span>

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

<span data-ttu-id="c7167-134">`Find-Module` verwendet den **Name** -Parameter, um das Modul " **PowerShellGet**" anzugeben.</span><span class="sxs-lookup"><span data-stu-id="c7167-134">`Find-Module` uses the **Name** parameter to specify the module, **PowerShellGet**.</span></span> <span data-ttu-id="c7167-135">Der **Repository** -Parameter gibt ein registriertes Repository, **psgallery**, an.</span><span class="sxs-lookup"><span data-stu-id="c7167-135">The **Repository** parameter specifies a registered repository, **PSGallery**.</span></span> <span data-ttu-id="c7167-136">Requirements **dversion** gibt Version **1.6.5** an.</span><span class="sxs-lookup"><span data-stu-id="c7167-136">**RequiredVersion** specifies version **1.6.5**.</span></span>

<span data-ttu-id="c7167-137">Das Objekt wird über die Pipeline an gesendet `Save-Module` .</span><span class="sxs-lookup"><span data-stu-id="c7167-137">The object is sent down the pipeline to `Save-Module`.</span></span> <span data-ttu-id="c7167-138">Der **path** -Parameter gibt an, wo das heruntergeladene Modul gespeichert werden soll.</span><span class="sxs-lookup"><span data-stu-id="c7167-138">The **Path** parameter specifies where to store the downloaded module.</span></span> <span data-ttu-id="c7167-139">Nachdem der Download abgeschlossen ist, `Get-ChildItem` zeigt den Inhalt des **Pfads** an, in dem die Dateien gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="c7167-139">After the download is finished, `Get-ChildItem` displays the contents of **Path** where the files are stored.</span></span>

## <span data-ttu-id="c7167-140">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c7167-140">PARAMETERS</span></span>

### <span data-ttu-id="c7167-141">-AcceptLicense</span><span class="sxs-lookup"><span data-stu-id="c7167-141">-AcceptLicense</span></span>

<span data-ttu-id="c7167-142">Akzeptieren Sie den Lizenzvertrag automatisch, wenn dies für das Paket erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="c7167-142">Automatically accept the license agreement if the package requires it.</span></span>

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

### <span data-ttu-id="c7167-143">-Allowprerelease</span><span class="sxs-lookup"><span data-stu-id="c7167-143">-AllowPrerelease</span></span>

<span data-ttu-id="c7167-144">Ermöglicht das Speichern eines als Vorabversion markierten Moduls.</span><span class="sxs-lookup"><span data-stu-id="c7167-144">Allows you to save a module marked as a prerelease.</span></span>

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

### <span data-ttu-id="c7167-145">-Confirm</span><span class="sxs-lookup"><span data-stu-id="c7167-145">-Confirm</span></span>

<span data-ttu-id="c7167-146">Fordert Sie zur Bestätigung auf, bevor Sie den ausführen `Save-Module` .</span><span class="sxs-lookup"><span data-stu-id="c7167-146">Prompts you for confirmation before running the `Save-Module`.</span></span>

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

### <span data-ttu-id="c7167-147">-Credential</span><span class="sxs-lookup"><span data-stu-id="c7167-147">-Credential</span></span>

<span data-ttu-id="c7167-148">Gibt ein Benutzerkonto an, das über Rechte zum Speichern eines Moduls verfügt.</span><span class="sxs-lookup"><span data-stu-id="c7167-148">Specifies a user account that has rights to save a module.</span></span>

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

### <span data-ttu-id="c7167-149">-Force</span><span class="sxs-lookup"><span data-stu-id="c7167-149">-Force</span></span>

<span data-ttu-id="c7167-150">Erzwingt das `Save-Module` Ausführen von, ohne dass eine Benutzer Bestätigung angefordert wird.</span><span class="sxs-lookup"><span data-stu-id="c7167-150">Forces `Save-Module` to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="c7167-151">-InputObject</span><span class="sxs-lookup"><span data-stu-id="c7167-151">-InputObject</span></span>

<span data-ttu-id="c7167-152">Akzeptiert ein **PSRepositoryItemInfo** -Objekt.</span><span class="sxs-lookup"><span data-stu-id="c7167-152">Accepts a **PSRepositoryItemInfo** object.</span></span> <span data-ttu-id="c7167-153">Geben `Find-Module` Sie z. b. eine Ausgabe an eine Variable ein, und verwenden Sie diese Variable als **Inputobject** -Argument.</span><span class="sxs-lookup"><span data-stu-id="c7167-153">For example, output `Find-Module` to a variable and use that variable as the **InputObject** argument.</span></span>

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

### <span data-ttu-id="c7167-154">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="c7167-154">-LiteralPath</span></span>

<span data-ttu-id="c7167-155">Gibt einen Pfad zu einem oder mehreren Speicherorten an.</span><span class="sxs-lookup"><span data-stu-id="c7167-155">Specifies a path to one or more locations.</span></span> <span data-ttu-id="c7167-156">Der Wert des **literalpath** -Parameters wird genau so verwendet, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="c7167-156">The value of the **LiteralPath** parameter is used exactly as entered.</span></span> <span data-ttu-id="c7167-157">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="c7167-157">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="c7167-158">Wenn der Pfad Escapezeichen enthält, schließen Sie Sie in einfache Anführungszeichen ein.</span><span class="sxs-lookup"><span data-stu-id="c7167-158">If the path includes escape characters, enclose them in single quotation marks.</span></span> <span data-ttu-id="c7167-159">PowerShell interpretiert keine Zeichen, die in einfache Anführungszeichen eingeschlossen sind, als Escapesequenzen.</span><span class="sxs-lookup"><span data-stu-id="c7167-159">PowerShell does not interpret any characters enclosed in single quotation marks as escape sequences.</span></span>

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

### <span data-ttu-id="c7167-160">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="c7167-160">-MaximumVersion</span></span>

<span data-ttu-id="c7167-161">Gibt die maximale oder neueste Version des zu speichernden Moduls an.</span><span class="sxs-lookup"><span data-stu-id="c7167-161">Specifies the maximum, or newest, version of the module to save.</span></span> <span data-ttu-id="c7167-162">Die Parameter **MaximumVersion** und Requirements **dversion** können nicht im selben Befehl verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c7167-162">The **MaximumVersion** and **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="c7167-163">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="c7167-163">-MinimumVersion</span></span>

<span data-ttu-id="c7167-164">Gibt die minimale Version eines einzelnen Moduls an, das gespeichert werden soll.</span><span class="sxs-lookup"><span data-stu-id="c7167-164">Specifies the minimum version of a single module to save.</span></span> <span data-ttu-id="c7167-165">Sie können diesen Parameter nicht hinzufügen, wenn Sie versuchen, mehrere Module zu installieren.</span><span class="sxs-lookup"><span data-stu-id="c7167-165">You cannot add this parameter if you are attempting to install multiple modules.</span></span> <span data-ttu-id="c7167-166">Die Parameter **MinimumVersion** und Requirements **dversion** können nicht im selben Befehl verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c7167-166">The **MinimumVersion** and **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="c7167-167">-Name</span><span class="sxs-lookup"><span data-stu-id="c7167-167">-Name</span></span>

<span data-ttu-id="c7167-168">Gibt ein Array von Namen von Modulen an, die gespeichert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="c7167-168">Specifies an array of names of modules to save.</span></span>

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

### <span data-ttu-id="c7167-169">-Path</span><span class="sxs-lookup"><span data-stu-id="c7167-169">-Path</span></span>

<span data-ttu-id="c7167-170">Gibt den Speicherort auf dem lokalen Computer zum Speichern eines gespeicherten Moduls an.</span><span class="sxs-lookup"><span data-stu-id="c7167-170">Specifies the location on the local computer to store a saved module.</span></span> <span data-ttu-id="c7167-171">Akzeptiert Platzhalter Zeichen.</span><span class="sxs-lookup"><span data-stu-id="c7167-171">Accepts wildcard characters.</span></span>

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

### <span data-ttu-id="c7167-172">-Proxy</span><span class="sxs-lookup"><span data-stu-id="c7167-172">-Proxy</span></span>

<span data-ttu-id="c7167-173">Gibt einen Proxy Server für die Anforderung an, anstatt eine direkte Verbindung mit der Internet Ressource herzustellen.</span><span class="sxs-lookup"><span data-stu-id="c7167-173">Specifies a proxy server for the request, rather than connecting directly to the internet resource.</span></span>

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

### <span data-ttu-id="c7167-174">-Proxy Credential</span><span class="sxs-lookup"><span data-stu-id="c7167-174">-ProxyCredential</span></span>

<span data-ttu-id="c7167-175">Gibt ein Benutzerkonto an, das über die Berechtigung zur Verwendung des Proxyservers verfügt, der durch den **Proxy**-Parameter angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="c7167-175">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="c7167-176">-Repository</span><span class="sxs-lookup"><span data-stu-id="c7167-176">-Repository</span></span>

<span data-ttu-id="c7167-177">Gibt den anzeigen Amen eines Repository an, das durch Ausführen von registriert wurde `Register-PSRepository` .</span><span class="sxs-lookup"><span data-stu-id="c7167-177">Specifies the friendly name of a repository that has been registered by running `Register-PSRepository`.</span></span> <span data-ttu-id="c7167-178">Verwenden `Get-PSRepository` Sie, um registrierte Depots anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="c7167-178">Use `Get-PSRepository` to display registered repositories.</span></span>

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

### <span data-ttu-id="c7167-179">-Requirements dversion</span><span class="sxs-lookup"><span data-stu-id="c7167-179">-RequiredVersion</span></span>

<span data-ttu-id="c7167-180">Gibt die genaue Versionsnummer des zu speichernden Moduls an.</span><span class="sxs-lookup"><span data-stu-id="c7167-180">Specifies the exact version number of the module to save.</span></span>

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

### <span data-ttu-id="c7167-181">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="c7167-181">-WhatIf</span></span>

<span data-ttu-id="c7167-182">Zeigt, was geschieht, wenn die ausgeführt wird `Save-Module` .</span><span class="sxs-lookup"><span data-stu-id="c7167-182">Shows what would happen if the `Save-Module` runs.</span></span> <span data-ttu-id="c7167-183">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="c7167-183">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="c7167-184">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="c7167-184">CommonParameters</span></span>

<span data-ttu-id="c7167-185">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="c7167-185">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="c7167-186">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="c7167-186">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="c7167-187">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="c7167-187">INPUTS</span></span>

### <span data-ttu-id="c7167-188">System.String[]</span><span class="sxs-lookup"><span data-stu-id="c7167-188">System.String[]</span></span>

### <span data-ttu-id="c7167-189">System. Management. Automation. psobject []</span><span class="sxs-lookup"><span data-stu-id="c7167-189">System.Management.Automation.PSObject[]</span></span>

### <span data-ttu-id="c7167-190">System.String</span><span class="sxs-lookup"><span data-stu-id="c7167-190">System.String</span></span>

### <span data-ttu-id="c7167-191">System.Uri</span><span class="sxs-lookup"><span data-stu-id="c7167-191">System.Uri</span></span>

### <span data-ttu-id="c7167-192">System. Management. Automation. PSCredential</span><span class="sxs-lookup"><span data-stu-id="c7167-192">System.Management.Automation.PSCredential</span></span>

## <span data-ttu-id="c7167-193">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="c7167-193">OUTPUTS</span></span>

### <span data-ttu-id="c7167-194">System.Object</span><span class="sxs-lookup"><span data-stu-id="c7167-194">System.Object</span></span>

## <span data-ttu-id="c7167-195">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="c7167-195">NOTES</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c7167-196">Ab April 2020 unterstützt der PowerShell-Katalog die TLS-Versionen (Transport Layer Security) 1.0 und 1.1 nicht mehr.</span><span class="sxs-lookup"><span data-stu-id="c7167-196">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="c7167-197">Wenn Sie nicht TLS 1.2 oder höher verwenden, erhalten Sie beim Versuch des Zugriffs auf den PowerShell-Katalog eine Fehlermeldung.</span><span class="sxs-lookup"><span data-stu-id="c7167-197">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="c7167-198">Mit dem folgenden Befehl können Sie sicherstellen, dass Sie TLS 1.2 verwenden:</span><span class="sxs-lookup"><span data-stu-id="c7167-198">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="c7167-199">Weitere Informationen finden Sie im PowerShell-Blog in der [Ankündigung](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/).</span><span class="sxs-lookup"><span data-stu-id="c7167-199">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="c7167-200">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="c7167-200">RELATED LINKS</span></span>
