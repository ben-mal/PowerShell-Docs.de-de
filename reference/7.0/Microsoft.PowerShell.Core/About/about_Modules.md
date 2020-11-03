---
description: Erläutert das installieren, importieren und Verwenden von PowerShell-Modulen.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 09/15/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_modules?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Modules
ms.openlocfilehash: 79fdfe018539f804933cad2354e11e45f89f724e
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93222964"
---
# <a name="about-modules"></a><span data-ttu-id="b7f3f-104">Informationen zu Modulen</span><span class="sxs-lookup"><span data-stu-id="b7f3f-104">About Modules</span></span>

## <a name="short-description"></a><span data-ttu-id="b7f3f-105">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b7f3f-105">Short Description</span></span>
<span data-ttu-id="b7f3f-106">Erläutert das installieren, importieren und Verwenden von PowerShell-Modulen.</span><span class="sxs-lookup"><span data-stu-id="b7f3f-106">Explains how to install, import, and use PowerShell modules.</span></span>

## <a name="long-description"></a><span data-ttu-id="b7f3f-107">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b7f3f-107">Long Description</span></span>

<span data-ttu-id="b7f3f-108">Ein Modul ist ein Paket, das PowerShell-Befehle wie z. b. Cmdlets, Anbieter, Funktionen, Workflows, Variablen und Aliase enthält.</span><span class="sxs-lookup"><span data-stu-id="b7f3f-108">A module is a package that contains PowerShell commands, such as cmdlets, providers, functions, workflows, variables, and aliases.</span></span>

<span data-ttu-id="b7f3f-109">Personen, die Befehle schreiben, können Module verwenden, um ihre Befehle zu organisieren und für andere Benutzer freizugeben.</span><span class="sxs-lookup"><span data-stu-id="b7f3f-109">People who write commands can use modules to organize their commands and share them with others.</span></span> <span data-ttu-id="b7f3f-110">Personen, die Module erhalten, können die Befehle in den Modulen ihren PowerShell-Sitzungen hinzufügen und wie die integrierten Befehle verwenden.</span><span class="sxs-lookup"><span data-stu-id="b7f3f-110">People who receive modules can add the commands in the modules to their PowerShell sessions and use them just like the built-in commands.</span></span>

<span data-ttu-id="b7f3f-111">In diesem Thema wird die Verwendung von PowerShell-Modulen erläutert.</span><span class="sxs-lookup"><span data-stu-id="b7f3f-111">This topic explains how to use PowerShell modules.</span></span> <span data-ttu-id="b7f3f-112">Informationen zum Schreiben von PowerShell-Modulen finden Sie unter [Schreiben eines PowerShell-Moduls](/powershell/scripting/developer/module/writing-a-windows-powershell-module).</span><span class="sxs-lookup"><span data-stu-id="b7f3f-112">For information about how to write PowerShell modules, see [Writing a PowerShell Module](/powershell/scripting/developer/module/writing-a-windows-powershell-module).</span></span>

## <a name="what-is-a-module"></a><span data-ttu-id="b7f3f-113">Was ist ein Modul?</span><span class="sxs-lookup"><span data-stu-id="b7f3f-113">What Is a Module?</span></span>

<span data-ttu-id="b7f3f-114">Ein Modul ist ein Paket mit Befehlen.</span><span class="sxs-lookup"><span data-stu-id="b7f3f-114">A module is a package of commands.</span></span> <span data-ttu-id="b7f3f-115">Alle Cmdlets und Anbieter in Ihrer Sitzung werden von einem Modul oder einem Snap-in hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="b7f3f-115">All cmdlets and providers in your session are added by a module or a snap-in.</span></span>

## <a name="module-auto-loading"></a><span data-ttu-id="b7f3f-116">Automatisches Laden von Modulen</span><span class="sxs-lookup"><span data-stu-id="b7f3f-116">Module Auto-Loading</span></span>

<span data-ttu-id="b7f3f-117">Ab PowerShell 3,0 importiert PowerShell automatisch Module, wenn Sie zum ersten Mal einen Befehl in einem installierten Modul ausführen.</span><span class="sxs-lookup"><span data-stu-id="b7f3f-117">Beginning in PowerShell 3.0, PowerShell imports modules automatically the first time that you run any command in an installed module.</span></span> <span data-ttu-id="b7f3f-118">Sie können jetzt die Befehle in einem Modul ohne weitere Einrichtung oder Profilkonfiguration verwenden, daher besteht keine Notwendigkeit, Module nach der Installation auf Ihrem Computer zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="b7f3f-118">You can now use the commands in a module without any set-up or profile configuration, so there's no need to manage modules after you install them on your computer.</span></span>

<span data-ttu-id="b7f3f-119">Die Befehle in einem Modul sind auch leichter zu finden.</span><span class="sxs-lookup"><span data-stu-id="b7f3f-119">The commands in a module are also easier to find.</span></span> <span data-ttu-id="b7f3f-120">Das `Get-Command` Cmdlet ruft nun alle Befehle in allen installierten Modulen ab, auch wenn Sie sich noch nicht in der Sitzung befinden, sodass Sie einen Befehl Suchen und ihn ohne Import verwenden können.</span><span class="sxs-lookup"><span data-stu-id="b7f3f-120">The `Get-Command` cmdlet now gets all commands in all installed modules, even if they are not yet in the session, so you can find a command and use it without importing.</span></span>

<span data-ttu-id="b7f3f-121">Jedes der folgenden Beispiele bewirkt, dass das cimcmdlets-Modul, das enthält `Get-CimInstance` , in Ihre Sitzung importiert wird.</span><span class="sxs-lookup"><span data-stu-id="b7f3f-121">Each of the following examples cause the CimCmdlets module, which contains `Get-CimInstance`, to be imported into your session.</span></span>

- <span data-ttu-id="b7f3f-122">Ausführen des Befehls</span><span class="sxs-lookup"><span data-stu-id="b7f3f-122">Run the Command</span></span>

  ```powershell
  Get-CimInstance Win32_OperatingSystem
  ```

- <span data-ttu-id="b7f3f-123">Befehl "Get"</span><span class="sxs-lookup"><span data-stu-id="b7f3f-123">Get the Command</span></span>

  ```powershell
  Get-Command Get-CimInstance
  ```

- <span data-ttu-id="b7f3f-124">Hilfe zum Befehl</span><span class="sxs-lookup"><span data-stu-id="b7f3f-124">Get Help for the Command</span></span>

  ```powershell
  Get-Help Get-CimInstance
  ```

<span data-ttu-id="b7f3f-125">`Get-Command` Befehle, die ein Platzhalter Zeichen () enthalten, werden `*` als zu erkennen, nicht zu verwenden und keine Module importiert.</span><span class="sxs-lookup"><span data-stu-id="b7f3f-125">`Get-Command` commands that include a wildcard character (`*`) are considered to be for discovery, not use, and do not import any modules.</span></span>

<span data-ttu-id="b7f3f-126">Nur Module, die an dem von der psmodulepath-Umgebungsvariablen angegebenen Speicherort gespeichert sind, werden automatisch importiert.</span><span class="sxs-lookup"><span data-stu-id="b7f3f-126">Only modules that are stored in the location specified by the PSModulePath environment variable are automatically imported.</span></span> <span data-ttu-id="b7f3f-127">Module an anderen Speicherorten müssen importiert werden, indem das `Import-Module` Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b7f3f-127">Modules in other locations must be imported by running the `Import-Module` cmdlet.</span></span>

<span data-ttu-id="b7f3f-128">Außerdem importieren Befehle, die PowerShell-Anbieter verwenden, nicht automatisch ein Modul.</span><span class="sxs-lookup"><span data-stu-id="b7f3f-128">Also, commands that use PowerShell providers do not automatically import a module.</span></span> <span data-ttu-id="b7f3f-129">Wenn Sie z. b. einen Befehl verwenden, der das WSMAN:-Laufwerk benötigt (z. b. das `Get-PSSessionConfiguration` Cmdlet), müssen Sie möglicherweise das `Import-Module` Cmdlet ausführen, um das **Microsoft. WSMAN. Management** -Modul zu importieren, das das `WSMan:` Laufwerk enthält.</span><span class="sxs-lookup"><span data-stu-id="b7f3f-129">For example, if you use a command that requires the WSMan: drive, such as the `Get-PSSessionConfiguration` cmdlet, you might need to run the `Import-Module` cmdlet to import the **Microsoft.WSMan.Management** module that includes the `WSMan:` drive.</span></span>

