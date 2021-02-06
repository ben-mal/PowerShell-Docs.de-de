---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 05/16/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/update-help?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Update-Help
ms.openlocfilehash: f4aec907a41378bbf49f744b66c5662aa3404beb
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99596765"
---
# <span data-ttu-id="a27e5-102">Update-Help</span><span class="sxs-lookup"><span data-stu-id="a27e5-102">Update-Help</span></span>

## <span data-ttu-id="a27e5-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="a27e5-103">SYNOPSIS</span></span>
<span data-ttu-id="a27e5-104">Lädt die neuesten Hilfedateien auf den Computer herunter und installiert sie.</span><span class="sxs-lookup"><span data-stu-id="a27e5-104">Downloads and installs the newest help files on your computer.</span></span>

## <span data-ttu-id="a27e5-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a27e5-105">SYNTAX</span></span>

### <span data-ttu-id="a27e5-106">Pfad (Standard)</span><span class="sxs-lookup"><span data-stu-id="a27e5-106">Path (Default)</span></span>

```
Update-Help [[-Module] <String[]>] [-FullyQualifiedModule <ModuleSpecification[]>]
 [[-SourcePath] <String[]>] [-Recurse] [[-UICulture] <CultureInfo[]>] [-Credential <PSCredential>]
 [-UseDefaultCredentials] [-Force] [-Scope <UpdateHelpScope>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="a27e5-107">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="a27e5-107">LiteralPath</span></span>

```
Update-Help [[-Module] <String[]>] [-FullyQualifiedModule <ModuleSpecification[]>]
 [-LiteralPath <String[]>] [-Recurse] [[-UICulture] <CultureInfo[]>] [-Credential <PSCredential>]
 [-UseDefaultCredentials] [-Force] [-Scope <UpdateHelpScope>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="a27e5-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a27e5-108">DESCRIPTION</span></span>

<span data-ttu-id="a27e5-109">Das `Update-Help` Cmdlet lädt die neuesten Hilfedateien für PowerShell-Module herunter und installiert Sie auf Ihrem Computer.</span><span class="sxs-lookup"><span data-stu-id="a27e5-109">The `Update-Help` cmdlet downloads the newest help files for PowerShell modules and installs them on your computer.</span></span> <span data-ttu-id="a27e5-110">PowerShell muss nicht neu gestartet werden, damit die Änderung wirksam wird.</span><span class="sxs-lookup"><span data-stu-id="a27e5-110">You need not restart PowerShell to make the change effective.</span></span> <span data-ttu-id="a27e5-111">Mit dem- `Get-Help` Cmdlet können Sie die neuen Hilfedateien sofort anzeigen.</span><span class="sxs-lookup"><span data-stu-id="a27e5-111">You can use the `Get-Help` cmdlet to view the new help files immediately.</span></span>

<span data-ttu-id="a27e5-112">`Update-Help` Hiermit wird die Version der Hilfedateien auf Ihrem Computer überprüft.</span><span class="sxs-lookup"><span data-stu-id="a27e5-112">`Update-Help` checks the version of the help files on your computer.</span></span> <span data-ttu-id="a27e5-113">Wenn Sie keine Hilfedateien für ein Modul haben oder wenn Ihre Hilfedateien veraltet sind, werden `Update-Help` die neuesten Hilfedateien heruntergeladen.</span><span class="sxs-lookup"><span data-stu-id="a27e5-113">If you don't have help files for a module or if your help files are outdated, `Update-Help` downloads the newest help files.</span></span> <span data-ttu-id="a27e5-114">Die Hilfedateien können aus dem Internet oder aus einer Dateifreigabe heruntergeladen und installiert werden.</span><span class="sxs-lookup"><span data-stu-id="a27e5-114">The help files can be downloaded and installed from the internet or a file share.</span></span>

<span data-ttu-id="a27e5-115">Ohne Parameter `Update-Help` aktualisiert die Hilfedateien für Module in der Sitzung und für alle installierten Module, die die aktualisierbare Hilfe unterstützen.</span><span class="sxs-lookup"><span data-stu-id="a27e5-115">Without parameters, `Update-Help` updates the help files for modules in the session and for all installed modules that support Updatable Help.</span></span> <span data-ttu-id="a27e5-116">Module, die installiert, aber nicht in der aktuellen Sitzung geladen werden, sind eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="a27e5-116">Modules that are installed but not loaded in the current session are included.</span></span> <span data-ttu-id="a27e5-117">PowerShell-Module werden an einem Speicherort gespeichert, der in der `$env:PSModulePath` Umgebungsvariablen aufgeführt ist.</span><span class="sxs-lookup"><span data-stu-id="a27e5-117">PowerShell modules are stored in a location listed in the `$env:PSModulePath` environment variable.</span></span> <span data-ttu-id="a27e5-118">Weitere Informationen hierzu finden Sie unter [about_Updatable_Help](./About/about_Updatable_Help.md).</span><span class="sxs-lookup"><span data-stu-id="a27e5-118">For more information, see [about_Updatable_Help](./About/about_Updatable_Help.md).</span></span>

<span data-ttu-id="a27e5-119">Sie können den **Module** -Parameter verwenden, um Hilfedateien für ein bestimmtes Modul zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="a27e5-119">You can use the **Module** parameter to update help files for a particular module.</span></span> <span data-ttu-id="a27e5-120">Verwenden Sie den **UICulture** -Parameter, um Hilfedateien in mehreren Sprachen und Gebiets Schemas herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="a27e5-120">Use the **UICulture** parameter to download help files in multiple languages and locales.</span></span>

<span data-ttu-id="a27e5-121">Sie können auch `Update-Help` auf Computern verwenden, die nicht mit dem Internet verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="a27e5-121">You can also use `Update-Help` on computers that are not connected to the internet.</span></span> <span data-ttu-id="a27e5-122">Verwenden Sie zunächst das `Save-Help` Cmdlet, um Hilfedateien aus dem Internet herunterzuladen, und speichern Sie Sie in einem freigegebenen Ordner, der für das System verfügbar ist, das nicht mit dem Internet verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="a27e5-122">First, use the `Save-Help`cmdlet to download help files from the internet and save them in a shared folder that is accessible to the system not connected to the internet.</span></span> <span data-ttu-id="a27e5-123">Verwenden Sie dann den **SourcePath** -Parameter von `Update-Help` , um die aktualisierten Hilfedateien aus dem freigegebenen herunterzuladen und auf dem Computer zu installieren.</span><span class="sxs-lookup"><span data-stu-id="a27e5-123">Then use the **SourcePath** parameter of `Update-Help` to download the updated help files from the shared and install them on the computer.</span></span>

<span data-ttu-id="a27e5-124">Sie können Hilfe Updates automatisieren, indem Sie das `Update-Help` Cmdlet Ihrem PowerShell-Profil hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="a27e5-124">You can automate help updates by adding the `Update-Help` cmdlet to your PowerShell profile.</span></span> <span data-ttu-id="a27e5-125">Standardmäßig wird `Update-Help` auf jedem Computer nur einmal pro Tag ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="a27e5-125">By default, `Update-Help` runs only one time per day on each computer.</span></span> <span data-ttu-id="a27e5-126">Um den Grenzwert von einmal täglich zu überschreiben, verwenden Sie den **Force**-Parameter.</span><span class="sxs-lookup"><span data-stu-id="a27e5-126">To override the once-per-day limit, use the **Force** parameter.</span></span>

<span data-ttu-id="a27e5-127">Das `Update-Help` Cmdlet wurde in Windows PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="a27e5-127">The `Update-Help` cmdlet was introduced in Windows PowerShell 3.0.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a27e5-128">`Update-Help` erfordert Administratorrechte in PowerShell 6,0 und niedriger.</span><span class="sxs-lookup"><span data-stu-id="a27e5-128">`Update-Help` requires administrative privileges in PowerShell 6.0 and below.</span></span>
> <span data-ttu-id="a27e5-129">Mit PowerShell 6,1 und höher wird der Standard **Bereich** auf festgelegt `CurrentUser` .</span><span class="sxs-lookup"><span data-stu-id="a27e5-129">PowerShell 6.1 and above set the default **Scope** to `CurrentUser`.</span></span>
> <span data-ttu-id="a27e5-130">Vor PowerShell 6,1 war der **Bereichs** Parameter nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="a27e5-130">Prior to PowerShell 6.1, the **Scope** parameter was not available.</span></span>
>
> <span data-ttu-id="a27e5-131">Sie müssen Mitglied der Gruppe "Administratoren" auf dem Computer sein, um die Hilfedateien für die PowerShell-Kernmodule zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="a27e5-131">You must be a member of the Administrators group on the computer to update the help files for the PowerShell Core modules.</span></span>
>
> <span data-ttu-id="a27e5-132">Zum Herunterladen oder Aktualisieren der Hilfedateien für Module im PowerShell-Installationsverzeichnis ( `$PSHOME\Modules` ), einschließlich der PowerShell-Kernmodule, starten Sie PowerShell mit der Option **als Administrator ausführen** .</span><span class="sxs-lookup"><span data-stu-id="a27e5-132">To download or update the help files for modules in the PowerShell installation directory (`$PSHOME\Modules`), including the PowerShell Core modules, start PowerShell by using the **Run as administrator** option.</span></span>
> <span data-ttu-id="a27e5-133">Beispiel: `Start-Process pwsh.exe -Verb RunAs`.</span><span class="sxs-lookup"><span data-stu-id="a27e5-133">For example: `Start-Process pwsh.exe -Verb RunAs`.</span></span>

## <span data-ttu-id="a27e5-134">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="a27e5-134">EXAMPLES</span></span>

### <span data-ttu-id="a27e5-135">Beispiel 1: Aktualisieren der Hilfedateien für alle Module</span><span class="sxs-lookup"><span data-stu-id="a27e5-135">Example 1: Update help files for all modules</span></span>

<span data-ttu-id="a27e5-136">Das- `Update-Help` Cmdlet aktualisiert Hilfedateien für installierte Module, die die aktualisierbare Hilfe unterstützen.</span><span class="sxs-lookup"><span data-stu-id="a27e5-136">The `Update-Help` cmdlet updates help files for installed modules that support Updatable Help.</span></span> <span data-ttu-id="a27e5-137">Die Kultur Sprache der Benutzeroberfläche (UI) wird im Betriebssystem festgelegt.</span><span class="sxs-lookup"><span data-stu-id="a27e5-137">The user-interface (UI) culture language is set in the operating system.</span></span>

```powershell
Update-Help
```

### <span data-ttu-id="a27e5-138">Beispiel 2: Aktualisieren der Hilfedateien für angegebene Module</span><span class="sxs-lookup"><span data-stu-id="a27e5-138">Example 2: Update help files for specified modules</span></span>

<span data-ttu-id="a27e5-139">Das `Update-Help` Cmdlet aktualisiert Hilfedateien nur für Modulnamen, die mit **Microsoft. PowerShell** beginnen.</span><span class="sxs-lookup"><span data-stu-id="a27e5-139">The `Update-Help` cmdlet updates help files only for module names that begin with **Microsoft.PowerShell**.</span></span>

```powershell
Update-Help -Module Microsoft.PowerShell*
```

### <span data-ttu-id="a27e5-140">Beispiel 3: Aktualisieren von Hilfedateien für verschiedene Sprachen</span><span class="sxs-lookup"><span data-stu-id="a27e5-140">Example 3: Update help files for different languages</span></span>

<span data-ttu-id="a27e5-141">Mit dem `Update-Help` -Cmdlet werden die Hilfedateien für Japanisch (ja-JP) und Englisch (en-US) für alle Module aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="a27e5-141">The `Update-Help` cmdlet updates the Japanese (ja-JP) and English (en-US) help files for all modules.</span></span>

<span data-ttu-id="a27e5-142">Wenn ein Modul keine Hilfedateien für eine angegebene UI-Kultur bereitstellt, wird eine Fehlermeldung für das Modul und die Benutzeroberflächen Kultur angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a27e5-142">If a module doesn't provide help files for a specified UI culture, an error message is displayed for the module and UI culture.</span></span> <span data-ttu-id="a27e5-143">In diesem Beispiel gibt die Fehlermeldung an, dass die **ja-JP-** Hilfedateien für das Modul " **Microsoft. PowerShell. Utility**" nicht gefunden wurden.</span><span class="sxs-lookup"><span data-stu-id="a27e5-143">In this example, the error message indicates that the **ja-JP** help files were not found for module **Microsoft.PowerShell.Utility**.</span></span>

```powershell
Update-Help -UICulture ja-JP, en-US
```

```Output
Update-Help : Failed to update Help for the module(s) 'Microsoft.PowerShell.Utility' with UI culture(s) {ja-JP}
No UI culture was found that matches the following pattern: ja-JP.
```

### <span data-ttu-id="a27e5-144">Beispiel 4: Aktualisieren von Hilfedateien auf mehreren Computern aus einer Dateifreigabe</span><span class="sxs-lookup"><span data-stu-id="a27e5-144">Example 4: Update help files on multiple computers from a file share</span></span>

<span data-ttu-id="a27e5-145">In diesem Beispiel werden aktualisierte Hilfedateien aus dem Internet heruntergeladen und in einer Dateifreigabe gespeichert.</span><span class="sxs-lookup"><span data-stu-id="a27e5-145">In this example, updated help files are downloaded from the internet and saved in a file share.</span></span> <span data-ttu-id="a27e5-146">Es sind Benutzer Anmelde Informationen erforderlich, die über Berechtigungen zum Zugreifen auf die Dateifreigabe und zum Installieren von Updates verfügen.</span><span class="sxs-lookup"><span data-stu-id="a27e5-146">User credentials are needed that have permissions to access the file share and install updates.</span></span> <span data-ttu-id="a27e5-147">Wenn eine Dateifreigabe verwendet wird, ist es möglich, Computer zu aktualisieren, die sich hinter Firewalls befinden oder nicht mit dem Internet verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="a27e5-147">When a file share is used, it's possible to update computers that are behind firewalls or aren't connected to the internet.</span></span>

```powershell
Save-Help -DestinationPath \\Server01\Share\PSHelp -Credential Domain01\Admin01
Invoke-Command -ComputerName (Get-Content Servers.txt) -ScriptBlock {
     Update-Help -SourcePath \\Server01\Share\PSHelp -Credential Domain01\Admin01
}
```

<span data-ttu-id="a27e5-148">Der `Save-Help` Befehl lädt die neuesten Hilfedateien für alle Module herunter, die die aktualisierbare Hilfe unterstützen.</span><span class="sxs-lookup"><span data-stu-id="a27e5-148">The `Save-Help` command downloads the newest help files for all modules that support Updatable Help.</span></span>
<span data-ttu-id="a27e5-149">Der **DestinationPath** -Parameter speichert die Dateien in der `\\Server01\Share\PSHelp` Dateifreigabe.</span><span class="sxs-lookup"><span data-stu-id="a27e5-149">The **DestinationPath** parameter saves the files in the `\\Server01\Share\PSHelp` file share.</span></span> <span data-ttu-id="a27e5-150">Der **Credential** -Parameter gibt einen Benutzer an, der über die Berechtigung für den Zugriff auf die Dateifreigabe verfügt.</span><span class="sxs-lookup"><span data-stu-id="a27e5-150">The **Credential** parameter specifies a user who has permission to access the file share.</span></span>

<span data-ttu-id="a27e5-151">Mit dem- `Invoke-Command` Cmdlet werden Remote `Update-Help` Befehle auf mehreren Computern ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="a27e5-151">The `Invoke-Command` cmdlet runs remote `Update-Help` commands on multiple computers.</span></span> <span data-ttu-id="a27e5-152">Mit dem Parameter " **Computername** " wird eine Liste von Remote Computern aus der **Servers.txt** Datei abgerufen.</span><span class="sxs-lookup"><span data-stu-id="a27e5-152">The **ComputerName** parameter gets a list of remote computers from the **Servers.txt** file.</span></span> <span data-ttu-id="a27e5-153">Der **ScriptBlock** -Parameter führt den `Update-Help` Befehl aus und verwendet den **SourcePath** -Parameter, um die Dateifreigabe anzugeben, die die aktualisierten Hilfedateien enthält.</span><span class="sxs-lookup"><span data-stu-id="a27e5-153">The **ScriptBlock** parameter runs the `Update-Help` command and uses the **SourcePath** parameter to specify the file share that contains the updated help files.</span></span> <span data-ttu-id="a27e5-154">Der **Credential** -Parameter gibt einen Benutzer an, der auf die Dateifreigabe zugreifen und den Remote Befehl ausführen kann `Update-Help` .</span><span class="sxs-lookup"><span data-stu-id="a27e5-154">The **Credential** parameter specifies a user who can access the file share and run the remote `Update-Help` command.</span></span>

### <span data-ttu-id="a27e5-155">Beispiel 5: erhalten einer Liste mit aktualisierten Hilfedateien</span><span class="sxs-lookup"><span data-stu-id="a27e5-155">Example 5: Get a list of updated help files</span></span>

<span data-ttu-id="a27e5-156">Das- `Update-Help` Cmdlet aktualisiert die Hilfe für ein angegebenes Modul.</span><span class="sxs-lookup"><span data-stu-id="a27e5-156">The `Update-Help` cmdlet updates help for a specified module.</span></span> <span data-ttu-id="a27e5-157">Das Cmdlet verwendet den allgemeinen **verbose** -Parameter, um die Liste der aktualisierten Hilfedateien anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="a27e5-157">The cmdlet uses the **Verbose** common parameter to display the list of help files that were updated.</span></span> <span data-ttu-id="a27e5-158">Sie können " **verbose** " verwenden, um die Ausgabe für alle Hilfedateien oder Hilfedateien für ein bestimmtes Modul anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="a27e5-158">You can use **Verbose** to view output for all help files or help files for a specific module.</span></span>

<span data-ttu-id="a27e5-159">Ohne den **verbose** -Parameter werden `Update-Help` die Ergebnisse des Befehls nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a27e5-159">Without the **Verbose** parameter, `Update-Help` doesn't display the results of the command.</span></span> <span data-ttu-id="a27e5-160">Mithilfe der ausführlichen Parameter Ausgabe können Sie überprüfen, ob die Hilfedateien aktualisiert wurden oder **ob die neueste** Version installiert ist.</span><span class="sxs-lookup"><span data-stu-id="a27e5-160">The **Verbose** parameter output is useful to verify that the help files were updated or if the latest version is installed.</span></span>

```powershell
Update-Help -Module Microsoft.PowerShell.Utility -Verbose
```

### <span data-ttu-id="a27e5-161">Beispiel 6: Suchen von Modulen, die aktualisierbare Hilfe unterstützen</span><span class="sxs-lookup"><span data-stu-id="a27e5-161">Example 6: Find modules that support Updatable Help</span></span>

<span data-ttu-id="a27e5-162">In diesem Beispiel werden Module aufgelistet, die aktualisierbare Hilfe unterstützen</span><span class="sxs-lookup"><span data-stu-id="a27e5-162">This example lists modules that support Updatable Help.</span></span> <span data-ttu-id="a27e5-163">Der Befehl verwendet die **helpinfouri** -Eigenschaft des Moduls zur Identifizierung von Modulen, die die aktualisierbare Hilfe unterstützen.</span><span class="sxs-lookup"><span data-stu-id="a27e5-163">The command uses the module's **HelpInfoUri** property to identify modules that support Updatable Help.</span></span> <span data-ttu-id="a27e5-164">Die **helpinfouri** -Eigenschaft enthält eine Adresse, die umgeleitet wird, wenn das `Update-Help` Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a27e5-164">The **HelpInfoUri** property contains an address that is redirected when the `Update-Help` cmdlet is run.</span></span>

```powershell
Get-Module -ListAvailable | Where-Object -Property HelpInfoUri
```

```output
   Directory: C:\program files\powershell\6\Modules

ModuleType Version    Name                                PSEdition ExportedCommands
---------- -------    ----                                --------- ----------------
Manifest   6.1.0.0    CimCmdlets                          Core      {Get-CimAssociatedInstance... }
Manifest   1.2.2.0    Microsoft.PowerShell.Archive        Desk      {Compress-Archive... }
Manifest   6.1.0.0    Microsoft.PowerShell.Diagnostics    Core      {Get-WinEvent, New-WinEvent}

    Directory: C:\WINDOWS\system32\WindowsPowerShell\v1.0\Modules

ModuleType Version    Name                                PSEdition ExportedCommands
---------- -------    ----                                --------- ----------------
Manifest   2.0.1.0    Appx                                Core,Desk {Add-AppxPackage, ... }
Script     1.0.0.0    AssignedAccess                      Core,Desk {Clear-AssignedAccess, ... }
Manifest   1.0.0.0    BitLocker                           Core,Desk {Unlock-BitLocker, ... }
```

### <span data-ttu-id="a27e5-165">Beispiel 7: Inventur aktualisierte Hilfedateien</span><span class="sxs-lookup"><span data-stu-id="a27e5-165">Example 7: Inventory updated help files</span></span>

<span data-ttu-id="a27e5-166">In diesem Beispiel erstellt das Skript `Get-UpdateHelpVersion.ps1` eine Inventur der aktualisierbaren Hilfedateien für jedes Modul und ihre Versionsnummern.</span><span class="sxs-lookup"><span data-stu-id="a27e5-166">In this example, the script `Get-UpdateHelpVersion.ps1` creates an inventory of the Updatable Help files for each module and their version numbers.</span></span>

<span data-ttu-id="a27e5-167">Das Skript identifiziert Module, die die aktualisierbare Hilfe unterstützen, mithilfe der **helpinfouri** -Eigenschaft von Modulen.</span><span class="sxs-lookup"><span data-stu-id="a27e5-167">The script identifies modules that support Updatable Help by using the **HelpInfoUri** property of modules.</span></span> <span data-ttu-id="a27e5-168">Bei Modulen, die die aktualisierbare Hilfe unterstützen, sucht das Skript nach der Hilfe Informationsdatei (\* helpinfo.xml) und analysiert sie, um die aktuelle Versionsnummer zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="a27e5-168">For modules that support Updatable Help, the script looks for and parses the help information file (\*helpinfo.xml) to find the latest version number.</span></span>

<span data-ttu-id="a27e5-169">Das Skript verwendet die **pscustomobject** -Klasse und eine Hash Tabelle zum Erstellen eines benutzerdefinierten Ausgabe Objekts.</span><span class="sxs-lookup"><span data-stu-id="a27e5-169">The script uses the **PSCustomObject** class and a hash table to create a custom output object.</span></span>

```powershell
# Get-UpdateHelpVersion.ps1
Param(
    [parameter(Mandatory=$False)]
    [String[]]
    $Module
)
$HelpInfoNamespace = @{helpInfo='http://schemas.microsoft.com/powershell/help/2010/05'}

if ($Module) { $Modules = Get-Module $Module -ListAvailable | where {$_.HelpInfoUri} }
else { $Modules = Get-Module -ListAvailable | where {$_.HelpInfoUri} }

foreach ($mModule in $Modules)
{
    $mDir = $mModule.ModuleBase

    if (Test-Path $mdir\*helpinfo.xml)
    {
        $mName=$mModule.Name
        $mNodes = dir $mdir\*helpinfo.xml -ErrorAction SilentlyContinue |
            Select-Xml -Namespace $HelpInfoNamespace -XPath "//helpInfo:UICulture"
        foreach ($mNode in $mNodes)
        {
            $mCulture=$mNode.Node.UICultureName
            $mVer=$mNode.Node.UICultureVersion

            [PSCustomObject]@{"ModuleName"=$mName; "Culture"=$mCulture; "Version"=$mVer}
        }
    }
}
```

```Output
ModuleName                              Culture                                 Version
----------                              -------                                 -------
ActiveDirectory                         en-US                                   3.0.0.0
ADCSAdministration                      en-US                                   3.0.0.0
ADCSDeployment                          en-US                                   3.0.0.0
ADDSDeployment                          en-US                                   3.0.0.0
ADFS                                    en-US                                   3.0.0.0
```

## <span data-ttu-id="a27e5-170">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a27e5-170">PARAMETERS</span></span>

### <span data-ttu-id="a27e5-171">-Credential</span><span class="sxs-lookup"><span data-stu-id="a27e5-171">-Credential</span></span>

<span data-ttu-id="a27e5-172">Gibt die Anmelde Informationen eines Benutzers an, der über die Berechtigung zum Zugriff auf den durch **SourcePath** angegebenen Dateisystem Speicherort verfügt.</span><span class="sxs-lookup"><span data-stu-id="a27e5-172">Specifies credentials of a user who has permission to access the file system location specified by **SourcePath**.</span></span> <span data-ttu-id="a27e5-173">Dieser Parameter ist nur gültig, wenn der **SourcePath**- oder **LiteralPath**-Parameter im Befehl verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a27e5-173">This parameter is valid only when the **SourcePath** or **LiteralPath** parameter is used in the command.</span></span>

<span data-ttu-id="a27e5-174">Mit dem **Credential** -Parameter können Sie `Update-Help` Befehle mit dem **SourcePath** -Parameter auf Remote Computern ausführen.</span><span class="sxs-lookup"><span data-stu-id="a27e5-174">The **Credential** parameter enables you to run `Update-Help` commands with the **SourcePath** parameter on remote computers.</span></span> <span data-ttu-id="a27e5-175">Durch die Angabe expliziter Anmelde Informationen können Sie den Befehl auf einem Remote Computer ausführen und auf eine Dateifreigabe auf einem dritten Computer zugreifen, ohne dass ein Zugriffs Verweigerungs Fehler aufgetreten ist oder die Verwendung der-Authentifizierung zum Delegieren von Anmelde Informationen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a27e5-175">By providing explicit credentials, you can run the command on a remote computer and access a file share on a third computer without encountering an access denied error or using CredSSP authentication to delegate credentials.</span></span>

<span data-ttu-id="a27e5-176">Geben Sie einen Benutzernamen ein, z. b. **USER01** oder **Domain01\User01**, oder geben Sie ein **PSCredential** -Objekt ein, das vom `Get-Credential` Cmdlet generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="a27e5-176">Type a user name, such as **User01** or **Domain01\User01**, or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="a27e5-177">Wenn Sie einen Benutzernamen eingeben, werden Sie zur Eingabe des Kennworts aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="a27e5-177">If you type a user name, you're prompted to enter the password.</span></span>

<span data-ttu-id="a27e5-178">Anmelde Informationen werden in einem [PSCredential](/dotnet/api/system.management.automation.pscredential) -Objekt gespeichert, und das Kennwort wird als [SecureString](/dotnet/api/system.security.securestring)gespeichert.</span><span class="sxs-lookup"><span data-stu-id="a27e5-178">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="a27e5-179">Weitere Informationen zum Schutz von **SecureString** -Daten finden Sie unter [wie sicher ist SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="a27e5-179">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a27e5-180">-Force</span><span class="sxs-lookup"><span data-stu-id="a27e5-180">-Force</span></span>

<span data-ttu-id="a27e5-181">Gibt an, dass dieses Cmdlet nicht die einmal pro Tag-Einschränkung befolgt, die Versions Überprüfung überspringt und Dateien herunterlädt, die den Grenzwert von 1 GB überschreiten.</span><span class="sxs-lookup"><span data-stu-id="a27e5-181">Indicates that this cmdlet doesn't follow the once-per-day limitation, skips version checking, and downloads files that exceed the 1 GB limit.</span></span>

<span data-ttu-id="a27e5-182">Ohne diesen Parameter wird `Update-Help` in jedem 24-Stunden-Zeitraum nur ein Mal ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="a27e5-182">Without this parameter, `Update-Help` runs only once in each 24-hour period.</span></span> <span data-ttu-id="a27e5-183">Downloads sind auf 1 GB an nicht komprimiertem Inhalt pro Modul beschränkt, und Hilfedateien werden nur installiert, wenn Sie neuer sind als die vorhandenen Dateien auf dem Computer.</span><span class="sxs-lookup"><span data-stu-id="a27e5-183">Downloads are limited to 1 GB of uncompressed content per module and help files are only installed when they're newer than the existing files on the computer.</span></span>

<span data-ttu-id="a27e5-184">Der Grenzwert von einmal täglich schützt die Server, die die Hilfedateien hosten, und ermöglicht es Ihnen, `Update-Help` Ihrem PowerShell-Profil einen Befehl hinzuzufügen, ohne dass die Ressourcenkosten für wiederholte Verbindungen oder Downloads anfallen.</span><span class="sxs-lookup"><span data-stu-id="a27e5-184">The once-per-day limit protects the servers that host the help files and makes it practical for you to add an `Update-Help` command to your PowerShell profile without incurring the resource cost of repeated connections or downloads.</span></span>

<span data-ttu-id="a27e5-185">Um die Hilfe für ein Modul in mehreren Benutzeroberflächenkulturen ohne den **Force**-Parameter zu aktualisieren, schließen Sie alle Benutzeroberflächenkulturen in denselben Befehl ein, z. B.:</span><span class="sxs-lookup"><span data-stu-id="a27e5-185">To update help for a module in multiple UI cultures without the **Force** parameter, include all UI cultures in the same command, such as:</span></span>

`Update-Help -Module PSScheduledJobs -UICulture en-US, fr-FR, pt-BR`

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

### <span data-ttu-id="a27e5-186">-Fullyqualifiedmodule</span><span class="sxs-lookup"><span data-stu-id="a27e5-186">-FullyQualifiedModule</span></span>

<span data-ttu-id="a27e5-187">Gibt Module an, deren Namen in Form von **modulespecification** -Objekten angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="a27e5-187">Specifies modules with names that are specified in the form of **ModuleSpecification** objects.</span></span>
<span data-ttu-id="a27e5-188">Diese Module werden im Abschnitt "Hinweise" des [modulespecification-Konstruktors (Hash Tabelle)](/dotnet/api/microsoft.powershell.commands.modulespecification.-ctor?view=powershellsdk-1.1.0#Microsoft_PowerShell_Commands_ModuleSpecification__ctor_System_Collections_Hashtable_)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a27e5-188">These modules are described in the Remarks section of [ModuleSpecification Constructor (Hashtable)](/dotnet/api/microsoft.powershell.commands.modulespecification.-ctor?view=powershellsdk-1.1.0#Microsoft_PowerShell_Commands_ModuleSpecification__ctor_System_Collections_Hashtable_).</span></span>

<span data-ttu-id="a27e5-189">Der **fullyqualifiedmodule** -Parameter akzeptiert z. b. einen Modulnamen, der im folgenden Format angegeben ist:</span><span class="sxs-lookup"><span data-stu-id="a27e5-189">For example, the **FullyQualifiedModule** parameter accepts a module name that is specified in the format:</span></span>

`@{ModuleName = "modulename"; ModuleVersion = "version_number"}`

<span data-ttu-id="a27e5-190">oder</span><span class="sxs-lookup"><span data-stu-id="a27e5-190">or</span></span>

`@{ModuleName = "modulename"; ModuleVersion = "version_number"; Guid = "GUID"}.`

<span data-ttu-id="a27e5-191">**ModuleName** und **ModuleVersion** sind erforderlich, aber **Guid** ist optional.</span><span class="sxs-lookup"><span data-stu-id="a27e5-191">**ModuleName** and **ModuleVersion** are required, but **Guid** is optional.</span></span>

<span data-ttu-id="a27e5-192">Sie können den **fullyqualifiedmodule** -Parameter nicht im selben Befehl wie einen **Modul** Parameter angeben.</span><span class="sxs-lookup"><span data-stu-id="a27e5-192">You can't specify the **FullyQualifiedModule** parameter in the same command as a **Module** parameter.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.ModuleSpecification[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="a27e5-193">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="a27e5-193">-LiteralPath</span></span>

<span data-ttu-id="a27e5-194">Gibt den Ordner für aktualisierte Hilfedateien an, anstatt Sie aus dem Internet herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="a27e5-194">Specifies the folder for updated help files instead of downloading them from the internet.</span></span> <span data-ttu-id="a27e5-195">Verwenden Sie diesen Parameter oder **SourcePath** , wenn Sie das `Save-Help` Cmdlet zum Herunterladen von Hilfedateien in ein Verzeichnis verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="a27e5-195">Use this parameter or **SourcePath** if you've used the `Save-Help` cmdlet to download help files to a directory.</span></span>

<span data-ttu-id="a27e5-196">Sie können ein Verzeichnis Objekt, z. b. aus den- `Get-Item` oder- `Get-ChildItem` Cmdlets, an Pipeline in Pipeline `Update-Help`</span><span class="sxs-lookup"><span data-stu-id="a27e5-196">You can pipeline a directory object, such as from the `Get-Item` or `Get-ChildItem` cmdlets, to `Update-Help`.</span></span>

<span data-ttu-id="a27e5-197">Im Gegensatz zum Wert von **SourcePath** wird der Wert von **literalpath** genau so verwendet, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="a27e5-197">Unlike the value of **SourcePath**, the value of **LiteralPath** is used exactly as it's typed.</span></span> <span data-ttu-id="a27e5-198">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="a27e5-198">No characters are interpreted as wildcard characters.</span></span> <span data-ttu-id="a27e5-199">Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="a27e5-199">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="a27e5-200">Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="a27e5-200">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath, LP

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="a27e5-201">-Modul</span><span class="sxs-lookup"><span data-stu-id="a27e5-201">-Module</span></span>

<span data-ttu-id="a27e5-202">Aktualisiert die Hilfe für die angegebenen Module.</span><span class="sxs-lookup"><span data-stu-id="a27e5-202">Updates help for the specified modules.</span></span> <span data-ttu-id="a27e5-203">Geben Sie mindestens einen Modulnamen oder ein Namensmuster in eine durch Trennzeichen getrennte Liste ein, oder geben Sie eine Datei an, in der in jeder Zeile ein Modulname aufgeführt ist.</span><span class="sxs-lookup"><span data-stu-id="a27e5-203">Enter one or more module names or name patterns in a comma-separated list, or specify a file that lists one module name on each line.</span></span> <span data-ttu-id="a27e5-204">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="a27e5-204">Wildcard characters are permitted.</span></span> <span data-ttu-id="a27e5-205">Sie können Module aus dem `Get-Module` Cmdlet an das `Update-Help` Cmdlet weitergeben.</span><span class="sxs-lookup"><span data-stu-id="a27e5-205">You can pipeline modules from the `Get-Module` cmdlet to the `Update-Help` cmdlet.</span></span>

<span data-ttu-id="a27e5-206">Die Module, die Sie angeben, müssen auf dem Computer installiert sein, aber Sie müssen nicht in die aktuelle Sitzung importiert werden.</span><span class="sxs-lookup"><span data-stu-id="a27e5-206">The modules that you specify must be installed on the computer, but they don't have to be imported into the current session.</span></span> <span data-ttu-id="a27e5-207">Sie können ein beliebiges Modul in der Sitzung oder ein beliebiges Modul angeben, das an einem in der Umgebungsvariablen aufgeführten Speicherort installiert ist `$env:PSModulePath` .</span><span class="sxs-lookup"><span data-stu-id="a27e5-207">You can specify any module in the session or any module that is installed in a location listed in the `$env:PSModulePath` environment variable.</span></span>

<span data-ttu-id="a27e5-208">Der Wert `*` (alle) versucht, die Hilfe für alle Module zu aktualisieren, die auf dem Computer installiert sind.</span><span class="sxs-lookup"><span data-stu-id="a27e5-208">A value of `*` (all) attempts to update help for all modules that are installed on the computer.</span></span>
<span data-ttu-id="a27e5-209">Module, die keine aktualisierbare Hilfe unterstützen, sind enthalten.</span><span class="sxs-lookup"><span data-stu-id="a27e5-209">Modules that don't support Updatable Help are included.</span></span> <span data-ttu-id="a27e5-210">Dieser Wert generiert möglicherweise Fehler, wenn der Befehl Module erkennt, die die aktualisierbare Hilfe nicht unterstützen.</span><span class="sxs-lookup"><span data-stu-id="a27e5-210">This value might generate errors when the command encounters modules that don't support Updatable Help.</span></span> <span data-ttu-id="a27e5-211">Führen Sie stattdessen `Update-Help` ohne Parameter aus.</span><span class="sxs-lookup"><span data-stu-id="a27e5-211">Instead, run `Update-Help` without parameters.</span></span>

<span data-ttu-id="a27e5-212">Der **Modul** Parameter des `Update-Help` Cmdlets akzeptiert nicht den vollständigen Pfad einer Modul Datei oder Modul Manifest-Datei.</span><span class="sxs-lookup"><span data-stu-id="a27e5-212">The **Module** parameter of the `Update-Help` cmdlet doesn't accept the full path of a module file or module manifest file.</span></span> <span data-ttu-id="a27e5-213">Um die Hilfe für ein Modul zu aktualisieren, das sich nicht an einem `$env:PSModulePath` Speicherort befindet, importieren Sie das Modul in die aktuelle Sitzung, bevor Sie den `Update-Help` Befehl ausführen.</span><span class="sxs-lookup"><span data-stu-id="a27e5-213">To update help for a module that isn't in a `$env:PSModulePath` location, import the module into the current session before you run the `Update-Help` command.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Name

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="a27e5-214">-Recurse</span><span class="sxs-lookup"><span data-stu-id="a27e5-214">-Recurse</span></span>

<span data-ttu-id="a27e5-215">Führt eine rekursive Suche nach Hilfedateien im angegebenen Verzeichnis aus.</span><span class="sxs-lookup"><span data-stu-id="a27e5-215">Performs a recursive search for help files in the specified directory.</span></span> <span data-ttu-id="a27e5-216">Dieser Parameter ist nur gültig, wenn der Befehl den **SourcePath** -Parameter verwendet.</span><span class="sxs-lookup"><span data-stu-id="a27e5-216">This parameter is valid only when the command uses the **SourcePath** parameter.</span></span>

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

### <span data-ttu-id="a27e5-217">-Bereich</span><span class="sxs-lookup"><span data-stu-id="a27e5-217">-Scope</span></span>

<span data-ttu-id="a27e5-218">Gibt den Systembereich an, in dem die Hilfe aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="a27e5-218">Specifies the system scope where help is updated.</span></span> <span data-ttu-id="a27e5-219">Updates im Bereich " **ALLUSERS** " erfordern Administratorrechte auf Windows-Systemen.</span><span class="sxs-lookup"><span data-stu-id="a27e5-219">Updates at the **AllUsers** scope require administrative privileges on Windows systems.</span></span> <span data-ttu-id="a27e5-220">Der- `-Scope` Parameter wurde in PowerShell Core Version 6,1 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="a27e5-220">The `-Scope` parameter was introduced in PowerShell Core version 6.1.</span></span>

<span data-ttu-id="a27e5-221">**CurrentUser** ist der Standardbereich für Hilfedateien in PowerShell 6,1 und höher.</span><span class="sxs-lookup"><span data-stu-id="a27e5-221">**CurrentUser** is the default scope for help files in PowerShell 6.1 and above.</span></span> <span data-ttu-id="a27e5-222">**ALLUSERS** können angegeben werden, um die Hilfe für alle Benutzer zu installieren oder zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="a27e5-222">**AllUsers** can be specified to install or update help for all users.</span></span> <span data-ttu-id="a27e5-223">Auf UNIX-Systemen `sudo` sind Berechtigungen erforderlich, um die Hilfe für alle Benutzer zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="a27e5-223">On Unix systems `sudo` privileges are required to update help for all users.</span></span> <span data-ttu-id="a27e5-224">Beispiel: `sudo pwsh -c Update-Help`</span><span class="sxs-lookup"><span data-stu-id="a27e5-224">For example: `sudo pwsh -c Update-Help`</span></span>

<span data-ttu-id="a27e5-225">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="a27e5-225">The acceptable values are:</span></span>

- <span data-ttu-id="a27e5-226">CurrentUser</span><span class="sxs-lookup"><span data-stu-id="a27e5-226">CurrentUser</span></span>
- <span data-ttu-id="a27e5-227">ALLUSERS</span><span class="sxs-lookup"><span data-stu-id="a27e5-227">AllUsers</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.UpdateHelpScope
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: CurrentUser
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="a27e5-228">-SourcePath</span><span class="sxs-lookup"><span data-stu-id="a27e5-228">-SourcePath</span></span>

<span data-ttu-id="a27e5-229">Gibt einen Dateisystem Ordner `Update-Help` an, in dem aktualisierte Hilfedateien abruft, anstatt Sie aus dem Internet herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="a27e5-229">Specifies a file system folder where `Update-Help` gets updated help files, instead of downloading them from the internet.</span></span> <span data-ttu-id="a27e5-230">Geben Sie den Pfad eines Ordners ein.</span><span class="sxs-lookup"><span data-stu-id="a27e5-230">Enter the path of a folder.</span></span> <span data-ttu-id="a27e5-231">Geben Sie keinen Dateinamen oder keine Dateinamenerweiterung an.</span><span class="sxs-lookup"><span data-stu-id="a27e5-231">Don't specify a file name or file name extension.</span></span> <span data-ttu-id="a27e5-232">Sie können einen Ordner, z. b. einen aus dem- `Get-Item` `Get-ChildItem` Cmdlet oder den-Cmdlet, in Pipeline `Update-Help`</span><span class="sxs-lookup"><span data-stu-id="a27e5-232">You can pipeline a folder, such as one from the `Get-Item` or `Get-ChildItem` cmdlets, to `Update-Help`.</span></span>

<span data-ttu-id="a27e5-233">Standardmäßig werden `Update-Help` aktualisierte Hilfedateien aus dem Internet heruntergeladen.</span><span class="sxs-lookup"><span data-stu-id="a27e5-233">By default, `Update-Help` downloads updated help files from the internet.</span></span> <span data-ttu-id="a27e5-234">Verwenden Sie **SourcePath** , wenn Sie das `Save-Help` Cmdlet zum Herunterladen aktualisierter Hilfedateien in ein Verzeichnis verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="a27e5-234">Use **SourcePath** when you've used the `Save-Help` cmdlet to download updated help files to a directory.</span></span>

<span data-ttu-id="a27e5-235">Um einen Standardwert für **SourcePath** anzugeben, navigieren Sie zu **Gruppenrichtlinie**, **Computer Konfiguration**, und **legen Sie den standardmäßigen Quellpfad für Update-Help fest**.</span><span class="sxs-lookup"><span data-stu-id="a27e5-235">To specify a default value for **SourcePath**, go to **Group Policy**, **Computer Configuration**, and **Set the default source path for Update-Help**.</span></span> <span data-ttu-id="a27e5-236">Diese Gruppenrichtlinie Einstellung verhindert, dass Benutzer `Update-Help` zum Herunterladen von Hilfedateien aus dem Internet verwenden.</span><span class="sxs-lookup"><span data-stu-id="a27e5-236">This Group Policy setting prevents users from using `Update-Help` to download help files from the internet.</span></span>
<span data-ttu-id="a27e5-237">Weitere Informationen finden Sie unter [about_Group_Policy_Settings](./About/about_Group_Policy_Settings.md).</span><span class="sxs-lookup"><span data-stu-id="a27e5-237">For more information, see [about_Group_Policy_Settings](./About/about_Group_Policy_Settings.md).</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases: Path

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a27e5-238">-UICulture</span><span class="sxs-lookup"><span data-stu-id="a27e5-238">-UICulture</span></span>

<span data-ttu-id="a27e5-239">Gibt UI-Kultur Werte `Update-Help` an, die von zum erhalten aktualisierter Hilfedateien verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a27e5-239">Specifies UI culture values that `Update-Help` uses to get updated help files.</span></span> <span data-ttu-id="a27e5-240">Geben Sie einen oder mehrere Sprachcodes ein, z. b. **es-es**, eine Variable, die Kultur Objekte enthält, oder einen Befehl, der Kultur Objekte abruft, z. b. einen- `Get-Culture` oder- `Get-UICulture` Befehl.</span><span class="sxs-lookup"><span data-stu-id="a27e5-240">Enter one or more language codes, such as **es-ES**, a variable that contains culture objects, or a command that gets culture objects, such as a `Get-Culture` or `Get-UICulture` command.</span></span> <span data-ttu-id="a27e5-241">Platzhalter Zeichen sind nicht zulässig, und Sie können keinen partiellen Sprachcode, z. b. **de**, senden.</span><span class="sxs-lookup"><span data-stu-id="a27e5-241">Wildcard characters aren't permitted and you can't submit a partial language code, such as **de**.</span></span>

<span data-ttu-id="a27e5-242">Standardmäßig ruft `Update-Help` Hilfedateien in der Benutzeroberflächen Kultur ab, die für das Betriebssystem festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="a27e5-242">By default, `Update-Help` gets help files in the UI culture set for the operating system.</span></span> <span data-ttu-id="a27e5-243">Wenn Sie den **UICulture** -Parameter angeben, `Update-Help` sucht nur nach Hilfe für die angegebene Benutzeroberflächen Kultur.</span><span class="sxs-lookup"><span data-stu-id="a27e5-243">If you specify the **UICulture** parameter, `Update-Help` looks for help only for the specified UI culture.</span></span>

> [!NOTE]
> <span data-ttu-id="a27e5-244">Ubuntu 18,04 hat die Standardeinstellung für das Gebiets Schema in geändert `C.UTF.8` . Dies ist keine erkannte Benutzeroberflächen Kultur.</span><span class="sxs-lookup"><span data-stu-id="a27e5-244">Ubuntu 18.04 changed the default locale setting to `C.UTF.8`, which is not a recognized UI culture.</span></span> <span data-ttu-id="a27e5-245">`Update-Help` Wenn Sie diesen Parameter nicht mit einem unterstützten Gebiets Schema wie verwenden, wird die Hilfe im Hintergrund nicht heruntergeladen `en-US` .</span><span class="sxs-lookup"><span data-stu-id="a27e5-245">`Update-Help` silently fails to download help unless you use this parameter with a supported locale like `en-US`.</span></span> <span data-ttu-id="a27e5-246">Dies kann auf jeder Plattform vorkommen, die einen nicht unterstützten Wert verwendet.</span><span class="sxs-lookup"><span data-stu-id="a27e5-246">This could occur on any platform that uses an unsupported value.</span></span>

<span data-ttu-id="a27e5-247">Befehle, die den **UICulture**-Parameter verwenden, werden nur dann erfolgreich ausgeführt, wenn das Modul Hilfedateien für die angegebene Benutzeroberflächenkultur bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="a27e5-247">Commands that use the **UICulture** parameter succeed only when the module provides help files for the specified UI culture.</span></span> <span data-ttu-id="a27e5-248">Wenn der Befehl fehlschlägt, da die angegebene Benutzeroberflächen Kultur nicht unterstützt wird, wird eine Fehlermeldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a27e5-248">If the command fails because the specified UI culture isn't supported, an error message is displayed.</span></span>

```yaml
Type: System.Globalization.CultureInfo[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a27e5-249">-Usedefault-Anmelde Informationen</span><span class="sxs-lookup"><span data-stu-id="a27e5-249">-UseDefaultCredentials</span></span>

<span data-ttu-id="a27e5-250">Gibt an, dass `Update-Help` den Befehl, einschließlich des Internet Downloads, mithilfe der Anmelde Informationen des aktuellen Benutzers ausführt.</span><span class="sxs-lookup"><span data-stu-id="a27e5-250">Indicates that `Update-Help` runs the command, including the internet download, by using the credentials of the current user.</span></span> <span data-ttu-id="a27e5-251">Standardmäßig wird der Befehl ohne explizite Anmeldeinformationen ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="a27e5-251">By default, the command runs without explicit credentials.</span></span>

<span data-ttu-id="a27e5-252">Dieser Parameter ist nur wirksam, wenn der Webdownload NT LAN Manager (NTLM), Aushandlung oder Kerberos-basierte Authentifizierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="a27e5-252">This parameter is effective only when the web download uses NT LAN Manager (NTLM), negotiate, or Kerberos-based authentication.</span></span>

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

### <span data-ttu-id="a27e5-253">-Confirm</span><span class="sxs-lookup"><span data-stu-id="a27e5-253">-Confirm</span></span>

<span data-ttu-id="a27e5-254">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="a27e5-254">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="a27e5-255">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="a27e5-255">-WhatIf</span></span>

<span data-ttu-id="a27e5-256">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a27e5-256">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="a27e5-257">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="a27e5-257">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="a27e5-258">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="a27e5-258">CommonParameters</span></span>

<span data-ttu-id="a27e5-259">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="a27e5-259">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a27e5-260">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="a27e5-260">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a27e5-261">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="a27e5-261">INPUTS</span></span>

### <span data-ttu-id="a27e5-262">System. IO. directoriyinfo</span><span class="sxs-lookup"><span data-stu-id="a27e5-262">System.IO.DirectoryInfo</span></span>

<span data-ttu-id="a27e5-263">Sie können einen Verzeichnispfad an über die Pipeline übergeben `Update-Help` .</span><span class="sxs-lookup"><span data-stu-id="a27e5-263">You can pipe a directory path to `Update-Help`.</span></span>

### <span data-ttu-id="a27e5-264">System. Management. Automation. psmoduleinfo</span><span class="sxs-lookup"><span data-stu-id="a27e5-264">System.Management.Automation.PSModuleInfo</span></span>

<span data-ttu-id="a27e5-265">Sie können ein Modul Objekt über die Pipeline aus dem `Get-Module` Cmdlet an übergeben `Update-Help` .</span><span class="sxs-lookup"><span data-stu-id="a27e5-265">You can pipe a module object from the `Get-Module` cmdlet to `Update-Help`.</span></span>

## <span data-ttu-id="a27e5-266">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="a27e5-266">OUTPUTS</span></span>

### <span data-ttu-id="a27e5-267">Keine</span><span class="sxs-lookup"><span data-stu-id="a27e5-267">None</span></span>

<span data-ttu-id="a27e5-268">`Update-Help` generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="a27e5-268">`Update-Help` doesn't generate any output.</span></span>

## <span data-ttu-id="a27e5-269">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="a27e5-269">NOTES</span></span>

<span data-ttu-id="a27e5-270">Um die Hilfe für die PowerShell-Kernmodule zu aktualisieren, die die Befehle enthalten, die mit PowerShell installiert werden, oder ein beliebiges Modul im `$PSHOME\Modules` Verzeichnis, starten Sie PowerShell mit der Option **als Administrator ausführen**.</span><span class="sxs-lookup"><span data-stu-id="a27e5-270">To update help for the PowerShell Core modules, that contain the commands that are installed with PowerShell, or any module in the `$PSHOME\Modules` directory, start PowerShell with the option to **Run as administrator**.</span></span>

<span data-ttu-id="a27e5-271">Nur Mitglieder der Gruppe "Administratoren" auf dem Computer können die Hilfe für die PowerShell-Kernmodule, die Befehle, die mit PowerShell installiert werden, und für Module im `$PSHOME\Modules` Ordner aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="a27e5-271">Only members of the Administrators group on the computer can update help for the PowerShell Core modules, the commands that are installed together with PowerShell, and for modules in the `$PSHOME\Modules` folder.</span></span> <span data-ttu-id="a27e5-272">Wenn Sie keine Berechtigung zum Aktualisieren von Hilfedateien haben, können Sie die Hilfedateien Online lesen.</span><span class="sxs-lookup"><span data-stu-id="a27e5-272">If you don't have permission to update help files, you can read the help files online.</span></span> <span data-ttu-id="a27e5-273">Beispiel: `Get-Help Update-Help -Online`.</span><span class="sxs-lookup"><span data-stu-id="a27e5-273">For example, `Get-Help Update-Help -Online`.</span></span>

<span data-ttu-id="a27e5-274">Module sind die kleinste Einheit der aktualisierbaren Hilfe.</span><span class="sxs-lookup"><span data-stu-id="a27e5-274">Modules are the smallest unit of updatable help.</span></span> <span data-ttu-id="a27e5-275">Sie können die Hilfe für ein bestimmtes Cmdlet nicht aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="a27e5-275">You can't update help for a particular cmdlet.</span></span> <span data-ttu-id="a27e5-276">Um das Modul zu suchen, das ein bestimmtes Cmdlet enthält, verwenden Sie die **ModuleName** -Eigenschaft des `Get-Command` Cmdlets, z `(Get-Command Update-Help).ModuleName` . b..</span><span class="sxs-lookup"><span data-stu-id="a27e5-276">To find the module that contains a particular cmdlet, use the **ModuleName** property of the `Get-Command` cmdlet, for example, `(Get-Command Update-Help).ModuleName`.</span></span>

<span data-ttu-id="a27e5-277">Da Hilfedateien im Modul Verzeichnis installiert werden, kann das `Update-Help` Cmdlet die aktualisierte Hilfedatei nur für Module installieren, die auf dem Computer installiert sind.</span><span class="sxs-lookup"><span data-stu-id="a27e5-277">Because help files are installed in the module directory, the `Update-Help` cmdlet can install updated help file only for modules that are installed on the computer.</span></span> <span data-ttu-id="a27e5-278">Allerdings `Save-Help` kann das Cmdlet die Hilfe für Module speichern, die nicht auf dem Computer installiert sind.</span><span class="sxs-lookup"><span data-stu-id="a27e5-278">However, the `Save-Help` cmdlet can save help for modules that aren't installed on the computer.</span></span>

<span data-ttu-id="a27e5-279">Wenn `Update-Help` keine aktualisierten Hilfedateien für ein Modul finden oder die aktualisierte Hilfe nicht in der angegebenen Sprache finden kann, wird Sie ohne Anzeige einer Fehlermeldung automatisch fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="a27e5-279">If `Update-Help` can't find updated help files for a module, or can't find updated help in the specified language, it continues silently without displaying an error message.</span></span> <span data-ttu-id="a27e5-280">Verwenden Sie zum Anzeigen des Status und der Fortschrittsdetails den **Verbose**-Parameter.</span><span class="sxs-lookup"><span data-stu-id="a27e5-280">To see status and progress details, use the **Verbose** parameter.</span></span>

<span data-ttu-id="a27e5-281">Das `Update-Help` Cmdlet wurde in Windows PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="a27e5-281">The `Update-Help` cmdlet was introduced in Windows PowerShell 3.0.</span></span> <span data-ttu-id="a27e5-282">Dies funktioniert nicht in früheren Versionen von PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a27e5-282">It doesn't work in earlier versions of PowerShell.</span></span> <span data-ttu-id="a27e5-283">Verwenden Sie auf Computern mit Windows PowerShell 2,0 und Windows PowerShell 3,0 das `Update-Help` -Cmdlet in einer Windows PowerShell 3,0-Sitzung, um Hilfedateien herunterzuladen und zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="a27e5-283">On computers that have both Windows PowerShell 2.0 and Windows PowerShell 3.0, use the `Update-Help` cmdlet in a Windows PowerShell 3.0 session to download and update help files.</span></span> <span data-ttu-id="a27e5-284">Die Hilfedateien sind sowohl für Windows PowerShell 2,0 als auch für Windows PowerShell 3,0 verfügbar.</span><span class="sxs-lookup"><span data-stu-id="a27e5-284">The help files are available to both Windows PowerShell 2.0 and Windows PowerShell 3.0.</span></span>

<span data-ttu-id="a27e5-285">Die `Update-Help` -und- `Save-Help` Cmdlets verwenden die folgenden Ports, um Hilfedateien herunterzuladen: Port 80 für http und Port 443 für HTTPS.</span><span class="sxs-lookup"><span data-stu-id="a27e5-285">The `Update-Help` and `Save-Help` cmdlets use the following ports to download help files: Port 80 for HTTP and port 443 for HTTPS.</span></span>

<span data-ttu-id="a27e5-286">`Update-Help` unterstützt alle Module und die PowerShell-Kern-Snap-Ins. Es werden keine anderen Snap-Ins unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a27e5-286">`Update-Help` supports all modules and the PowerShell Core snap-ins. It doesn't support any other snap-ins.</span></span>

<span data-ttu-id="a27e5-287">Um die Hilfe für ein Modul an einem Speicherort zu aktualisieren, der nicht in der `$env:PSModulePath` Umgebungsvariablen aufgeführt ist, importieren Sie das Modul in die aktuelle Sitzung, und führen Sie dann einen `Update-Help` Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="a27e5-287">To update help for a module in a location that isn't listed in the `$env:PSModulePath` environment variable, import the module into the current session and then run an `Update-Help` command.</span></span> <span data-ttu-id="a27e5-288">Führen `Update-Help` Sie ohne Parameter aus, oder verwenden Sie den **Module** -Parameter, um den Modulnamen anzugeben.</span><span class="sxs-lookup"><span data-stu-id="a27e5-288">Run `Update-Help` without parameters or use the **Module** parameter to specify the module name.</span></span> <span data-ttu-id="a27e5-289">Der **Modul** Parameter der `Update-Help` -und- `Save-Help` Cmdlets akzeptiert nicht den vollständigen Pfad einer Modul Datei oder Modul Manifest-Datei.</span><span class="sxs-lookup"><span data-stu-id="a27e5-289">The **Module** parameter of the `Update-Help` and `Save-Help` cmdlets doesn't accept the full path of a module file or module manifest file.</span></span>

<span data-ttu-id="a27e5-290">Jedes Modul kann die aktualisierbare Hilfe unterstützen.</span><span class="sxs-lookup"><span data-stu-id="a27e5-290">Any module can support Updatable Help.</span></span> <span data-ttu-id="a27e5-291">Anweisungen zur Unterstützung der aktualisierbaren Hilfe in den Modulen, die Sie erstellen, finden Sie [unter unterstützen der aktualisierbaren](/powershell/scripting/developer/module/supporting-updatable-help)</span><span class="sxs-lookup"><span data-stu-id="a27e5-291">For instructions for supporting Updatable Help in the modules that you author, see [Supporting Updatable Help](/powershell/scripting/developer/module/supporting-updatable-help).</span></span>

<span data-ttu-id="a27e5-292">Die `Update-Help` `Save-Help` Cmdlets und werden auf Windows Preinstallation Environment (Windows PE) nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a27e5-292">The `Update-Help` and `Save-Help` cmdlets are not supported on Windows Preinstallation Environment (Windows PE).</span></span>

## <span data-ttu-id="a27e5-293">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="a27e5-293">RELATED LINKS</span></span>

[<span data-ttu-id="a27e5-294">Get-Culture</span><span class="sxs-lookup"><span data-stu-id="a27e5-294">Get-Culture</span></span>](../Microsoft.PowerShell.Utility/Get-Culture.md)

[<span data-ttu-id="a27e5-295">Get-Help</span><span class="sxs-lookup"><span data-stu-id="a27e5-295">Get-Help</span></span>](Get-Help.md)

[<span data-ttu-id="a27e5-296">Get-Module</span><span class="sxs-lookup"><span data-stu-id="a27e5-296">Get-Module</span></span>](Get-Module.md)

[<span data-ttu-id="a27e5-297">Get-UICulture</span><span class="sxs-lookup"><span data-stu-id="a27e5-297">Get-UICulture</span></span>](../Microsoft.PowerShell.Utility/Get-UICulture.md)

[<span data-ttu-id="a27e5-298">Start-Job</span><span class="sxs-lookup"><span data-stu-id="a27e5-298">Start-Job</span></span>](Start-Job.md)

[<span data-ttu-id="a27e5-299">Save-Help</span><span class="sxs-lookup"><span data-stu-id="a27e5-299">Save-Help</span></span>](Save-Help.md)
