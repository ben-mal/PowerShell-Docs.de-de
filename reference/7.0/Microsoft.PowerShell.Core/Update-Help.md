---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 5/16/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/update-help?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Update-Help
ms.openlocfilehash: 541059691e794591e85a8321a4507ed8838bcb4a
ms.sourcegitcommit: d3f78120bdc9096c72aa0dfdbdd91efaf254c738
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "93219127"
---
# <span data-ttu-id="28dc2-103">Update-Help</span><span class="sxs-lookup"><span data-stu-id="28dc2-103">Update-Help</span></span>

## <span data-ttu-id="28dc2-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="28dc2-104">SYNOPSIS</span></span>
<span data-ttu-id="28dc2-105">Lädt die neuesten Hilfedateien auf den Computer herunter und installiert sie.</span><span class="sxs-lookup"><span data-stu-id="28dc2-105">Downloads and installs the newest help files on your computer.</span></span>

## <span data-ttu-id="28dc2-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="28dc2-106">SYNTAX</span></span>

### <span data-ttu-id="28dc2-107">Pfad (Standard)</span><span class="sxs-lookup"><span data-stu-id="28dc2-107">Path (Default)</span></span>

```
Update-Help [[-Module] <String[]>] [-FullyQualifiedModule <ModuleSpecification[]>]
 [[-SourcePath] <String[]>] [-Recurse] [[-UICulture] <CultureInfo[]>] [-Credential <PSCredential>]
 [-UseDefaultCredentials] [-Force] [-Scope <UpdateHelpScope>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="28dc2-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="28dc2-108">LiteralPath</span></span>

```
Update-Help [[-Module] <String[]>] [-FullyQualifiedModule <ModuleSpecification[]>]
 [-LiteralPath <String[]>] [-Recurse] [[-UICulture] <CultureInfo[]>] [-Credential <PSCredential>]
 [-UseDefaultCredentials] [-Force] [-Scope <UpdateHelpScope>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="28dc2-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="28dc2-109">DESCRIPTION</span></span>

<span data-ttu-id="28dc2-110">Das `Update-Help` Cmdlet lädt die neuesten Hilfedateien für PowerShell-Module herunter und installiert Sie auf Ihrem Computer.</span><span class="sxs-lookup"><span data-stu-id="28dc2-110">The `Update-Help` cmdlet downloads the newest help files for PowerShell modules and installs them on your computer.</span></span> <span data-ttu-id="28dc2-111">PowerShell muss nicht neu gestartet werden, damit die Änderung wirksam wird.</span><span class="sxs-lookup"><span data-stu-id="28dc2-111">You need not restart PowerShell to make the change effective.</span></span> <span data-ttu-id="28dc2-112">Mit dem- `Get-Help` Cmdlet können Sie die neuen Hilfedateien sofort anzeigen.</span><span class="sxs-lookup"><span data-stu-id="28dc2-112">You can use the `Get-Help` cmdlet to view the new help files immediately.</span></span>

<span data-ttu-id="28dc2-113">`Update-Help` Hiermit wird die Version der Hilfedateien auf Ihrem Computer überprüft.</span><span class="sxs-lookup"><span data-stu-id="28dc2-113">`Update-Help` checks the version of the help files on your computer.</span></span> <span data-ttu-id="28dc2-114">Wenn Sie keine Hilfedateien für ein Modul haben oder wenn Ihre Hilfedateien veraltet sind, werden `Update-Help` die neuesten Hilfedateien heruntergeladen.</span><span class="sxs-lookup"><span data-stu-id="28dc2-114">If you don't have help files for a module or if your help files are outdated, `Update-Help` downloads the newest help files.</span></span> <span data-ttu-id="28dc2-115">Die Hilfedateien können aus dem Internet oder aus einer Dateifreigabe heruntergeladen und installiert werden.</span><span class="sxs-lookup"><span data-stu-id="28dc2-115">The help files can be downloaded and installed from the internet or a file share.</span></span>

<span data-ttu-id="28dc2-116">Ohne Parameter `Update-Help` aktualisiert die Hilfedateien für Module in der Sitzung und für alle installierten Module, die die aktualisierbare Hilfe unterstützen.</span><span class="sxs-lookup"><span data-stu-id="28dc2-116">Without parameters, `Update-Help` updates the help files for modules in the session and for all installed modules that support Updatable Help.</span></span> <span data-ttu-id="28dc2-117">Module, die installiert, aber nicht in der aktuellen Sitzung geladen werden, sind eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="28dc2-117">Modules that are installed but not loaded in the current session are included.</span></span> <span data-ttu-id="28dc2-118">PowerShell-Module werden an einem Speicherort gespeichert, der in der `$env:PSModulePath` Umgebungsvariablen aufgeführt ist.</span><span class="sxs-lookup"><span data-stu-id="28dc2-118">PowerShell modules are stored in a location listed in the `$env:PSModulePath` environment variable.</span></span> <span data-ttu-id="28dc2-119">Weitere Informationen hierzu finden Sie unter [about_Updatable_Help](./About/about_Updatable_Help.md).</span><span class="sxs-lookup"><span data-stu-id="28dc2-119">For more information, see [about_Updatable_Help](./About/about_Updatable_Help.md).</span></span>

<span data-ttu-id="28dc2-120">Sie können den **Module** -Parameter verwenden, um Hilfedateien für ein bestimmtes Modul zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="28dc2-120">You can use the **Module** parameter to update help files for a particular module.</span></span> <span data-ttu-id="28dc2-121">Verwenden Sie den **UICulture** -Parameter, um Hilfedateien in mehreren Sprachen und Gebiets Schemas herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="28dc2-121">Use the **UICulture** parameter to download help files in multiple languages and locales.</span></span>

<span data-ttu-id="28dc2-122">Sie können auch `Update-Help` auf Computern verwenden, die nicht mit dem Internet verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="28dc2-122">You can also use `Update-Help` on computers that are not connected to the internet.</span></span> <span data-ttu-id="28dc2-123">Verwenden Sie zunächst das `Save-Help` Cmdlet, um Hilfedateien aus dem Internet herunterzuladen, und speichern Sie Sie in einem freigegebenen Ordner, der für das System verfügbar ist, das nicht mit dem Internet verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="28dc2-123">First, use the `Save-Help`cmdlet to download help files from the internet and save them in a shared folder that is accessible to the system not connected to the internet.</span></span> <span data-ttu-id="28dc2-124">Verwenden Sie dann den **SourcePath** -Parameter von `Update-Help` , um die aktualisierten Hilfedateien aus dem freigegebenen herunterzuladen und auf dem Computer zu installieren.</span><span class="sxs-lookup"><span data-stu-id="28dc2-124">Then use the **SourcePath** parameter of `Update-Help` to download the updated help files from the shared and install them on the computer.</span></span>

<span data-ttu-id="28dc2-125">Sie können Hilfe Updates automatisieren, indem Sie das `Update-Help` Cmdlet Ihrem PowerShell-Profil hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="28dc2-125">You can automate help updates by adding the `Update-Help` cmdlet to your PowerShell profile.</span></span> <span data-ttu-id="28dc2-126">Standardmäßig wird `Update-Help` auf jedem Computer nur einmal pro Tag ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="28dc2-126">By default, `Update-Help` runs only one time per day on each computer.</span></span> <span data-ttu-id="28dc2-127">Um den Grenzwert von einmal täglich zu überschreiben, verwenden Sie den **Force** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="28dc2-127">To override the once-per-day limit, use the **Force** parameter.</span></span>

<span data-ttu-id="28dc2-128">Das `Update-Help` Cmdlet wurde in Windows PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="28dc2-128">The `Update-Help` cmdlet was introduced in Windows PowerShell 3.0.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="28dc2-129">`Update-Help` erfordert Administratorrechte in PowerShell 6,0 und niedriger.</span><span class="sxs-lookup"><span data-stu-id="28dc2-129">`Update-Help` requires administrative privileges in PowerShell 6.0 and below.</span></span>
> <span data-ttu-id="28dc2-130">Mit PowerShell 6,1 und höher wird der Standard **Bereich** auf festgelegt `CurrentUser` .</span><span class="sxs-lookup"><span data-stu-id="28dc2-130">PowerShell 6.1 and above set the default **Scope** to `CurrentUser`.</span></span>
> <span data-ttu-id="28dc2-131">Vor PowerShell 6,1 war der **Bereichs** Parameter nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="28dc2-131">Prior to PowerShell 6.1, the **Scope** parameter was not available.</span></span>
>
> <span data-ttu-id="28dc2-132">Sie müssen Mitglied der Gruppe "Administratoren" auf dem Computer sein, um die Hilfedateien für die PowerShell-Kernmodule zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="28dc2-132">You must be a member of the Administrators group on the computer to update the help files for the PowerShell Core modules.</span></span>
>
> <span data-ttu-id="28dc2-133">Zum Herunterladen oder Aktualisieren der Hilfedateien für Module im PowerShell-Installationsverzeichnis ( `$PSHOME\Modules` ), einschließlich der PowerShell-Kernmodule, starten Sie PowerShell mit der Option **als Administrator ausführen** .</span><span class="sxs-lookup"><span data-stu-id="28dc2-133">To download or update the help files for modules in the PowerShell installation directory (`$PSHOME\Modules`), including the PowerShell Core modules, start PowerShell by using the **Run as administrator** option.</span></span>
> <span data-ttu-id="28dc2-134">Ein Beispiel für die Camel-Case-Schreibweise lautet: `Start-Process pwsh.exe -Verb RunAs`.</span><span class="sxs-lookup"><span data-stu-id="28dc2-134">For example: `Start-Process pwsh.exe -Verb RunAs`.</span></span>

## <span data-ttu-id="28dc2-135">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="28dc2-135">EXAMPLES</span></span>

### <span data-ttu-id="28dc2-136">Beispiel 1: Aktualisieren der Hilfedateien für alle Module</span><span class="sxs-lookup"><span data-stu-id="28dc2-136">Example 1: Update help files for all modules</span></span>

<span data-ttu-id="28dc2-137">Das- `Update-Help` Cmdlet aktualisiert Hilfedateien für installierte Module, die die aktualisierbare Hilfe unterstützen.</span><span class="sxs-lookup"><span data-stu-id="28dc2-137">The `Update-Help` cmdlet updates help files for installed modules that support Updatable Help.</span></span> <span data-ttu-id="28dc2-138">Die Kultur Sprache der Benutzeroberfläche (UI) wird im Betriebssystem festgelegt.</span><span class="sxs-lookup"><span data-stu-id="28dc2-138">The user-interface (UI) culture language is set in the operating system.</span></span>

```powershell
Update-Help
```

### <span data-ttu-id="28dc2-139">Beispiel 2: Aktualisieren der Hilfedateien für angegebene Module</span><span class="sxs-lookup"><span data-stu-id="28dc2-139">Example 2: Update help files for specified modules</span></span>

<span data-ttu-id="28dc2-140">Das `Update-Help` Cmdlet aktualisiert Hilfedateien nur für Modulnamen, die mit **Microsoft. PowerShell** beginnen.</span><span class="sxs-lookup"><span data-stu-id="28dc2-140">The `Update-Help` cmdlet updates help files only for module names that begin with **Microsoft.PowerShell**.</span></span>

```powershell
Update-Help -Module Microsoft.PowerShell*
```

### <span data-ttu-id="28dc2-141">Beispiel 3: Aktualisieren von Hilfedateien für verschiedene Sprachen</span><span class="sxs-lookup"><span data-stu-id="28dc2-141">Example 3: Update help files for different languages</span></span>

<span data-ttu-id="28dc2-142">Mit dem `Update-Help` -Cmdlet werden die Hilfedateien für Japanisch (ja-JP) und Englisch (en-US) für alle Module aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="28dc2-142">The `Update-Help` cmdlet updates the Japanese (ja-JP) and English (en-US) help files for all modules.</span></span>

<span data-ttu-id="28dc2-143">Wenn ein Modul keine Hilfedateien für eine angegebene UI-Kultur bereitstellt, wird eine Fehlermeldung für das Modul und die Benutzeroberflächen Kultur angezeigt.</span><span class="sxs-lookup"><span data-stu-id="28dc2-143">If a module doesn't provide help files for a specified UI culture, an error message is displayed for the module and UI culture.</span></span> <span data-ttu-id="28dc2-144">In diesem Beispiel gibt die Fehlermeldung an, dass die **ja-JP-** Hilfedateien für das Modul " **Microsoft. PowerShell. Utility** " nicht gefunden wurden.</span><span class="sxs-lookup"><span data-stu-id="28dc2-144">In this example, the error message indicates that the **ja-JP** help files were not found for module **Microsoft.PowerShell.Utility**.</span></span>

```powershell
Update-Help -UICulture ja-JP, en-US
```

```Output
Update-Help : Failed to update Help for the module(s) 'Microsoft.PowerShell.Utility' with UI culture(s) {ja-JP}
No UI culture was found that matches the following pattern: ja-JP.
```

### <span data-ttu-id="28dc2-145">Beispiel 4: Aktualisieren von Hilfedateien auf mehreren Computern aus einer Dateifreigabe</span><span class="sxs-lookup"><span data-stu-id="28dc2-145">Example 4: Update help files on multiple computers from a file share</span></span>

<span data-ttu-id="28dc2-146">In diesem Beispiel werden aktualisierte Hilfedateien aus dem Internet heruntergeladen und in einer Dateifreigabe gespeichert.</span><span class="sxs-lookup"><span data-stu-id="28dc2-146">In this example, updated help files are downloaded from the internet and saved in a file share.</span></span> <span data-ttu-id="28dc2-147">Es sind Benutzer Anmelde Informationen erforderlich, die über Berechtigungen zum Zugreifen auf die Dateifreigabe und zum Installieren von Updates verfügen.</span><span class="sxs-lookup"><span data-stu-id="28dc2-147">User credentials are needed that have permissions to access the file share and install updates.</span></span> <span data-ttu-id="28dc2-148">Wenn eine Dateifreigabe verwendet wird, ist es möglich, Computer zu aktualisieren, die sich hinter Firewalls befinden oder nicht mit dem Internet verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="28dc2-148">When a file share is used, it's possible to update computers that are behind firewalls or aren't connected to the internet.</span></span>

```powershell
Save-Help -DestinationPath \\Server01\Share\PSHelp -Credential Domain01\Admin01
Invoke-Command -ComputerName (Get-Content Servers.txt) -ScriptBlock {
     Update-Help -SourcePath \\Server01\Share\PSHelp -Credential Domain01\Admin01
}
```

<span data-ttu-id="28dc2-149">Der `Save-Help` Befehl lädt die neuesten Hilfedateien für alle Module herunter, die die aktualisierbare Hilfe unterstützen.</span><span class="sxs-lookup"><span data-stu-id="28dc2-149">The `Save-Help` command downloads the newest help files for all modules that support Updatable Help.</span></span>
<span data-ttu-id="28dc2-150">Der **DestinationPath** -Parameter speichert die Dateien in der `\\Server01\Share\PSHelp` Dateifreigabe.</span><span class="sxs-lookup"><span data-stu-id="28dc2-150">The **DestinationPath** parameter saves the files in the `\\Server01\Share\PSHelp` file share.</span></span> <span data-ttu-id="28dc2-151">Der **Credential** -Parameter gibt einen Benutzer an, der über die Berechtigung für den Zugriff auf die Dateifreigabe verfügt.</span><span class="sxs-lookup"><span data-stu-id="28dc2-151">The **Credential** parameter specifies a user who has permission to access the file share.</span></span>

<span data-ttu-id="28dc2-152">Mit dem- `Invoke-Command` Cmdlet werden Remote `Update-Help` Befehle auf mehreren Computern ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="28dc2-152">The `Invoke-Command` cmdlet runs remote `Update-Help` commands on multiple computers.</span></span> <span data-ttu-id="28dc2-153">Mit dem Parameter " **Computername** " wird eine Liste von Remote Computern aus der **Servers.txt** Datei abgerufen.</span><span class="sxs-lookup"><span data-stu-id="28dc2-153">The **ComputerName** parameter gets a list of remote computers from the **Servers.txt** file.</span></span> <span data-ttu-id="28dc2-154">Der **ScriptBlock** -Parameter führt den `Update-Help` Befehl aus und verwendet den **SourcePath** -Parameter, um die Dateifreigabe anzugeben, die die aktualisierten Hilfedateien enthält.</span><span class="sxs-lookup"><span data-stu-id="28dc2-154">The **ScriptBlock** parameter runs the `Update-Help` command and uses the **SourcePath** parameter to specify the file share that contains the updated help files.</span></span> <span data-ttu-id="28dc2-155">Der **Credential** -Parameter gibt einen Benutzer an, der auf die Dateifreigabe zugreifen und den Remote Befehl ausführen kann `Update-Help` .</span><span class="sxs-lookup"><span data-stu-id="28dc2-155">The **Credential** parameter specifies a user who can access the file share and run the remote `Update-Help` command.</span></span>

### <span data-ttu-id="28dc2-156">Beispiel 5: erhalten einer Liste mit aktualisierten Hilfedateien</span><span class="sxs-lookup"><span data-stu-id="28dc2-156">Example 5: Get a list of updated help files</span></span>

<span data-ttu-id="28dc2-157">Das- `Update-Help` Cmdlet aktualisiert die Hilfe für ein angegebenes Modul.</span><span class="sxs-lookup"><span data-stu-id="28dc2-157">The `Update-Help` cmdlet updates help for a specified module.</span></span> <span data-ttu-id="28dc2-158">Das Cmdlet verwendet den allgemeinen **verbose** -Parameter, um die Liste der aktualisierten Hilfedateien anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="28dc2-158">The cmdlet uses the **Verbose** common parameter to display the list of help files that were updated.</span></span> <span data-ttu-id="28dc2-159">Sie können " **verbose** " verwenden, um die Ausgabe für alle Hilfedateien oder Hilfedateien für ein bestimmtes Modul anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="28dc2-159">You can use **Verbose** to view output for all help files or help files for a specific module.</span></span>

<span data-ttu-id="28dc2-160">Ohne den **verbose** -Parameter werden `Update-Help` die Ergebnisse des Befehls nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="28dc2-160">Without the **Verbose** parameter, `Update-Help` doesn't display the results of the command.</span></span> <span data-ttu-id="28dc2-161">Mithilfe der ausführlichen Parameter Ausgabe können Sie überprüfen, ob die Hilfedateien aktualisiert wurden oder **ob die neueste** Version installiert ist.</span><span class="sxs-lookup"><span data-stu-id="28dc2-161">The **Verbose** parameter output is useful to verify that the help files were updated or if the latest version is installed.</span></span>

```powershell
Update-Help -Module Microsoft.PowerShell.Utility -Verbose
```

### <span data-ttu-id="28dc2-162">Beispiel 6: Suchen von Modulen, die aktualisierbare Hilfe unterstützen</span><span class="sxs-lookup"><span data-stu-id="28dc2-162">Example 6: Find modules that support Updatable Help</span></span>

<span data-ttu-id="28dc2-163">In diesem Beispiel werden Module aufgelistet, die aktualisierbare Hilfe unterstützen</span><span class="sxs-lookup"><span data-stu-id="28dc2-163">This example lists modules that support Updatable Help.</span></span> <span data-ttu-id="28dc2-164">Der Befehl verwendet die **helpinfouri** -Eigenschaft des Moduls zur Identifizierung von Modulen, die die aktualisierbare Hilfe unterstützen.</span><span class="sxs-lookup"><span data-stu-id="28dc2-164">The command uses the module's **HelpInfoUri** property to identify modules that support Updatable Help.</span></span> <span data-ttu-id="28dc2-165">Die **helpinfouri** -Eigenschaft enthält eine Adresse, die umgeleitet wird, wenn das `Update-Help` Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="28dc2-165">The **HelpInfoUri** property contains an address that is redirected when the `Update-Help` cmdlet is run.</span></span>

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

### <span data-ttu-id="28dc2-166">Beispiel 7: Inventur aktualisierte Hilfedateien</span><span class="sxs-lookup"><span data-stu-id="28dc2-166">Example 7: Inventory updated help files</span></span>

<span data-ttu-id="28dc2-167">In diesem Beispiel erstellt das Skript `Get-UpdateHelpVersion.ps1` eine Inventur der aktualisierbaren Hilfedateien für jedes Modul und ihre Versionsnummern.</span><span class="sxs-lookup"><span data-stu-id="28dc2-167">In this example, the script `Get-UpdateHelpVersion.ps1` creates an inventory of the Updatable Help files for each module and their version numbers.</span></span>

<span data-ttu-id="28dc2-168">Das Skript identifiziert Module, die die aktualisierbare Hilfe unterstützen, mithilfe der **helpinfouri** -Eigenschaft von Modulen.</span><span class="sxs-lookup"><span data-stu-id="28dc2-168">The script identifies modules that support Updatable Help by using the **HelpInfoUri** property of modules.</span></span> <span data-ttu-id="28dc2-169">Bei Modulen, die die aktualisierbare Hilfe unterstützen, sucht das Skript nach der Hilfe Informationsdatei (\* helpinfo.xml) und analysiert sie, um die aktuelle Versionsnummer zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="28dc2-169">For modules that support Updatable Help, the script looks for and parses the help information file (\*helpinfo.xml) to find the latest version number.</span></span>

<span data-ttu-id="28dc2-170">Das Skript verwendet die **pscustomobject** -Klasse und eine Hash Tabelle zum Erstellen eines benutzerdefinierten Ausgabe Objekts.</span><span class="sxs-lookup"><span data-stu-id="28dc2-170">The script uses the **PSCustomObject** class and a hash table to create a custom output object.</span></span>

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

## <span data-ttu-id="28dc2-171">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="28dc2-171">PARAMETERS</span></span>

### <span data-ttu-id="28dc2-172">-Credential</span><span class="sxs-lookup"><span data-stu-id="28dc2-172">-Credential</span></span>

<span data-ttu-id="28dc2-173">Gibt die Anmelde Informationen eines Benutzers an, der über die Berechtigung zum Zugriff auf den durch **SourcePath** angegebenen Dateisystem Speicherort verfügt.</span><span class="sxs-lookup"><span data-stu-id="28dc2-173">Specifies credentials of a user who has permission to access the file system location specified by **SourcePath**.</span></span> <span data-ttu-id="28dc2-174">Dieser Parameter ist nur gültig, wenn der **SourcePath** - oder **LiteralPath** -Parameter im Befehl verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="28dc2-174">This parameter is valid only when the **SourcePath** or **LiteralPath** parameter is used in the command.</span></span>

<span data-ttu-id="28dc2-175">Mit dem **Credential** -Parameter können Sie `Update-Help` Befehle mit dem **SourcePath** -Parameter auf Remote Computern ausführen.</span><span class="sxs-lookup"><span data-stu-id="28dc2-175">The **Credential** parameter enables you to run `Update-Help` commands with the **SourcePath** parameter on remote computers.</span></span> <span data-ttu-id="28dc2-176">Durch die Angabe expliziter Anmelde Informationen können Sie den Befehl auf einem Remote Computer ausführen und auf eine Dateifreigabe auf einem dritten Computer zugreifen, ohne dass ein Zugriffs Verweigerungs Fehler aufgetreten ist oder die Verwendung der-Authentifizierung zum Delegieren von Anmelde Informationen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="28dc2-176">By providing explicit credentials, you can run the command on a remote computer and access a file share on a third computer without encountering an access denied error or using CredSSP authentication to delegate credentials.</span></span>

<span data-ttu-id="28dc2-177">Geben Sie einen Benutzernamen ein, z. b. **USER01** oder **Domain01\User01** , oder geben Sie ein **PSCredential** -Objekt ein, das vom `Get-Credential` Cmdlet generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="28dc2-177">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="28dc2-178">Wenn Sie einen Benutzernamen eingeben, werden Sie zur Eingabe des Kennworts aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="28dc2-178">If you type a user name, you're prompted to enter the password.</span></span>

<span data-ttu-id="28dc2-179">Anmelde Informationen werden in einem [PSCredential](/dotnet/api/system.management.automation.pscredential) -Objekt gespeichert, und das Kennwort wird als [SecureString](/dotnet/api/system.security.securestring)gespeichert.</span><span class="sxs-lookup"><span data-stu-id="28dc2-179">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="28dc2-180">Weitere Informationen zum Schutz von **SecureString** -Daten finden Sie unter [wie sicher ist SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="28dc2-180">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

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

### <span data-ttu-id="28dc2-181">-Force</span><span class="sxs-lookup"><span data-stu-id="28dc2-181">-Force</span></span>

<span data-ttu-id="28dc2-182">Gibt an, dass dieses Cmdlet nicht die einmal pro Tag-Einschränkung befolgt, die Versions Überprüfung überspringt und Dateien herunterlädt, die den Grenzwert von 1 GB überschreiten.</span><span class="sxs-lookup"><span data-stu-id="28dc2-182">Indicates that this cmdlet doesn't follow the once-per-day limitation, skips version checking, and downloads files that exceed the 1 GB limit.</span></span>

<span data-ttu-id="28dc2-183">Ohne diesen Parameter wird `Update-Help` in jedem 24-Stunden-Zeitraum nur ein Mal ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="28dc2-183">Without this parameter, `Update-Help` runs only once in each 24-hour period.</span></span> <span data-ttu-id="28dc2-184">Downloads sind auf 1 GB an nicht komprimiertem Inhalt pro Modul beschränkt, und Hilfedateien werden nur installiert, wenn Sie neuer sind als die vorhandenen Dateien auf dem Computer.</span><span class="sxs-lookup"><span data-stu-id="28dc2-184">Downloads are limited to 1 GB of uncompressed content per module and help files are only installed when they're newer than the existing files on the computer.</span></span>

<span data-ttu-id="28dc2-185">Der Grenzwert von einmal täglich schützt die Server, die die Hilfedateien hosten, und ermöglicht es Ihnen, `Update-Help` Ihrem PowerShell-Profil einen Befehl hinzuzufügen, ohne dass die Ressourcenkosten für wiederholte Verbindungen oder Downloads anfallen.</span><span class="sxs-lookup"><span data-stu-id="28dc2-185">The once-per-day limit protects the servers that host the help files and makes it practical for you to add an `Update-Help` command to your PowerShell profile without incurring the resource cost of repeated connections or downloads.</span></span>

<span data-ttu-id="28dc2-186">Um die Hilfe für ein Modul in mehreren Benutzeroberflächenkulturen ohne den **Force** -Parameter zu aktualisieren, schließen Sie alle Benutzeroberflächenkulturen in denselben Befehl ein, z. B.:</span><span class="sxs-lookup"><span data-stu-id="28dc2-186">To update help for a module in multiple UI cultures without the **Force** parameter, include all UI cultures in the same command, such as:</span></span>

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

### <span data-ttu-id="28dc2-187">-Fullyqualifiedmodule</span><span class="sxs-lookup"><span data-stu-id="28dc2-187">-FullyQualifiedModule</span></span>

<span data-ttu-id="28dc2-188">Gibt Module an, deren Namen in Form von **modulespecification** -Objekten angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="28dc2-188">Specifies modules with names that are specified in the form of **ModuleSpecification** objects.</span></span>
<span data-ttu-id="28dc2-189">Diese Module werden im Abschnitt "Hinweise" des [modulespecification-Konstruktors (Hash Tabelle)](/dotnet/api/microsoft.powershell.commands.modulespecification.-ctor?view=powershellsdk-1.1.0#Microsoft_PowerShell_Commands_ModuleSpecification__ctor_System_Collections_Hashtable_)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="28dc2-189">These modules are described in the Remarks section of [ModuleSpecification Constructor (Hashtable)](/dotnet/api/microsoft.powershell.commands.modulespecification.-ctor?view=powershellsdk-1.1.0#Microsoft_PowerShell_Commands_ModuleSpecification__ctor_System_Collections_Hashtable_).</span></span>

<span data-ttu-id="28dc2-190">Der **fullyqualifiedmodule** -Parameter akzeptiert z. b. einen Modulnamen, der im folgenden Format angegeben ist:</span><span class="sxs-lookup"><span data-stu-id="28dc2-190">For example, the **FullyQualifiedModule** parameter accepts a module name that is specified in the format:</span></span>

`@{ModuleName = "modulename"; ModuleVersion = "version_number"}`

<span data-ttu-id="28dc2-191">oder</span><span class="sxs-lookup"><span data-stu-id="28dc2-191">or</span></span>

`@{ModuleName = "modulename"; ModuleVersion = "version_number"; Guid = "GUID"}.`

<span data-ttu-id="28dc2-192">**ModuleName** und **ModuleVersion** sind erforderlich, aber **Guid** ist optional.</span><span class="sxs-lookup"><span data-stu-id="28dc2-192">**ModuleName** and **ModuleVersion** are required, but **Guid** is optional.</span></span>

<span data-ttu-id="28dc2-193">Sie können den **fullyqualifiedmodule** -Parameter nicht im selben Befehl wie einen **Modul** Parameter angeben.</span><span class="sxs-lookup"><span data-stu-id="28dc2-193">You can't specify the **FullyQualifiedModule** parameter in the same command as a **Module** parameter.</span></span>

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

### <span data-ttu-id="28dc2-194">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="28dc2-194">-LiteralPath</span></span>

<span data-ttu-id="28dc2-195">Gibt den Ordner für aktualisierte Hilfedateien an, anstatt Sie aus dem Internet herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="28dc2-195">Specifies the folder for updated help files instead of downloading them from the internet.</span></span> <span data-ttu-id="28dc2-196">Verwenden Sie diesen Parameter oder **SourcePath** , wenn Sie das `Save-Help` Cmdlet zum Herunterladen von Hilfedateien in ein Verzeichnis verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="28dc2-196">Use this parameter or **SourcePath** if you've used the `Save-Help` cmdlet to download help files to a directory.</span></span>

<span data-ttu-id="28dc2-197">Sie können ein Verzeichnis Objekt, z. b. aus den- `Get-Item` oder- `Get-ChildItem` Cmdlets, an Pipeline in Pipeline `Update-Help`</span><span class="sxs-lookup"><span data-stu-id="28dc2-197">You can pipeline a directory object, such as from the `Get-Item` or `Get-ChildItem` cmdlets, to `Update-Help`.</span></span>

<span data-ttu-id="28dc2-198">Im Gegensatz zum Wert von **SourcePath** wird der Wert von **literalpath** genau so verwendet, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="28dc2-198">Unlike the value of **SourcePath** , the value of **LiteralPath** is used exactly as it's typed.</span></span> <span data-ttu-id="28dc2-199">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="28dc2-199">No characters are interpreted as wildcard characters.</span></span> <span data-ttu-id="28dc2-200">Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="28dc2-200">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="28dc2-201">Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="28dc2-201">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="28dc2-202">-Modul</span><span class="sxs-lookup"><span data-stu-id="28dc2-202">-Module</span></span>

<span data-ttu-id="28dc2-203">Aktualisiert die Hilfe für die angegebenen Module.</span><span class="sxs-lookup"><span data-stu-id="28dc2-203">Updates help for the specified modules.</span></span> <span data-ttu-id="28dc2-204">Geben Sie mindestens einen Modulnamen oder ein Namensmuster in eine durch Trennzeichen getrennte Liste ein, oder geben Sie eine Datei an, in der in jeder Zeile ein Modulname aufgeführt ist.</span><span class="sxs-lookup"><span data-stu-id="28dc2-204">Enter one or more module names or name patterns in a comma-separated list, or specify a file that lists one module name on each line.</span></span> <span data-ttu-id="28dc2-205">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="28dc2-205">Wildcard characters are permitted.</span></span> <span data-ttu-id="28dc2-206">Sie können Module aus dem `Get-Module` Cmdlet an das `Update-Help` Cmdlet weitergeben.</span><span class="sxs-lookup"><span data-stu-id="28dc2-206">You can pipeline modules from the `Get-Module` cmdlet to the `Update-Help` cmdlet.</span></span>

<span data-ttu-id="28dc2-207">Die Module, die Sie angeben, müssen auf dem Computer installiert sein, aber Sie müssen nicht in die aktuelle Sitzung importiert werden.</span><span class="sxs-lookup"><span data-stu-id="28dc2-207">The modules that you specify must be installed on the computer, but they don't have to be imported into the current session.</span></span> <span data-ttu-id="28dc2-208">Sie können ein beliebiges Modul in der Sitzung oder ein beliebiges Modul angeben, das an einem in der Umgebungsvariablen aufgeführten Speicherort installiert ist `$env:PSModulePath` .</span><span class="sxs-lookup"><span data-stu-id="28dc2-208">You can specify any module in the session or any module that is installed in a location listed in the `$env:PSModulePath` environment variable.</span></span>

<span data-ttu-id="28dc2-209">Der Wert `*` (alle) versucht, die Hilfe für alle Module zu aktualisieren, die auf dem Computer installiert sind.</span><span class="sxs-lookup"><span data-stu-id="28dc2-209">A value of `*` (all) attempts to update help for all modules that are installed on the computer.</span></span>
<span data-ttu-id="28dc2-210">Module, die keine aktualisierbare Hilfe unterstützen, sind enthalten.</span><span class="sxs-lookup"><span data-stu-id="28dc2-210">Modules that don't support Updatable Help are included.</span></span> <span data-ttu-id="28dc2-211">Dieser Wert generiert möglicherweise Fehler, wenn der Befehl Module erkennt, die die aktualisierbare Hilfe nicht unterstützen.</span><span class="sxs-lookup"><span data-stu-id="28dc2-211">This value might generate errors when the command encounters modules that don't support Updatable Help.</span></span> <span data-ttu-id="28dc2-212">Führen Sie stattdessen `Update-Help` ohne Parameter aus.</span><span class="sxs-lookup"><span data-stu-id="28dc2-212">Instead, run `Update-Help` without parameters.</span></span>

<span data-ttu-id="28dc2-213">Der **Modul** Parameter des `Update-Help` Cmdlets akzeptiert nicht den vollständigen Pfad einer Modul Datei oder Modul Manifest-Datei.</span><span class="sxs-lookup"><span data-stu-id="28dc2-213">The **Module** parameter of the `Update-Help` cmdlet doesn't accept the full path of a module file or module manifest file.</span></span> <span data-ttu-id="28dc2-214">Um die Hilfe für ein Modul zu aktualisieren, das sich nicht an einem `$env:PSModulePath` Speicherort befindet, importieren Sie das Modul in die aktuelle Sitzung, bevor Sie den `Update-Help` Befehl ausführen.</span><span class="sxs-lookup"><span data-stu-id="28dc2-214">To update help for a module that isn't in a `$env:PSModulePath` location, import the module into the current session before you run the `Update-Help` command.</span></span>

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

### <span data-ttu-id="28dc2-215">-Recurse</span><span class="sxs-lookup"><span data-stu-id="28dc2-215">-Recurse</span></span>

<span data-ttu-id="28dc2-216">Führt eine rekursive Suche nach Hilfedateien im angegebenen Verzeichnis aus.</span><span class="sxs-lookup"><span data-stu-id="28dc2-216">Performs a recursive search for help files in the specified directory.</span></span> <span data-ttu-id="28dc2-217">Dieser Parameter ist nur gültig, wenn der Befehl den **SourcePath** -Parameter verwendet.</span><span class="sxs-lookup"><span data-stu-id="28dc2-217">This parameter is valid only when the command uses the **SourcePath** parameter.</span></span>

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

### <span data-ttu-id="28dc2-218">-Bereich</span><span class="sxs-lookup"><span data-stu-id="28dc2-218">-Scope</span></span>

<span data-ttu-id="28dc2-219">Gibt den Systembereich an, in dem die Hilfe aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="28dc2-219">Specifies the system scope where help is updated.</span></span> <span data-ttu-id="28dc2-220">Updates im Bereich " **ALLUSERS** " erfordern Administratorrechte auf Windows-Systemen.</span><span class="sxs-lookup"><span data-stu-id="28dc2-220">Updates at the **AllUsers** scope require administrative privileges on Windows systems.</span></span> <span data-ttu-id="28dc2-221">Der- `-Scope` Parameter wurde in PowerShell Core Version 6,1 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="28dc2-221">The `-Scope` parameter was introduced in PowerShell Core version 6.1.</span></span>

<span data-ttu-id="28dc2-222">**CurrentUser** ist der Standardbereich für Hilfedateien in PowerShell 6,1 und höher.</span><span class="sxs-lookup"><span data-stu-id="28dc2-222">**CurrentUser** is the default scope for help files in PowerShell 6.1 and above.</span></span> <span data-ttu-id="28dc2-223">**ALLUSERS** können angegeben werden, um die Hilfe für alle Benutzer zu installieren oder zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="28dc2-223">**AllUsers** can be specified to install or update help for all users.</span></span> <span data-ttu-id="28dc2-224">Auf UNIX-Systemen `sudo` sind Berechtigungen erforderlich, um die Hilfe für alle Benutzer zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="28dc2-224">On Unix systems `sudo` privileges are required to update help for all users.</span></span> <span data-ttu-id="28dc2-225">Beispiel: `sudo pwsh -c Update-Help`</span><span class="sxs-lookup"><span data-stu-id="28dc2-225">For example: `sudo pwsh -c Update-Help`</span></span>

<span data-ttu-id="28dc2-226">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="28dc2-226">The acceptable values are:</span></span>

- <span data-ttu-id="28dc2-227">CurrentUser</span><span class="sxs-lookup"><span data-stu-id="28dc2-227">CurrentUser</span></span>
- <span data-ttu-id="28dc2-228">ALLUSERS</span><span class="sxs-lookup"><span data-stu-id="28dc2-228">AllUsers</span></span>

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

### <span data-ttu-id="28dc2-229">-SourcePath</span><span class="sxs-lookup"><span data-stu-id="28dc2-229">-SourcePath</span></span>

<span data-ttu-id="28dc2-230">Gibt einen Dateisystem Ordner `Update-Help` an, in dem aktualisierte Hilfedateien abruft, anstatt Sie aus dem Internet herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="28dc2-230">Specifies a file system folder where `Update-Help` gets updated help files, instead of downloading them from the internet.</span></span> <span data-ttu-id="28dc2-231">Geben Sie den Pfad eines Ordners ein.</span><span class="sxs-lookup"><span data-stu-id="28dc2-231">Enter the path of a folder.</span></span> <span data-ttu-id="28dc2-232">Geben Sie keinen Dateinamen oder keine Dateinamenerweiterung an.</span><span class="sxs-lookup"><span data-stu-id="28dc2-232">Don't specify a file name or file name extension.</span></span> <span data-ttu-id="28dc2-233">Sie können einen Ordner, z. b. einen aus dem- `Get-Item` `Get-ChildItem` Cmdlet oder den-Cmdlet, in Pipeline `Update-Help`</span><span class="sxs-lookup"><span data-stu-id="28dc2-233">You can pipeline a folder, such as one from the `Get-Item` or `Get-ChildItem` cmdlets, to `Update-Help`.</span></span>

<span data-ttu-id="28dc2-234">Standardmäßig werden `Update-Help` aktualisierte Hilfedateien aus dem Internet heruntergeladen.</span><span class="sxs-lookup"><span data-stu-id="28dc2-234">By default, `Update-Help` downloads updated help files from the internet.</span></span> <span data-ttu-id="28dc2-235">Verwenden Sie **SourcePath** , wenn Sie das `Save-Help` Cmdlet zum Herunterladen aktualisierter Hilfedateien in ein Verzeichnis verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="28dc2-235">Use **SourcePath** when you've used the `Save-Help` cmdlet to download updated help files to a directory.</span></span>

<span data-ttu-id="28dc2-236">Um einen Standardwert für **SourcePath** anzugeben, navigieren Sie zu **Gruppenrichtlinie** , **Computer Konfiguration** , und **legen Sie den standardmäßigen Quellpfad für Update-Help fest**.</span><span class="sxs-lookup"><span data-stu-id="28dc2-236">To specify a default value for **SourcePath** , go to **Group Policy** , **Computer Configuration** , and **Set the default source path for Update-Help**.</span></span> <span data-ttu-id="28dc2-237">Diese Gruppenrichtlinie Einstellung verhindert, dass Benutzer `Update-Help` zum Herunterladen von Hilfedateien aus dem Internet verwenden.</span><span class="sxs-lookup"><span data-stu-id="28dc2-237">This Group Policy setting prevents users from using `Update-Help` to download help files from the internet.</span></span>
<span data-ttu-id="28dc2-238">Weitere Informationen finden Sie unter [about_Group_Policy_Settings](./About/about_Group_Policy_Settings.md).</span><span class="sxs-lookup"><span data-stu-id="28dc2-238">For more information, see [about_Group_Policy_Settings](./About/about_Group_Policy_Settings.md).</span></span>

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

### <span data-ttu-id="28dc2-239">-UICulture</span><span class="sxs-lookup"><span data-stu-id="28dc2-239">-UICulture</span></span>

<span data-ttu-id="28dc2-240">Gibt UI-Kultur Werte `Update-Help` an, die von zum erhalten aktualisierter Hilfedateien verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="28dc2-240">Specifies UI culture values that `Update-Help` uses to get updated help files.</span></span> <span data-ttu-id="28dc2-241">Geben Sie einen oder mehrere Sprachcodes ein, z. b. **es-es** , eine Variable, die Kultur Objekte enthält, oder einen Befehl, der Kultur Objekte abruft, z. b. einen- `Get-Culture` oder- `Get-UICulture` Befehl.</span><span class="sxs-lookup"><span data-stu-id="28dc2-241">Enter one or more language codes, such as **es-ES** , a variable that contains culture objects, or a command that gets culture objects, such as a `Get-Culture` or `Get-UICulture` command.</span></span> <span data-ttu-id="28dc2-242">Platzhalter Zeichen sind nicht zulässig, und Sie können keinen partiellen Sprachcode, z. b. **de** , senden.</span><span class="sxs-lookup"><span data-stu-id="28dc2-242">Wildcard characters aren't permitted and you can't submit a partial language code, such as **de**.</span></span>

<span data-ttu-id="28dc2-243">Standardmäßig ruft `Update-Help` Hilfedateien in der Benutzeroberflächen Kultur ab, die für das Betriebssystem festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="28dc2-243">By default, `Update-Help` gets help files in the UI culture set for the operating system.</span></span> <span data-ttu-id="28dc2-244">Wenn Sie den **UICulture** -Parameter angeben, `Update-Help` sucht nur nach Hilfe für die angegebene Benutzeroberflächen Kultur.</span><span class="sxs-lookup"><span data-stu-id="28dc2-244">If you specify the **UICulture** parameter, `Update-Help` looks for help only for the specified UI culture.</span></span>

> [!NOTE]
> <span data-ttu-id="28dc2-245">Ubuntu 18,04 hat die Standardeinstellung für das Gebiets Schema in geändert `C.UTF.8` . Dies ist keine erkannte Benutzeroberflächen Kultur.</span><span class="sxs-lookup"><span data-stu-id="28dc2-245">Ubuntu 18.04 changed the default locale setting to `C.UTF.8`, which is not a recognized UI culture.</span></span> <span data-ttu-id="28dc2-246">`Update-Help` Wenn Sie diesen Parameter nicht mit einem unterstützten Gebiets Schema wie verwenden, wird die Hilfe im Hintergrund nicht heruntergeladen `en-US` .</span><span class="sxs-lookup"><span data-stu-id="28dc2-246">`Update-Help` silently fails to download help unless you use this parameter with a supported locale like `en-US`.</span></span> <span data-ttu-id="28dc2-247">Dies kann auf jeder Plattform vorkommen, die einen nicht unterstützten Wert verwendet.</span><span class="sxs-lookup"><span data-stu-id="28dc2-247">This could occur on any platform that uses an unsupported value.</span></span>

<span data-ttu-id="28dc2-248">Befehle, die den **UICulture** -Parameter verwenden, werden nur dann erfolgreich ausgeführt, wenn das Modul Hilfedateien für die angegebene Benutzeroberflächenkultur bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="28dc2-248">Commands that use the **UICulture** parameter succeed only when the module provides help files for the specified UI culture.</span></span> <span data-ttu-id="28dc2-249">Wenn der Befehl fehlschlägt, da die angegebene Benutzeroberflächen Kultur nicht unterstützt wird, wird eine Fehlermeldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="28dc2-249">If the command fails because the specified UI culture isn't supported, an error message is displayed.</span></span>

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

### <span data-ttu-id="28dc2-250">-Usedefault-Anmelde Informationen</span><span class="sxs-lookup"><span data-stu-id="28dc2-250">-UseDefaultCredentials</span></span>

<span data-ttu-id="28dc2-251">Gibt an, dass `Update-Help` den Befehl, einschließlich des Internet Downloads, mithilfe der Anmelde Informationen des aktuellen Benutzers ausführt.</span><span class="sxs-lookup"><span data-stu-id="28dc2-251">Indicates that `Update-Help` runs the command, including the internet download, by using the credentials of the current user.</span></span> <span data-ttu-id="28dc2-252">Standardmäßig wird der Befehl ohne explizite Anmeldeinformationen ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="28dc2-252">By default, the command runs without explicit credentials.</span></span>

<span data-ttu-id="28dc2-253">Dieser Parameter ist nur wirksam, wenn der Webdownload NT LAN Manager (NTLM), Aushandlung oder Kerberos-basierte Authentifizierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="28dc2-253">This parameter is effective only when the web download uses NT LAN Manager (NTLM), negotiate, or Kerberos-based authentication.</span></span>

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

### <span data-ttu-id="28dc2-254">-Confirm</span><span class="sxs-lookup"><span data-stu-id="28dc2-254">-Confirm</span></span>

<span data-ttu-id="28dc2-255">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="28dc2-255">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="28dc2-256">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="28dc2-256">-WhatIf</span></span>

<span data-ttu-id="28dc2-257">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="28dc2-257">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="28dc2-258">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="28dc2-258">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="28dc2-259">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="28dc2-259">CommonParameters</span></span>

<span data-ttu-id="28dc2-260">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="28dc2-260">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="28dc2-261">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="28dc2-261">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="28dc2-262">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="28dc2-262">INPUTS</span></span>

### <span data-ttu-id="28dc2-263">System. IO. directoriyinfo</span><span class="sxs-lookup"><span data-stu-id="28dc2-263">System.IO.DirectoryInfo</span></span>

<span data-ttu-id="28dc2-264">Sie können einen Verzeichnispfad an über die Pipeline übergeben `Update-Help` .</span><span class="sxs-lookup"><span data-stu-id="28dc2-264">You can pipe a directory path to `Update-Help`.</span></span>

### <span data-ttu-id="28dc2-265">System. Management. Automation. psmoduleinfo</span><span class="sxs-lookup"><span data-stu-id="28dc2-265">System.Management.Automation.PSModuleInfo</span></span>

<span data-ttu-id="28dc2-266">Sie können ein Modul Objekt über die Pipeline aus dem `Get-Module` Cmdlet an übergeben `Update-Help` .</span><span class="sxs-lookup"><span data-stu-id="28dc2-266">You can pipe a module object from the `Get-Module` cmdlet to `Update-Help`.</span></span>

## <span data-ttu-id="28dc2-267">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="28dc2-267">OUTPUTS</span></span>

### <span data-ttu-id="28dc2-268">Keine</span><span class="sxs-lookup"><span data-stu-id="28dc2-268">None</span></span>

<span data-ttu-id="28dc2-269">`Update-Help` generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="28dc2-269">`Update-Help` doesn't generate any output.</span></span>

## <span data-ttu-id="28dc2-270">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="28dc2-270">NOTES</span></span>

<span data-ttu-id="28dc2-271">Um die Hilfe für die PowerShell-Kernmodule zu aktualisieren, die die Befehle enthalten, die mit PowerShell installiert werden, oder ein beliebiges Modul im `$PSHOME\Modules` Verzeichnis, starten Sie PowerShell mit der Option **als Administrator ausführen**.</span><span class="sxs-lookup"><span data-stu-id="28dc2-271">To update help for the PowerShell Core modules, that contain the commands that are installed with PowerShell, or any module in the `$PSHOME\Modules` directory, start PowerShell with the option to **Run as administrator**.</span></span>

<span data-ttu-id="28dc2-272">Nur Mitglieder der Gruppe "Administratoren" auf dem Computer können die Hilfe für die PowerShell-Kernmodule, die Befehle, die mit PowerShell installiert werden, und für Module im `$PSHOME\Modules` Ordner aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="28dc2-272">Only members of the Administrators group on the computer can update help for the PowerShell Core modules, the commands that are installed together with PowerShell, and for modules in the `$PSHOME\Modules` folder.</span></span> <span data-ttu-id="28dc2-273">Wenn Sie keine Berechtigung zum Aktualisieren von Hilfedateien haben, können Sie die Hilfedateien Online lesen.</span><span class="sxs-lookup"><span data-stu-id="28dc2-273">If you don't have permission to update help files, you can read the help files online.</span></span> <span data-ttu-id="28dc2-274">Beispiel: `Get-Help Update-Help -Online`.</span><span class="sxs-lookup"><span data-stu-id="28dc2-274">For example, `Get-Help Update-Help -Online`.</span></span>

<span data-ttu-id="28dc2-275">Module sind die kleinste Einheit der aktualisierbaren Hilfe.</span><span class="sxs-lookup"><span data-stu-id="28dc2-275">Modules are the smallest unit of updatable help.</span></span> <span data-ttu-id="28dc2-276">Sie können die Hilfe für ein bestimmtes Cmdlet nicht aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="28dc2-276">You can't update help for a particular cmdlet.</span></span> <span data-ttu-id="28dc2-277">Um das Modul zu suchen, das ein bestimmtes Cmdlet enthält, verwenden Sie die **ModuleName** -Eigenschaft des `Get-Command` Cmdlets, z `(Get-Command Update-Help).ModuleName` . b..</span><span class="sxs-lookup"><span data-stu-id="28dc2-277">To find the module that contains a particular cmdlet, use the **ModuleName** property of the `Get-Command` cmdlet, for example, `(Get-Command Update-Help).ModuleName`.</span></span>

<span data-ttu-id="28dc2-278">Da Hilfedateien im Modul Verzeichnis installiert werden, kann das `Update-Help` Cmdlet die aktualisierte Hilfedatei nur für Module installieren, die auf dem Computer installiert sind.</span><span class="sxs-lookup"><span data-stu-id="28dc2-278">Because help files are installed in the module directory, the `Update-Help` cmdlet can install updated help file only for modules that are installed on the computer.</span></span> <span data-ttu-id="28dc2-279">Allerdings `Save-Help` kann das Cmdlet die Hilfe für Module speichern, die nicht auf dem Computer installiert sind.</span><span class="sxs-lookup"><span data-stu-id="28dc2-279">However, the `Save-Help` cmdlet can save help for modules that aren't installed on the computer.</span></span>

<span data-ttu-id="28dc2-280">Wenn `Update-Help` keine aktualisierten Hilfedateien für ein Modul finden oder die aktualisierte Hilfe nicht in der angegebenen Sprache finden kann, wird Sie ohne Anzeige einer Fehlermeldung automatisch fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="28dc2-280">If `Update-Help` can't find updated help files for a module, or can't find updated help in the specified language, it continues silently without displaying an error message.</span></span> <span data-ttu-id="28dc2-281">Verwenden Sie zum Anzeigen des Status und der Fortschrittsdetails den **Verbose** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="28dc2-281">To see status and progress details, use the **Verbose** parameter.</span></span>

<span data-ttu-id="28dc2-282">Das `Update-Help` Cmdlet wurde in Windows PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="28dc2-282">The `Update-Help` cmdlet was introduced in Windows PowerShell 3.0.</span></span> <span data-ttu-id="28dc2-283">Dies funktioniert nicht in früheren Versionen von PowerShell.</span><span class="sxs-lookup"><span data-stu-id="28dc2-283">It doesn't work in earlier versions of PowerShell.</span></span> <span data-ttu-id="28dc2-284">Verwenden Sie auf Computern mit Windows PowerShell 2,0 und Windows PowerShell 3,0 das `Update-Help` -Cmdlet in einer Windows PowerShell 3,0-Sitzung, um Hilfedateien herunterzuladen und zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="28dc2-284">On computers that have both Windows PowerShell 2.0 and Windows PowerShell 3.0, use the `Update-Help` cmdlet in a Windows PowerShell 3.0 session to download and update help files.</span></span> <span data-ttu-id="28dc2-285">Die Hilfedateien sind sowohl für Windows PowerShell 2,0 als auch für Windows PowerShell 3,0 verfügbar.</span><span class="sxs-lookup"><span data-stu-id="28dc2-285">The help files are available to both Windows PowerShell 2.0 and Windows PowerShell 3.0.</span></span>

<span data-ttu-id="28dc2-286">Die `Update-Help` -und- `Save-Help` Cmdlets verwenden die folgenden Ports, um Hilfedateien herunterzuladen: Port 80 für http und Port 443 für HTTPS.</span><span class="sxs-lookup"><span data-stu-id="28dc2-286">The `Update-Help` and `Save-Help` cmdlets use the following ports to download help files: Port 80 for HTTP and port 443 for HTTPS.</span></span>

<span data-ttu-id="28dc2-287">`Update-Help` unterstützt alle Module und die PowerShell-Kern-Snap-Ins. Es werden keine anderen Snap-Ins unterstützt.</span><span class="sxs-lookup"><span data-stu-id="28dc2-287">`Update-Help` supports all modules and the PowerShell Core snap-ins. It doesn't support any other snap-ins.</span></span>

<span data-ttu-id="28dc2-288">Um die Hilfe für ein Modul an einem Speicherort zu aktualisieren, der nicht in der `$env:PSModulePath` Umgebungsvariablen aufgeführt ist, importieren Sie das Modul in die aktuelle Sitzung, und führen Sie dann einen `Update-Help` Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="28dc2-288">To update help for a module in a location that isn't listed in the `$env:PSModulePath` environment variable, import the module into the current session and then run an `Update-Help` command.</span></span> <span data-ttu-id="28dc2-289">Führen `Update-Help` Sie ohne Parameter aus, oder verwenden Sie den **Module** -Parameter, um den Modulnamen anzugeben.</span><span class="sxs-lookup"><span data-stu-id="28dc2-289">Run `Update-Help` without parameters or use the **Module** parameter to specify the module name.</span></span> <span data-ttu-id="28dc2-290">Der **Modul** Parameter der `Update-Help` -und- `Save-Help` Cmdlets akzeptiert nicht den vollständigen Pfad einer Modul Datei oder Modul Manifest-Datei.</span><span class="sxs-lookup"><span data-stu-id="28dc2-290">The **Module** parameter of the `Update-Help` and `Save-Help` cmdlets doesn't accept the full path of a module file or module manifest file.</span></span>

<span data-ttu-id="28dc2-291">Jedes Modul kann die aktualisierbare Hilfe unterstützen.</span><span class="sxs-lookup"><span data-stu-id="28dc2-291">Any module can support Updatable Help.</span></span> <span data-ttu-id="28dc2-292">Anweisungen zur Unterstützung der aktualisierbaren Hilfe in den Modulen, die Sie erstellen, finden Sie [unter unterstützen der aktualisierbaren](/powershell/scripting/developer/module/supporting-updatable-help)</span><span class="sxs-lookup"><span data-stu-id="28dc2-292">For instructions for supporting Updatable Help in the modules that you author, see [Supporting Updatable Help](/powershell/scripting/developer/module/supporting-updatable-help).</span></span>

<span data-ttu-id="28dc2-293">Die `Update-Help` `Save-Help` Cmdlets und werden auf Windows Preinstallation Environment (Windows PE) nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="28dc2-293">The `Update-Help` and `Save-Help` cmdlets are not supported on Windows Preinstallation Environment (Windows PE).</span></span>

## <span data-ttu-id="28dc2-294">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="28dc2-294">RELATED LINKS</span></span>

[<span data-ttu-id="28dc2-295">Get-Culture</span><span class="sxs-lookup"><span data-stu-id="28dc2-295">Get-Culture</span></span>](../Microsoft.PowerShell.Utility/Get-Culture.md)

[<span data-ttu-id="28dc2-296">Get-Help</span><span class="sxs-lookup"><span data-stu-id="28dc2-296">Get-Help</span></span>](Get-Help.md)

[<span data-ttu-id="28dc2-297">Get-Module</span><span class="sxs-lookup"><span data-stu-id="28dc2-297">Get-Module</span></span>](Get-Module.md)

[<span data-ttu-id="28dc2-298">Get-UICulture</span><span class="sxs-lookup"><span data-stu-id="28dc2-298">Get-UICulture</span></span>](../Microsoft.PowerShell.Utility/Get-UICulture.md)

[<span data-ttu-id="28dc2-299">Start-Job</span><span class="sxs-lookup"><span data-stu-id="28dc2-299">Start-Job</span></span>](Start-Job.md)

[<span data-ttu-id="28dc2-300">Save-Help</span><span class="sxs-lookup"><span data-stu-id="28dc2-300">Save-Help</span></span>](Save-Help.md)