<span data-ttu-id="b7f3f-130">Sie können weiterhin den `Import-Module` Befehl ausführen, um ein Modul zu importieren, und die `$PSModuleAutoloadingPreference` Variable verwenden, um das automatische Importieren von Modulen zu aktivieren, zu deaktivieren und zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="b7f3f-130">You can still run the `Import-Module` command to import a module and use the `$PSModuleAutoloadingPreference` variable to enable, disable and configure automatic importing of modules.</span></span> <span data-ttu-id="b7f3f-131">Weitere Informationen finden Sie unter [about_Preference_Variables](about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="b7f3f-131">For more information, see [about_Preference_Variables](about_Preference_Variables.md).</span></span>

## <a name="how-to-use-a-module"></a><span data-ttu-id="b7f3f-132">Verwenden eines Moduls</span><span class="sxs-lookup"><span data-stu-id="b7f3f-132">How to Use a Module</span></span>

<span data-ttu-id="b7f3f-133">Um ein Modul zu verwenden, führen Sie die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="b7f3f-133">To use a module, perform the following tasks:</span></span>

1. <span data-ttu-id="b7f3f-134">Installieren Sie das Modul.</span><span class="sxs-lookup"><span data-stu-id="b7f3f-134">Install the module.</span></span> <span data-ttu-id="b7f3f-135">(Dies wird häufig für Sie durchgeführt.)</span><span class="sxs-lookup"><span data-stu-id="b7f3f-135">(This is often done for you.)</span></span>
1. <span data-ttu-id="b7f3f-136">Suchen Sie die Befehle, die das Modul hinzugefügt hat.</span><span class="sxs-lookup"><span data-stu-id="b7f3f-136">Find the commands that the module added.</span></span>
1. <span data-ttu-id="b7f3f-137">Verwenden Sie die Befehle, die das Modul hinzugefügt hat.</span><span class="sxs-lookup"><span data-stu-id="b7f3f-137">Use the commands that the module added.</span></span>

<span data-ttu-id="b7f3f-138">In diesem Thema wird erläutert, wie Sie diese Aufgaben ausführen.</span><span class="sxs-lookup"><span data-stu-id="b7f3f-138">This topic explains how to perform these tasks.</span></span> <span data-ttu-id="b7f3f-139">Darüber hinaus gibt es weitere wichtige Informationen zur Verwaltung von Modulen.</span><span class="sxs-lookup"><span data-stu-id="b7f3f-139">It also includes other useful information about managing modules.</span></span>

## <a name="how-to-install-a-module"></a><span data-ttu-id="b7f3f-140">Installieren eines Moduls</span><span class="sxs-lookup"><span data-stu-id="b7f3f-140">How to Install a Module</span></span>

<span data-ttu-id="b7f3f-141">Wenn Sie ein Modul als Ordner mit Dateien erhalten, müssen Sie es auf dem Computer installieren, bevor Sie es in PowerShell verwenden können.</span><span class="sxs-lookup"><span data-stu-id="b7f3f-141">If you receive a module as a folder with files in it, you need to install it on your computer before you can use it in PowerShell.</span></span>

<span data-ttu-id="b7f3f-142">Die meisten Module werden für Sie installiert.</span><span class="sxs-lookup"><span data-stu-id="b7f3f-142">Most modules are installed for you.</span></span> <span data-ttu-id="b7f3f-143">PowerShell verfügt über mehrere vorinstallierte Module, die manchmal auch als _Kern_ Module bezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="b7f3f-143">PowerShell comes with several preinstalled modules, sometimes called the _core_ modules.</span></span> <span data-ttu-id="b7f3f-144">Wenn auf Windows-basierten Computern Features, die im Betriebssystem enthalten sind, über Cmdlets zur Verwaltung verfügen, sind diese Module vorinstalliert.</span><span class="sxs-lookup"><span data-stu-id="b7f3f-144">On Windows-based computers, if features that are included with the operating system have cmdlets to manage them, those modules are preinstalled.</span></span> <span data-ttu-id="b7f3f-145">Wenn Sie ein Windows-Feature wie z. b. den Assistenten zum Hinzufügen von Rollen und Features in Server-Manager oder das Dialogfeld Windows-Funktionen ein-oder ausschalten in der Systemsteuerung installieren, werden alle PowerShell-Module installiert, die Teil der Funktion sind.</span><span class="sxs-lookup"><span data-stu-id="b7f3f-145">When you install a Windows feature, by using, for example, the Add Roles and Features Wizard in Server Manager, or the Turn Windows features on or off dialog box in Control Panel, any PowerShell modules that are part of the feature are installed.</span></span> <span data-ttu-id="b7f3f-146">Viele andere Module sind in einem Installationsprogramm oder Setup-Programm, mit dem das Modul installiert wird.</span><span class="sxs-lookup"><span data-stu-id="b7f3f-146">Many other modules come in an installer or Setup program that installs the module.</span></span>

<span data-ttu-id="b7f3f-147">Verwenden Sie den folgenden Befehl, um ein **Modul** Verzeichnis für den aktuellen Benutzer zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="b7f3f-147">Use the following command to create a **Modules** directory for the current user:</span></span>

```powershell
New-Item -Type Directory -Path $HOME\Documents\PowerShell\Modules
```

<span data-ttu-id="b7f3f-148">Kopieren Sie den gesamten Modulordner in das Verzeichnis „Modules“.</span><span class="sxs-lookup"><span data-stu-id="b7f3f-148">Copy the entire module folder into the Modules directory.</span></span> <span data-ttu-id="b7f3f-149">Sie können eine beliebige Methode verwenden, um den Ordner zu kopieren, einschließlich Windows Explorer und Cmd.exe sowie PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b7f3f-149">You can use any method to copy the folder, including Windows Explorer and Cmd.exe, as well as PowerShell.</span></span> <span data-ttu-id="b7f3f-150">Verwenden Sie das `Copy-Item` Cmdlet in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b7f3f-150">In PowerShell use the `Copy-Item` cmdlet.</span></span> <span data-ttu-id="b7f3f-151">Um beispielsweise den Ordner "MyModule" aus `C:\ps-test\MyModule` in das Verzeichnis "modules" zu kopieren, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="b7f3f-151">For example, to copy the MyModule folder from `C:\ps-test\MyModule` to the Modules directory, type:</span></span>

```powershell
Copy-Item -Path C:\ps-test\MyModule -Destination `
    $HOME\Documents\PowerShell\Modules
```

<span data-ttu-id="b7f3f-152">Sie können ein Modul an einem beliebigen Speicherort installieren, aber wenn Sie Ihre Module an einem Standardspeicherort installieren, sind sie leichter zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="b7f3f-152">You can install a module in any location, but installing your modules in a default module location makes them easier to manage.</span></span> <span data-ttu-id="b7f3f-153">Weitere Informationen zu den standardmäßigen Modul Speicherorten finden Sie im Abschnitt " [Module und DSC-Ressourcen Speicherorte" und "psmodulepath](#module-and-dsc-resource-locations-and-psmodulepath) ".</span><span class="sxs-lookup"><span data-stu-id="b7f3f-153">For more information about the default module locations, see the [Module and DSC Resource Locations, and PSModulePath](#module-and-dsc-resource-locations-and-psmodulepath) section.</span></span>

## <a name="how-to-find-installed-modules"></a><span data-ttu-id="b7f3f-154">So finden Sie installierte Module</span><span class="sxs-lookup"><span data-stu-id="b7f3f-154">How to Find Installed Modules</span></span>

<span data-ttu-id="b7f3f-155">Geben Sie Folgendes ein, um Module zu suchen, die an einem Modul-Standardspeicherort installiert sind, jedoch noch nicht in die Sitzung importiert wurden:</span><span class="sxs-lookup"><span data-stu-id="b7f3f-155">To find modules that are installed in a default module location, but not yet imported into your session, type:</span></span>

```powershell
Get-Module -ListAvailable
```

<span data-ttu-id="b7f3f-156">Geben Sie an der PowerShell-Eingabeaufforderung Folgendes ein, um die Module zu suchen, die bereits in die Sitzung importiert wurden:</span><span class="sxs-lookup"><span data-stu-id="b7f3f-156">To find the modules that have already been imported into your session, at the PowerShell prompt, type:</span></span>

```powershell
Get-Module
```

<span data-ttu-id="b7f3f-157">Weitere Informationen zum `Get-Module` Cmdlet finden [Sie unter Get-Module](xref:Microsoft.PowerShell.Core.Get-Module).</span><span class="sxs-lookup"><span data-stu-id="b7f3f-157">For more information about the `Get-Module` cmdlet, see [Get-Module](xref:Microsoft.PowerShell.Core.Get-Module).</span></span>

## <a name="how-to-find-the-commands-in-a-module"></a><span data-ttu-id="b7f3f-158">Suchen der Befehle in einem Modul</span><span class="sxs-lookup"><span data-stu-id="b7f3f-158">How to Find the Commands in a Module</span></span>

<span data-ttu-id="b7f3f-159">Verwenden `Get-Command` Sie das Cmdlet, um alle verfügbaren Befehle zu suchen.</span><span class="sxs-lookup"><span data-stu-id="b7f3f-159">Use the `Get-Command` cmdlet to find all available commands.</span></span> <span data-ttu-id="b7f3f-160">Sie können die Parameter des `Get-Command` Cmdlets verwenden, um Befehle wie z. b. nach Modul, Namen und Nomen zu filtern.</span><span class="sxs-lookup"><span data-stu-id="b7f3f-160">You can use the parameters of the `Get-Command` cmdlet to filter commands such as by module, name, and noun.</span></span>

<span data-ttu-id="b7f3f-161">Um alle Befehle in einem Modul zu suchen, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="b7f3f-161">To find all commands in a module, type:</span></span>

```powershell
Get-Command -Module <module-name>
```

<span data-ttu-id="b7f3f-162">Wenn Sie z. b. die Befehle im bitstransfer-Modul suchen möchten, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="b7f3f-162">For example, to find the commands in the BitsTransfer module, type:</span></span>

```powershell
Get-Command -Module BitsTransfer
```

<span data-ttu-id="b7f3f-163">Weitere Informationen zum `Get-Command` Cmdlet finden [Sie unter Get-Command](xref:Microsoft.PowerShell.Core.Get-Command).</span><span class="sxs-lookup"><span data-stu-id="b7f3f-163">For more information about the `Get-Command` cmdlet, see [Get-Command](xref:Microsoft.PowerShell.Core.Get-Command).</span></span>

## <a name="how-to-get-help-for-the-commands-in-a-module"></a><span data-ttu-id="b7f3f-164">So erhalten Sie Hilfe für die Befehle in einem Modul</span><span class="sxs-lookup"><span data-stu-id="b7f3f-164">How to Get Help for the Commands in a Module</span></span>

<span data-ttu-id="b7f3f-165">Wenn das Modul Hilfedateien für die Befehle enthält, die es exportiert, `Get-Help` zeigt das Cmdlet die Hilfe Themen an.</span><span class="sxs-lookup"><span data-stu-id="b7f3f-165">If the module contains Help files for the commands that it exports, the `Get-Help` cmdlet will display the Help topics.</span></span> <span data-ttu-id="b7f3f-166">Verwenden Sie das gleiche `Get-Help` Befehls Format, das Sie verwenden, um Hilfe zu einem beliebigen Befehl in PowerShell zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="b7f3f-166">Use the same `Get-Help` command format that you would use to get help for any command in PowerShell.</span></span>

<span data-ttu-id="b7f3f-167">Ab PowerShell 3,0 können Sie Hilfedateien für ein Modul herunterladen und Updates in die Hilfedateien herunterladen, damit Sie nie veraltet sind.</span><span class="sxs-lookup"><span data-stu-id="b7f3f-167">Beginning in PowerShell 3.0, you can download Help files for a module and download updates to the Help files so they are never obsolete.</span></span>

<span data-ttu-id="b7f3f-168">Um Hilfe für Befehle in einem Modul zu erhalten, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="b7f3f-168">To get help for a commands in a module, type:</span></span>

```powershell
Get-Help <command-name>
```

<span data-ttu-id="b7f3f-169">Um die Hilfe für den Befehl in einem Modul online zu erhalten, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="b7f3f-169">To get help online for command in a module, type:</span></span>

```powershell
Get-Help <command-name> -Online
```

<span data-ttu-id="b7f3f-170">Geben Sie Folgendes ein, um die Hilfedateien für die Befehle in einem Modul herunterzuladen und zu installieren:</span><span class="sxs-lookup"><span data-stu-id="b7f3f-170">To download and install the help files for the commands in a module, type:</span></span>

```powershell
Update-Help -Module <module-name>
```

<span data-ttu-id="b7f3f-171">Weitere Informationen finden Sie unter " [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) " und " [Update-Help](xref:Microsoft.PowerShell.Core.Update-Help)".</span><span class="sxs-lookup"><span data-stu-id="b7f3f-171">For more information, see [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) and [Update-Help](xref:Microsoft.PowerShell.Core.Update-Help).</span></span>

## <a name="how-to-import-a-module"></a><span data-ttu-id="b7f3f-172">Importieren eines Moduls</span><span class="sxs-lookup"><span data-stu-id="b7f3f-172">How to Import a Module</span></span>

<span data-ttu-id="b7f3f-173">Sie müssen möglicherweise ein Modul oder eine Moduldatei importieren.</span><span class="sxs-lookup"><span data-stu-id="b7f3f-173">You might have to import a module or import a module file.</span></span> <span data-ttu-id="b7f3f-174">Der Import ist erforderlich, wenn ein Modul nicht an den von der **psmodulepath** -Umgebungsvariablen angegebenen Speicherorten installiert ist, `$env:PSModulePath` oder wenn das Modul aus einer Datei besteht (z. b. eine DLL-oder. psm1-Datei), anstelle eines typischen Moduls, das als Ordner übermittelt wird.</span><span class="sxs-lookup"><span data-stu-id="b7f3f-174">Importing is required when a module is not installed in the locations specified by the **PSModulePath** environment variable, `$env:PSModulePath`, or the module consists of file, such as a .dll or .psm1 file, instead of typical module that is delivered as a folder.</span></span>

<span data-ttu-id="b7f3f-175">Sie können auch ein Modul importieren, sodass Sie die Parameter des Befehls verwenden können, z. b. `Import-Module` den prefix-Parameter, der den Substantiv Namen aller importierten Befehle ein eindeutiges Präfix hinzufügt, oder den **noClobber** -Parameter, der verhindert, dass das Modul Befehle hinzufügt, die vorhandene Befehle in der Sitzung ausblenden oder ersetzen würden.</span><span class="sxs-lookup"><span data-stu-id="b7f3f-175">You might also choose to import a module so that you can use the parameters of the `Import-Module` command, such as the Prefix parameter, which adds a distinctive prefix to the noun names of all imported commands, or the **NoClobber** parameter, which prevents the module from adding commands that would hide or replace existing commands in the session.</span></span>

<span data-ttu-id="b7f3f-176">Verwenden Sie das-Cmdlet, um Module zu importieren `Import-Module` .</span><span class="sxs-lookup"><span data-stu-id="b7f3f-176">To import modules, use the `Import-Module` cmdlet.</span></span>

<span data-ttu-id="b7f3f-177">Verwenden Sie das folgende Befehlsformat, um Module an einen PSModulePath-Speicherort in der aktuellen Sitzung zu importieren.</span><span class="sxs-lookup"><span data-stu-id="b7f3f-177">To import modules in a PSModulePath location into the current session, use the following command format.</span></span>

```powershell
Import-Module <module-name>
```

<span data-ttu-id="b7f3f-178">Mit dem folgenden Befehl importieren Sie beispielsweise das Modul "BitsTransfer" in die aktuelle Sitzung.</span><span class="sxs-lookup"><span data-stu-id="b7f3f-178">For example, the following command imports the BitsTransfer module into the current session.</span></span>

```powershell
Import-Module BitsTransfer
```

<span data-ttu-id="b7f3f-179">Verwenden Sie zum Importieren eines Moduls, das sich nicht am Standard-Modulspeicherort befindet, den vollqualifizierten Pfad zum Modulordner im Befehl.</span><span class="sxs-lookup"><span data-stu-id="b7f3f-179">To import a module that is not in a default module location, use the fully qualified path to the module folder in the command.</span></span>

<span data-ttu-id="b7f3f-180">Wenn Sie z. b. das Modul testcmdlets im Verzeichnis der Sitzung hinzufügen möchten, geben Sie Folgendes ein `C:\ps-test` :</span><span class="sxs-lookup"><span data-stu-id="b7f3f-180">For example, to add the TestCmdlets module in the `C:\ps-test` directory to your session, type:</span></span>

```powershell
Import-Module C:\ps-test\TestCmdlets
```

<span data-ttu-id="b7f3f-181">Um eine Moduldatei zu importieren, die nicht in einem Modulordner enthalten ist, verwenden Sie den vollqualifizierten Pfad der Moduldatei im Befehl.</span><span class="sxs-lookup"><span data-stu-id="b7f3f-181">To import a module file that is not contained in a module folder, use the fully qualified path to the module file in the command.</span></span>

<span data-ttu-id="b7f3f-182">Wenn Sie z. b. der Sitzung das TestCmdlets.dll Modul im Verzeichnis hinzufügen möchten, geben Sie Folgendes ein `C:\ps-test` :</span><span class="sxs-lookup"><span data-stu-id="b7f3f-182">For example, to add the TestCmdlets.dll module in the `C:\ps-test` directory to your session, type:</span></span>

```powershell
Import-Module C:\ps-test\TestCmdlets.dll
```

<span data-ttu-id="b7f3f-183">Weitere Informationen zum Hinzufügen von Modulen zu Ihrer Sitzung finden Sie unter [Import-Module](xref:Microsoft.PowerShell.Core.Import-Module).</span><span class="sxs-lookup"><span data-stu-id="b7f3f-183">For more information about adding modules to your session, see [Import-Module](xref:Microsoft.PowerShell.Core.Import-Module).</span></span>

## <a name="how-to-import-a-module-into-every-session"></a><span data-ttu-id="b7f3f-184">Importieren eines Moduls in jede Sitzung</span><span class="sxs-lookup"><span data-stu-id="b7f3f-184">How to Import a Module into Every Session</span></span>

<span data-ttu-id="b7f3f-185">Der `Import-Module` Befehl importiert Module in Ihre aktuelle PowerShell-Sitzung.</span><span class="sxs-lookup"><span data-stu-id="b7f3f-185">The `Import-Module` command imports modules into your current PowerShell session.</span></span> <span data-ttu-id="b7f3f-186">Wenn Sie ein Modul in jede PowerShell-Sitzung importieren möchten, die Sie starten, fügen Sie den `Import-Module` Befehl zu Ihrem PowerShell-Profil hinzu.</span><span class="sxs-lookup"><span data-stu-id="b7f3f-186">To import a module into every PowerShell session that you start, add the `Import-Module` command to your PowerShell profile.</span></span>

<span data-ttu-id="b7f3f-187">Weitere Informationen zu Profilen finden Sie unter [about_Profiles](about_Profiles.md).</span><span class="sxs-lookup"><span data-stu-id="b7f3f-187">For more information about profiles, see [about_Profiles](about_Profiles.md).</span></span>

## <a name="how-to-remove-a-module"></a><span data-ttu-id="b7f3f-188">Entfernen eines Moduls</span><span class="sxs-lookup"><span data-stu-id="b7f3f-188">How to Remove a Module</span></span>

<span data-ttu-id="b7f3f-189">Wenn Sie ein Modul entfernen, werden die vom Modul hinzugefügten Befehle aus der Sitzung gelöscht.</span><span class="sxs-lookup"><span data-stu-id="b7f3f-189">When you remove a module, the commands that the module added are deleted from the session.</span></span>

<span data-ttu-id="b7f3f-190">Verwenden Sie das folgende Befehls Format, um ein Modul aus der Sitzung zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="b7f3f-190">To remove a module from your session, use the following command format.</span></span>

```powershell
Remove-Module <module-name>
```

<span data-ttu-id="b7f3f-191">Mit dem folgenden Befehl wird beispielsweise das Modul "bitstransfer" aus der aktuellen Sitzung entfernt.</span><span class="sxs-lookup"><span data-stu-id="b7f3f-191">For example, the following command removes the BitsTransfer module from the current session.</span></span>

```powershell
Remove-Module BitsTransfer
```

<span data-ttu-id="b7f3f-192">Entfernen einrd Moduld kehrt den Vorgang des Modulimports um.</span><span class="sxs-lookup"><span data-stu-id="b7f3f-192">Removing a module reverses the operation of importing a module.</span></span> <span data-ttu-id="b7f3f-193">Beim Entfernen eines Moduls wird das Modul nicht deinstalliert.</span><span class="sxs-lookup"><span data-stu-id="b7f3f-193">Removing a module does not uninstall the module.</span></span> <span data-ttu-id="b7f3f-194">Weitere Informationen finden Sie unter [Remove-Module](xref:Microsoft.PowerShell.Core.Remove-Module).</span><span class="sxs-lookup"><span data-stu-id="b7f3f-194">For more information, see [Remove-Module](xref:Microsoft.PowerShell.Core.Remove-Module).</span></span>

## <a name="module-and-dsc-resource-locations-and-psmodulepath"></a><span data-ttu-id="b7f3f-195">Modul-und DSC-Ressourcen Speicherorte und psmodulepath</span><span class="sxs-lookup"><span data-stu-id="b7f3f-195">Module and DSC Resource Locations, and PSModulePath</span></span>

<span data-ttu-id="b7f3f-196">Die `$env:PSModulePath` Umgebungsvariable enthält eine Liste der Ordner Speicherorte, die durchsucht werden, um Module und Ressourcen zu finden.</span><span class="sxs-lookup"><span data-stu-id="b7f3f-196">The `$env:PSModulePath` environment variable contains a list of folder locations that are searched to find modules and resources.</span></span>

<span data-ttu-id="b7f3f-197">Standardmäßig sind die folgenden effektiven Speicherorte zugewiesen `$env:PSModulePath` :</span><span class="sxs-lookup"><span data-stu-id="b7f3f-197">By default, the effective locations assigned to `$env:PSModulePath` are:</span></span>

- <span data-ttu-id="b7f3f-198">System weite Standorte: `$PSHOME\Modules`</span><span class="sxs-lookup"><span data-stu-id="b7f3f-198">System-wide locations: `$PSHOME\Modules`</span></span>

  <span data-ttu-id="b7f3f-199">Diese Ordner enthalten Module, die mit Windows und PowerShell ausgeliefert werden.</span><span class="sxs-lookup"><span data-stu-id="b7f3f-199">These folders contain modules that ship with Windows and PowerShell.</span></span>

  <span data-ttu-id="b7f3f-200">DSC-Ressourcen, die in PowerShell enthalten sind, werden im `$PSHOME\Modules\PSDesiredStateConfiguration\DSCResources` Ordner gespeichert.</span><span class="sxs-lookup"><span data-stu-id="b7f3f-200">DSC resources that are included with PowerShell are stored in the `$PSHOME\Modules\PSDesiredStateConfiguration\DSCResources` folder.</span></span>

- <span data-ttu-id="b7f3f-201">Benutzerspezifische Module: Hierbei handelt es sich um Module, die vom Benutzer im Gültigkeitsbereich des Benutzers installiert werden.</span><span class="sxs-lookup"><span data-stu-id="b7f3f-201">User-specific modules: These are modules installed by the user in the user's scope.</span></span> <span data-ttu-id="b7f3f-202">`Install-Module` verfügt über einen **Scope** -Parameter, mit dem Sie angeben können, ob das Modul für den aktuellen Benutzer oder für alle Benutzer installiert ist.</span><span class="sxs-lookup"><span data-stu-id="b7f3f-202">`Install-Module` has a **Scope** parameter that allows you to specify whether the module is installed for the current user or for all users.</span></span> <span data-ttu-id="b7f3f-203">Weitere Informationen finden Sie unter [Install-Module](xref:PowerShellGet.Install-Module).</span><span class="sxs-lookup"><span data-stu-id="b7f3f-203">For more information, see [Install-Module](xref:PowerShellGet.Install-Module).</span></span>

  <span data-ttu-id="b7f3f-204">Der benutzerspezifische **CurrentUser** -Speicherort unter Windows ist der `PowerShell\Modules` Ordner im Speicherort der **Dokumente** in Ihrem Benutzerprofil.</span><span class="sxs-lookup"><span data-stu-id="b7f3f-204">The user-specific **CurrentUser** location on Windows is the `PowerShell\Modules` folder located in the **Documents** location in your user profile.</span></span> <span data-ttu-id="b7f3f-205">Der spezifische Pfad dieses Standorts variiert je nach Version von Windows und ob Sie die Ordner Umleitung verwenden.</span><span class="sxs-lookup"><span data-stu-id="b7f3f-205">The specific path of that location varies by version of Windows and whether or not you are using folder redirection.</span></span> <span data-ttu-id="b7f3f-206">Microsoft onedrive kann auch den Speicherort des Ordners " **Dokumente** " ändern.</span><span class="sxs-lookup"><span data-stu-id="b7f3f-206">Microsoft OneDrive can also change the location of your **Documents** folder.</span></span>

  <span data-ttu-id="b7f3f-207">Standardmäßig ist dieser Speicherort unter Windows 10 `$HOME\Documents\PowerShell\Modules` .</span><span class="sxs-lookup"><span data-stu-id="b7f3f-207">By default, on Windows 10, that location is `$HOME\Documents\PowerShell\Modules`.</span></span> <span data-ttu-id="b7f3f-208">Unter Linux oder Mac lautet der **CurrentUser** -Speicherort `$HOME/.local/share/powershell/Modules` .</span><span class="sxs-lookup"><span data-stu-id="b7f3f-208">On Linux or Mac, the **CurrentUser** location is `$HOME/.local/share/powershell/Modules`.</span></span>

  > [!NOTE]
  > <span data-ttu-id="b7f3f-209">Sie können den Speicherort des Ordners " **Dokumente** " mithilfe des folgenden Befehls überprüfen: `[Environment]::GetFolderPath('MyDocuments')` .</span><span class="sxs-lookup"><span data-stu-id="b7f3f-209">You can verify the location of your **Documents** folder using the following command: `[Environment]::GetFolderPath('MyDocuments')`.</span></span>

- <span data-ttu-id="b7f3f-210">Der **ALLUSERS** -Speicherort ist `$env:PROGRAMFILES\PowerShell\Modules` unter Windows.</span><span class="sxs-lookup"><span data-stu-id="b7f3f-210">The **AllUsers** location is `$env:PROGRAMFILES\PowerShell\Modules` on Windows.</span></span> <span data-ttu-id="b7f3f-211">Unter Linux oder Mac werden die Module unter gespeichert `/usr/local/share/powershell/Modules` .</span><span class="sxs-lookup"><span data-stu-id="b7f3f-211">On Linux or Mac the modules are stored at `/usr/local/share/powershell/Modules`.</span></span>

> [!NOTE]
> <span data-ttu-id="b7f3f-212">Um Dateien im Verzeichnis hinzuzufügen oder zu ändern `$env:Windir\System32` , starten Sie PowerShell mit der Option **als Administrator ausführen** .</span><span class="sxs-lookup"><span data-stu-id="b7f3f-212">To add or change files in the `$env:Windir\System32` directory, start PowerShell with the **Run as administrator** option.</span></span>

<span data-ttu-id="b7f3f-213">Sie können die standardmäßigen Modul Speicherorte auf dem System ändern, indem Sie den Wert der **psmodulepath** -Umgebungsvariablen ändern `$Env:PSModulePath` .</span><span class="sxs-lookup"><span data-stu-id="b7f3f-213">You can change the default module locations on your system by changing the value of the **PSModulePath** environment variable, `$Env:PSModulePath`.</span></span> <span data-ttu-id="b7f3f-214">Die Umgebungsvariable **psmodulepath** wird anhand der PATH-Umgebungsvariablen modelliert und weist das gleiche Format auf.</span><span class="sxs-lookup"><span data-stu-id="b7f3f-214">The **PSModulePath** environment variable is modeled on the Path environment variable and has the same format.</span></span>

<span data-ttu-id="b7f3f-215">Um die Standardspeicherorte für das Modul anzuzeigen, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="b7f3f-215">To view the default module locations, type:</span></span>

```powershell
$Env:PSModulePath
```

<span data-ttu-id="b7f3f-216">Um einen Standardspeicherort für das Modul hinzuzufügen, verwenden Sie das folgende Befehlsformat.</span><span class="sxs-lookup"><span data-stu-id="b7f3f-216">To add a default module location, use the following command format.</span></span>

```powershell
$Env:PSModulePath = $Env:PSModulePath + ";<path>"
```

<span data-ttu-id="b7f3f-217">Das Semikolon ( `;` ) im Befehl trennt den neuen Pfad von dem Pfad, der in der Liste vorangestellt ist.</span><span class="sxs-lookup"><span data-stu-id="b7f3f-217">The semi-colon (`;`) in the command separates the new path from the path that precedes it in the list.</span></span>

<span data-ttu-id="b7f3f-218">Geben Sie z. b. Folgendes ein, um das Verzeichnis hinzuzufügen `C:\ps-test\Modules` :</span><span class="sxs-lookup"><span data-stu-id="b7f3f-218">For example, to add the `C:\ps-test\Modules` directory, type:</span></span>

```powershell
$Env:PSModulePath + ";C:\ps-test\Modules"
```

<span data-ttu-id="b7f3f-219">Verwenden Sie das folgende Befehls Format, um einen standardmäßigen Modul Speicherort unter Linux oder MacOS hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="b7f3f-219">To add a default module location on Linux or MacOS, use the following command format:</span></span>

```powershell
$Env:PSModulePath += ":<path>"
```

<span data-ttu-id="b7f3f-220">Wenn Sie z. b. das `/usr/local/Fabrikam/Modules` Verzeichnis dem Wert der **psmodulepath** -Umgebungsvariablen hinzufügen möchten, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="b7f3f-220">For example, to add the `/usr/local/Fabrikam/Modules` directory to the value of the **PSModulePath** environment variable, type:</span></span>

```powershell
$Env:PSModulePath += ":/usr/local/Fabrikam/Modules"
```

<span data-ttu-id="b7f3f-221">Unter Linux oder MacOS trennt der Doppelpunkt ( `:` ) im Befehl den neuen Pfad von dem Pfad, der in der Liste vorangestellt ist.</span><span class="sxs-lookup"><span data-stu-id="b7f3f-221">On Linux or MacOS, the colon (`:`) in the command separates the new path from the path that precedes it in the list.</span></span>

<span data-ttu-id="b7f3f-222">Wenn Sie einen Pfad zu **psmodulepath** hinzufügen, `Get-Module` enthalten-und- `Import-Module` Befehle Module in diesem Pfad.</span><span class="sxs-lookup"><span data-stu-id="b7f3f-222">When you add a path to **PSModulePath** , `Get-Module` and `Import-Module` commands include modules in that path.</span></span>

<span data-ttu-id="b7f3f-223">Der festgelegte Wert wirkt sich nur auf die aktuelle Sitzung aus.</span><span class="sxs-lookup"><span data-stu-id="b7f3f-223">The value that you set affects only the current session.</span></span> <span data-ttu-id="b7f3f-224">Um die Änderung dauerhaft zu machen, fügen Sie den Befehl zu Ihrem PowerShell-Profil hinzu, oder verwenden Sie System in der Systemsteuerung, um den Wert der Umgebungsvariablen **psmodulepath** in der Registrierung zu ändern.</span><span class="sxs-lookup"><span data-stu-id="b7f3f-224">To make the change persistent, add the command to your PowerShell profile or use System in Control Panel to change the value of the **PSModulePath** environment variable in the registry.</span></span>

<span data-ttu-id="b7f3f-225">Um die Änderung dauerhaft zu machen, können Sie auch die Methode " **stenvironmentvariable** " der **System. Environment** -Klasse verwenden, um einen Pfad zur **psmodulepath** -Umgebungsvariablen hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="b7f3f-225">Also, to make the change persistent, you can also use the **SetEnvironmentVariable** method of the **System.Environment** class to add a Path to the **PSModulePath** environment variable.</span></span>

<span data-ttu-id="b7f3f-226">Weitere Informationen zur **psmodulepath** -Variablen finden Sie unter [about_Environment_Variables](about_Environment_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="b7f3f-226">For more information about the **PSModulePath** variable, see [about_Environment_Variables](about_Environment_Variables.md).</span></span>

## <a name="modules-and-name-conflicts"></a><span data-ttu-id="b7f3f-227">Module und Namenskonflikte</span><span class="sxs-lookup"><span data-stu-id="b7f3f-227">Modules and Name Conflicts</span></span>

<span data-ttu-id="b7f3f-228">Namenskonflikte treten auf, wenn mehrere Befehle in der Sitzung denselben Namen haben.</span><span class="sxs-lookup"><span data-stu-id="b7f3f-228">Name conflicts occur when more than one command in the session has the same name.</span></span> <span data-ttu-id="b7f3f-229">Das Importieren eines Moduls bewirkt einen Namenskonflikt, wenn Befehle im Modul die gleichen Namen wie die Befehle oder Elemente in der Sitzung haben.</span><span class="sxs-lookup"><span data-stu-id="b7f3f-229">Importing a module causes a name conflict when commands in the module have the same names as commands or items in the session.</span></span>

<span data-ttu-id="b7f3f-230">Namenskonflikte können dazu führen, dass Befehle ausgeblendet oder ersetzt werden.</span><span class="sxs-lookup"><span data-stu-id="b7f3f-230">Name conflicts can result in commands being hidden or replaced.</span></span>

### <a name="hidden"></a><span data-ttu-id="b7f3f-231">Ausgeblendet</span><span class="sxs-lookup"><span data-stu-id="b7f3f-231">Hidden</span></span>

<span data-ttu-id="b7f3f-232">Ein Befehl ist ausgeblendet, wenn er nicht ausgeführt wird, wenn Sie den Befehl eingeben, Sie ihn jedoch mithilfe einer anderen Methode ausführen können, wie z. B. den Befehlsnamen mit dem Namen des Moduls oder Snap-Ins zu qualifizieren, aus dem sie stammen.</span><span class="sxs-lookup"><span data-stu-id="b7f3f-232">A command is hidden when it is not the command that runs when you type the command name, but you can run it by using another method, such as by qualifying the command name with the name of the module or snap-in in which it originated.</span></span>

### <a name="replaced"></a><span data-ttu-id="b7f3f-233">Ersetzt</span><span class="sxs-lookup"><span data-stu-id="b7f3f-233">Replaced</span></span>

<span data-ttu-id="b7f3f-234">Ein Befehl wurde ersetzt, wenn Sie ihn nicht ausführen können, weil er durch einen Befehl mit demselben Namen überschrieben wurde.</span><span class="sxs-lookup"><span data-stu-id="b7f3f-234">A command is replaced when you cannot run it because it has been overwritten by a command with the same name.</span></span> <span data-ttu-id="b7f3f-235">Selbst wenn Sie das Modul entfernen, das den Konflikt verursacht hat, kann ein ersetzter Befehl nicht ausgeführt werden, sofern Sie die Sitzung nicht neu starten.</span><span class="sxs-lookup"><span data-stu-id="b7f3f-235">Even when you remove the module that caused the conflict, you cannot run a replaced command unless you restart the session.</span></span>

<span data-ttu-id="b7f3f-236">`Import-Module` kann Befehle hinzufügen, die Befehle in der aktuellen Sitzung ausblenden und ersetzen.</span><span class="sxs-lookup"><span data-stu-id="b7f3f-236">`Import-Module` might add commands that hide and replace commands in the current session.</span></span> <span data-ttu-id="b7f3f-237">Darüber hinaus können Befehle in der Sitzung Befehle ausblenden, die das Modul hinzugefügt hat.</span><span class="sxs-lookup"><span data-stu-id="b7f3f-237">Also, commands in your session can hide commands that the module added.</span></span>

<span data-ttu-id="b7f3f-238">Verwenden Sie den **all** -Parameter des Cmdlets, um Namenskonflikte zu erkennen `Get-Command` .</span><span class="sxs-lookup"><span data-stu-id="b7f3f-238">To detect name conflicts, use the **All** parameter of the `Get-Command` cmdlet.</span></span> <span data-ttu-id="b7f3f-239">Ab PowerShell 3,0 ruft nur die Befehle ab, die ausgeführt werden, `Get-Command` Wenn Sie den Befehlsnamen eingeben.</span><span class="sxs-lookup"><span data-stu-id="b7f3f-239">Beginning in PowerShell 3.0, `Get-Command` gets only that commands that run when you type the command name.</span></span> <span data-ttu-id="b7f3f-240">Der **all** -Parameter ruft alle Befehle mit dem angegebenen Namen in der Sitzung ab.</span><span class="sxs-lookup"><span data-stu-id="b7f3f-240">The **All** parameter gets all commands with the specific name in the session.</span></span>

<span data-ttu-id="b7f3f-241">Um Namenskonflikte zu vermeiden, verwenden Sie die **noClobber** -oder **prefix** -Parameter des `Import-Module` Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="b7f3f-241">To prevent name conflicts, use the **NoClobber** or **Prefix** parameters of the `Import-Module` cmdlet.</span></span> <span data-ttu-id="b7f3f-242">Der **prefix** -Parameter fügt den Namen importierter Befehle ein Präfix hinzu, damit Sie in der Sitzung eindeutig sind.</span><span class="sxs-lookup"><span data-stu-id="b7f3f-242">The **Prefix** parameter adds a prefix to the names of imported commands so that they are unique in the session.</span></span> <span data-ttu-id="b7f3f-243">Der **noClobber** -Parameter importiert keine Befehle, die vorhandene Befehle in der Sitzung ausblenden oder ersetzen würden.</span><span class="sxs-lookup"><span data-stu-id="b7f3f-243">The **NoClobber** parameter does not import any commands that would hide or replace existing commands in the session.</span></span>

<span data-ttu-id="b7f3f-244">Sie können auch die Parameter **Alias** , **Cmdlet** , **Function** und **Variable** von verwenden, `Import-Module` um nur die Befehle auszuwählen, die Sie importieren möchten, und Sie können die Befehle ausschließen, die in Ihrer Sitzung zu Namenskonflikten führen.</span><span class="sxs-lookup"><span data-stu-id="b7f3f-244">You can also use the **Alias** , **Cmdlet** , **Function** , and **Variable** parameters of `Import-Module` to select only the commands that you want to import, and you can exclude commands that cause name conflicts in your session.</span></span>

<span data-ttu-id="b7f3f-245">Modul Autoren können Namenskonflikte mithilfe der **defaultcommandprefix** -Eigenschaft des Modul Manifests verhindern, um allen Befehlsnamen ein Standard Präfix hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="b7f3f-245">Module authors can prevent name conflicts by using the **DefaultCommandPrefix** property of the module manifest to add a default prefix to all command names.</span></span>
<span data-ttu-id="b7f3f-246">Der Wert des **prefix** -Parameters hat Vorrang vor dem Wert von **defaultcommandprefix**.</span><span class="sxs-lookup"><span data-stu-id="b7f3f-246">The value of the **Prefix** parameter takes precedence over the value of **DefaultCommandPrefix**.</span></span>

<span data-ttu-id="b7f3f-247">Selbst wenn ein Befehl ausgeblendet ist, können Sie ihn durch die Qualifizierung des Befehlsnamens mit dem Namen des Moduls oder des ursprüunglichen Snap-Ins ausführen.</span><span class="sxs-lookup"><span data-stu-id="b7f3f-247">Even if a command is hidden, you can run it by qualifying the command name with the name of the module or snap-in in which it originated.</span></span>

<span data-ttu-id="b7f3f-248">Die Regeln der PowerShell-Befehls Rangfolge bestimmen, welcher Befehl ausgeführt wird, wenn die Sitzung Befehle mit demselben Namen enthält.</span><span class="sxs-lookup"><span data-stu-id="b7f3f-248">The PowerShell command precedence rules determine which command runs when the session includes commands with the same name.</span></span>

<span data-ttu-id="b7f3f-249">Wenn eine Sitzung z. b. eine Funktion und ein Cmdlet mit dem gleichen Namen enthält, führt PowerShell die Funktion standardmäßig aus.</span><span class="sxs-lookup"><span data-stu-id="b7f3f-249">For example, when a session includes a function and a cmdlet with the same name, PowerShell runs the function by default.</span></span> <span data-ttu-id="b7f3f-250">Wenn die Sitzung Befehle vom gleichen Typ mit dem gleichen Namen, z. B. zwei Cmdlets mit demselben Namen enthält, wird standardmäßig der zuletzt hinzugefügte Befehl ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="b7f3f-250">When the session includes commands of the same type with the same name, such as two cmdlets with the same name, by default, it runs the most recently added command.</span></span>

<span data-ttu-id="b7f3f-251">Weitere Informationen, einschließlich einer Erläuterung der Rang folgen Regeln und Anweisungen zum Ausführen von ausgeblendeten Befehlen, finden Sie unter [about_Command_Precedence](about_Command_Precedence.md).</span><span class="sxs-lookup"><span data-stu-id="b7f3f-251">For more information, including an explanation of the precedence rules and instructions for running hidden commands, see [about_Command_Precedence](about_Command_Precedence.md).</span></span>

## <a name="modules-and-snap-ins"></a><span data-ttu-id="b7f3f-252">Module und Snap-Ins</span><span class="sxs-lookup"><span data-stu-id="b7f3f-252">Modules and Snap-ins</span></span>

<span data-ttu-id="b7f3f-253">Sie können Ihrer Sitzung Befehle aus Modulen und Snap-Ins hinzufügen. Module können alle Arten von Befehlen, einschließlich Cmdlets, Anbieter, Funktionen und Elemente, wie z. b. Variablen, Aliase und PowerShell-Laufwerke, hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="b7f3f-253">You can add commands to your session from modules and snap-ins. Modules can add all types of commands, including cmdlets, providers, and functions, and items, such as variables, aliases, and PowerShell drives.</span></span> <span data-ttu-id="b7f3f-254">Snap-Ins können nur Cmdlets und Anbieter hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="b7f3f-254">Snap-ins can add only cmdlets and providers.</span></span>

<span data-ttu-id="b7f3f-255">Vor dem Entfernen eines Moduls oder Snap-Ins aus der Sitzung verwenden Sie die folgenden Befehle, um zu bestimmen, welche Befehle entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="b7f3f-255">Before removing a module or snap-in from your session, use the following commands to determine which commands will be removed.</span></span>

<span data-ttu-id="b7f3f-256">Um die Quelle eines Cmdlets in Ihrer Sitzung zu ermitteln, verwenden Sie das folgende Befehls Format:</span><span class="sxs-lookup"><span data-stu-id="b7f3f-256">To find the source of a cmdlet in your session, use the following command format:</span></span>

```powershell
Get-Command <cmdlet-name> | Format-List -Property verb,noun,pssnapin,module
```

<span data-ttu-id="b7f3f-257">Wenn Sie z. b. die Quelle des `Get-Date` Cmdlets ermitteln möchten, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="b7f3f-257">For example, to find the source of the `Get-Date` cmdlet, type:</span></span>

```powershell
Get-Command Get-Date | Format-List -Property verb,noun,module
```

## <a name="module-related-warnings-and-errors"></a><span data-ttu-id="b7f3f-258">Modul bezogene Warnungen und Fehler</span><span class="sxs-lookup"><span data-stu-id="b7f3f-258">Module-related Warnings and Errors</span></span>

<span data-ttu-id="b7f3f-259">Die Befehle, die ein Modul exportiert, müssen die Benennungs Regeln für den PowerShell-Befehl einhalten.</span><span class="sxs-lookup"><span data-stu-id="b7f3f-259">The commands that a module exports should follow the PowerShell command naming rules.</span></span> <span data-ttu-id="b7f3f-260">Wenn das Modul, das Sie importieren, Cmdlets oder Funktionen exportiert, die nicht genehmigte Verben in ihren Namen haben, `Import-Module` zeigt das Cmdlet die folgende Warnmeldung an.</span><span class="sxs-lookup"><span data-stu-id="b7f3f-260">If the module that you import exports cmdlets or functions that have unapproved verbs in their names, the `Import-Module` cmdlet displays the following warning message.</span></span>

> <span data-ttu-id="b7f3f-261">Warnung: einige importierte Befehlsnamen enthalten nicht genehmigte Verben, die Sie möglicherweise weniger auffallen machen.</span><span class="sxs-lookup"><span data-stu-id="b7f3f-261">WARNING: Some imported command names include unapproved verbs which might make them less discoverable.</span></span> <span data-ttu-id="b7f3f-262">Verwenden Sie den Verbose-Parameter für weitere Details, oder geben Sie „Get-Verb“ ein, um die Liste der zulässigen Verben anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="b7f3f-262">Use the Verbose parameter for more detail or type Get-Verb to see the list of approved verbs.</span></span>

<span data-ttu-id="b7f3f-263">Diese Meldung ist nur eine Warnung.</span><span class="sxs-lookup"><span data-stu-id="b7f3f-263">This message is only a warning.</span></span> <span data-ttu-id="b7f3f-264">Es wird trotzdem das gesamte Modul einschließlich nicht konformer Befehle importiert.</span><span class="sxs-lookup"><span data-stu-id="b7f3f-264">The complete module is still imported, including the non-conforming commands.</span></span> <span data-ttu-id="b7f3f-265">Obwohl die Meldung für Modulbenutzer angezeigt wird, sollte das Namensproblem vom Modulautor behoben werden.</span><span class="sxs-lookup"><span data-stu-id="b7f3f-265">Although the message is displayed to module users, the naming problem should be fixed by the module author.</span></span>

<span data-ttu-id="b7f3f-266">Um die Warnmeldung zu unterdrücken, verwenden Sie den **disablenamecheck** -Parameter des `Import-Module` Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="b7f3f-266">To suppress the warning message, use the **DisableNameChecking** parameter of the `Import-Module` cmdlet.</span></span>

## <a name="built-in-modules-and-snap-ins"></a><span data-ttu-id="b7f3f-267">Integrierte Module und Snap-Ins</span><span class="sxs-lookup"><span data-stu-id="b7f3f-267">Built-in Modules and Snap-ins</span></span>

<span data-ttu-id="b7f3f-268">In PowerShell 2,0 und älteren Host Programmen in PowerShell 3,0 und höher werden die Kern Befehle, die mit PowerShell installiert werden, in Snap-Ins verpackt, die automatisch zu jeder PowerShell-Sitzung hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="b7f3f-268">In PowerShell 2.0 and in older-style host programs in PowerShell 3.0 and later, the core commands that are installed with PowerShell are packaged in snap-ins that are added automatically to every PowerShell session.</span></span>

<span data-ttu-id="b7f3f-269">Ab PowerShell 3,0 wird für Host Programme, die die `InitialSessionState.CreateDefault2` erste Sitzungs Status-API implementieren, das Microsoft. PowerShell. Core-Snap-in jeder Sitzung standardmäßig hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="b7f3f-269">Beginning in PowerShell 3.0, for host programs that implement the `InitialSessionState.CreateDefault2` initial session state API the Microsoft.PowerShell.Core snap-in is added to every session by default.</span></span> <span data-ttu-id="b7f3f-270">Module werden automatisch bei der ersten Verwendung geladen.</span><span class="sxs-lookup"><span data-stu-id="b7f3f-270">Modules are loaded automatically on first-use.</span></span>

> [!NOTE]
> <span data-ttu-id="b7f3f-271">Remote Sitzungen, einschließlich Sitzungen, die mithilfe des `New-PSSession` Cmdlets gestartet werden, sind Sitzungen älterer Sitzungen, in denen die integrierten Befehle in Snap-Ins verpackt werden.</span><span class="sxs-lookup"><span data-stu-id="b7f3f-271">Remote sessions, including sessions that are started by using the `New-PSSession` cmdlet, are older-style sessions in which the built-in commands are packaged in snap-ins.</span></span>

<span data-ttu-id="b7f3f-272">Die folgenden Module (oder Snap-Ins) werden mit PowerShell installiert.</span><span class="sxs-lookup"><span data-stu-id="b7f3f-272">The following modules (or snap-ins) are installed with PowerShell.</span></span>

- <span data-ttu-id="b7f3f-273">CimCmdlets</span><span class="sxs-lookup"><span data-stu-id="b7f3f-273">CimCmdlets</span></span>
- <span data-ttu-id="b7f3f-274">Microsoft.PowerShell.Archive</span><span class="sxs-lookup"><span data-stu-id="b7f3f-274">Microsoft.PowerShell.Archive</span></span>
- <span data-ttu-id="b7f3f-275">Microsoft.PowerShell.Core</span><span class="sxs-lookup"><span data-stu-id="b7f3f-275">Microsoft.PowerShell.Core</span></span>
- <span data-ttu-id="b7f3f-276">Microsoft.PowerShell.Diagnostics</span><span class="sxs-lookup"><span data-stu-id="b7f3f-276">Microsoft.PowerShell.Diagnostics</span></span>
- <span data-ttu-id="b7f3f-277">Microsoft.PowerShell.Host</span><span class="sxs-lookup"><span data-stu-id="b7f3f-277">Microsoft.PowerShell.Host</span></span>
- <span data-ttu-id="b7f3f-278">Microsoft.PowerShell.Management</span><span class="sxs-lookup"><span data-stu-id="b7f3f-278">Microsoft.PowerShell.Management</span></span>
- <span data-ttu-id="b7f3f-279">Microsoft.PowerShell.Security</span><span class="sxs-lookup"><span data-stu-id="b7f3f-279">Microsoft.PowerShell.Security</span></span>
- <span data-ttu-id="b7f3f-280">Microsoft.PowerShell.Utility</span><span class="sxs-lookup"><span data-stu-id="b7f3f-280">Microsoft.PowerShell.Utility</span></span>
- <span data-ttu-id="b7f3f-281">Microsoft.WSMan.Management</span><span class="sxs-lookup"><span data-stu-id="b7f3f-281">Microsoft.WSMan.Management</span></span>
- <span data-ttu-id="b7f3f-282">PackageManagement</span><span class="sxs-lookup"><span data-stu-id="b7f3f-282">PackageManagement</span></span>
- <span data-ttu-id="b7f3f-283">PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="b7f3f-283">PowerShellGet</span></span>
- <span data-ttu-id="b7f3f-284">PSDesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="b7f3f-284">PSDesiredStateConfiguration</span></span>
- <span data-ttu-id="b7f3f-285">PSDiagnostics</span><span class="sxs-lookup"><span data-stu-id="b7f3f-285">PSDiagnostics</span></span>
- <span data-ttu-id="b7f3f-286">PSReadline</span><span class="sxs-lookup"><span data-stu-id="b7f3f-286">PSReadline</span></span>

## <a name="logging-module-events"></a><span data-ttu-id="b7f3f-287">Protokollieren von Modul Ereignissen</span><span class="sxs-lookup"><span data-stu-id="b7f3f-287">Logging Module Events</span></span>

<span data-ttu-id="b7f3f-288">Ab PowerShell 3,0 können Sie Ausführungs Ereignisse für die Cmdlets und Funktionen in PowerShell-Modulen und-Snap-Ins aufzeichnen, indem Sie die **logpipelineexecutiondetails** -Eigenschaft von Modulen und Snap-Ins auf festlegen `$True` .</span><span class="sxs-lookup"><span data-stu-id="b7f3f-288">Beginning in PowerShell 3.0, you can record execution events for the cmdlets and functions in PowerShell modules and snap-ins by setting the **LogPipelineExecutionDetails** property of modules and snap-ins to `$True`.</span></span>
<span data-ttu-id="b7f3f-289">Sie können auch eine Gruppenrichtlinie Einstellung, die Modul Protokollierung aktivieren, verwenden, um die Modul Protokollierung in allen PowerShell-Sitzungen zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="b7f3f-289">You can also use a Group Policy setting, Turn on Module Logging, to enable module logging in all PowerShell sessions.</span></span> <span data-ttu-id="b7f3f-290">Weitere Informationen finden Sie in den Artikeln Protokollierung und Gruppenrichtlinie.</span><span class="sxs-lookup"><span data-stu-id="b7f3f-290">For more information, see the logging and group policy articles.</span></span>

## <a name="see-also"></a><span data-ttu-id="b7f3f-291">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b7f3f-291">See Also</span></span>

[<span data-ttu-id="b7f3f-292">about_Logging_Windows</span><span class="sxs-lookup"><span data-stu-id="b7f3f-292">about_Logging_Windows</span></span>](about_Logging_Windows.md)

[<span data-ttu-id="b7f3f-293">about_Logging_Non-Windows</span><span class="sxs-lookup"><span data-stu-id="b7f3f-293">about_Logging_Non-Windows</span></span>](about_Logging_Non-Windows.md)

[<span data-ttu-id="b7f3f-294">about_Group_Policy_Settings</span><span class="sxs-lookup"><span data-stu-id="b7f3f-294">about_Group_Policy_Settings</span></span>](about_Group_Policy_Settings.md)

[<span data-ttu-id="b7f3f-295">about_Command_Precedence</span><span class="sxs-lookup"><span data-stu-id="b7f3f-295">about_Command_Precedence</span></span>](about_Command_Precedence.md)

[<span data-ttu-id="b7f3f-296">about_Group_Policy_Settings</span><span class="sxs-lookup"><span data-stu-id="b7f3f-296">about_Group_Policy_Settings</span></span>](about_Group_Policy_Settings.md)

[<span data-ttu-id="b7f3f-297">Get-Command</span><span class="sxs-lookup"><span data-stu-id="b7f3f-297">Get-Command</span></span>](xref:Microsoft.PowerShell.Core.Get-Command)

[<span data-ttu-id="b7f3f-298">Get-Help</span><span class="sxs-lookup"><span data-stu-id="b7f3f-298">Get-Help</span></span>](xref:Microsoft.PowerShell.Core.Get-Help)

[<span data-ttu-id="b7f3f-299">Get-Module</span><span class="sxs-lookup"><span data-stu-id="b7f3f-299">Get-Module</span></span>](xref:Microsoft.PowerShell.Core.Get-Module)

[<span data-ttu-id="b7f3f-300">Import-Module</span><span class="sxs-lookup"><span data-stu-id="b7f3f-300">Import-Module</span></span>](xref:Microsoft.PowerShell.Core.Import-Module)

[<span data-ttu-id="b7f3f-301">Remove-Module</span><span class="sxs-lookup"><span data-stu-id="b7f3f-301">Remove-Module</span></span>](xref:Microsoft.PowerShell.Core.Remove-Module)
