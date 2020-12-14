---
description: Erläutert das installieren, importieren und Verwenden von PowerShell-Modulen.
Locale: en-US
ms.date: 12/03/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_modules?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Modules
ms.openlocfilehash: ab4e9658ed4820c3ae84ac1cd9a55b59cc8017ab
ms.sourcegitcommit: 7b376314e7640c39a53aac9f0db8bb935514a960
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2020
ms.locfileid: "96564478"
---
# <a name="about-modules"></a><span data-ttu-id="b9fe0-103">Informationen zu Modulen</span><span class="sxs-lookup"><span data-stu-id="b9fe0-103">About Modules</span></span>

## <a name="short-description"></a><span data-ttu-id="b9fe0-104">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b9fe0-104">Short Description</span></span>
<span data-ttu-id="b9fe0-105">Erläutert das installieren, importieren und Verwenden von PowerShell-Modulen.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-105">Explains how to install, import, and use PowerShell modules.</span></span>

## <a name="long-description"></a><span data-ttu-id="b9fe0-106">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b9fe0-106">Long Description</span></span>

<span data-ttu-id="b9fe0-107">Ein Modul ist ein Paket, das PowerShell-Member enthält, z. b. Cmdlets, Anbieter, Funktionen, Workflows, Variablen und Aliase.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-107">A module is a package that contains PowerShell members, such as cmdlets, providers, functions, workflows, variables, and aliases.</span></span>

<span data-ttu-id="b9fe0-108">Personen, die Befehle schreiben, können Module verwenden, um ihre Befehle zu organisieren und für andere Benutzer freizugeben.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-108">People who write commands can use modules to organize their commands and share them with others.</span></span> <span data-ttu-id="b9fe0-109">Personen, die Module erhalten, können die Befehle in den Modulen ihren PowerShell-Sitzungen hinzufügen und wie die integrierten Befehle verwenden.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-109">People who receive modules can add the commands in the modules to their PowerShell sessions and use them just like the built-in commands.</span></span>

<span data-ttu-id="b9fe0-110">In diesem Thema wird die Verwendung von PowerShell-Modulen erläutert.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-110">This topic explains how to use PowerShell modules.</span></span> <span data-ttu-id="b9fe0-111">Informationen zum Schreiben von PowerShell-Modulen finden Sie unter [Schreiben eines PowerShell-Moduls](/powershell/scripting/developer/module/writing-a-windows-powershell-module).</span><span class="sxs-lookup"><span data-stu-id="b9fe0-111">For information about how to write PowerShell modules, see [Writing a PowerShell Module](/powershell/scripting/developer/module/writing-a-windows-powershell-module).</span></span>

## <a name="what-is-a-module"></a><span data-ttu-id="b9fe0-112">Was ist ein Modul?</span><span class="sxs-lookup"><span data-stu-id="b9fe0-112">What Is a Module?</span></span>

<span data-ttu-id="b9fe0-113">Ein Modul ist ein Paket, das PowerShell-Member enthält, z. b. Cmdlets, Anbieter, Funktionen, Workflows, Variablen und Aliase.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-113">A module is a package that contains PowerShell members, such as cmdlets, providers, functions, workflows, variables, and aliases.</span></span> <span data-ttu-id="b9fe0-114">Die Mitglieder dieses Pakets können in einem PowerShell-Skript, einer kompilierten DLL oder einer Kombination aus beidem implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-114">The members of this package can be implemented in a PowerShell script, a compiled DLL, or a combination of both.</span></span> <span data-ttu-id="b9fe0-115">Diese Dateien werden normalerweise in einem Verzeichnis zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-115">These files are usually grouped together in a single directory.</span></span> <span data-ttu-id="b9fe0-116">Weitere Informationen finden Sie Untergrund Legendes zu [einem Windows PowerShell-Modul](/powershell/scripting/developer/module/understanding-a-windows-powershell-module) in der SDK-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-116">For more information, see [Understanding a Windows PowerShell Module](/powershell/scripting/developer/module/understanding-a-windows-powershell-module) in the SDK documentation.</span></span>

## <a name="module-auto-loading"></a><span data-ttu-id="b9fe0-117">Automatisches Laden von Modulen</span><span class="sxs-lookup"><span data-stu-id="b9fe0-117">Module Auto-Loading</span></span>

<span data-ttu-id="b9fe0-118">Ab PowerShell 3,0 importiert PowerShell automatisch Module, wenn Sie zum ersten Mal einen Befehl in einem installierten Modul ausführen.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-118">Beginning in PowerShell 3.0, PowerShell imports modules automatically the first time that you run any command in an installed module.</span></span> <span data-ttu-id="b9fe0-119">Sie können jetzt die Befehle in einem Modul ohne weitere Einrichtung oder Profilkonfiguration verwenden, daher besteht keine Notwendigkeit, Module nach der Installation auf Ihrem Computer zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-119">You can now use the commands in a module without any set-up or profile configuration, so there's no need to manage modules after you install them on your computer.</span></span>

<span data-ttu-id="b9fe0-120">Die Befehle in einem Modul sind auch leichter zu finden.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-120">The commands in a module are also easier to find.</span></span> <span data-ttu-id="b9fe0-121">Das `Get-Command` Cmdlet ruft nun alle Befehle in allen installierten Modulen ab, auch wenn Sie noch nicht in der Sitzung sind.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-121">The `Get-Command` cmdlet now gets all commands in all installed modules, even if they are not yet in the session.</span></span> <span data-ttu-id="b9fe0-122">Sie können einen Befehl Suchen und verwenden, ohne zu importieren, dass Sie zuerst das Modul importieren müssen.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-122">You can find a command and use it without importing needing to import the module first.</span></span>

<span data-ttu-id="b9fe0-123">Jedes der folgenden Beispiele bewirkt, dass das cimcmdlets-Modul, das enthält `Get-CimInstance` , in Ihre Sitzung importiert wird.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-123">Each of the following examples cause the CimCmdlets module, which contains `Get-CimInstance`, to be imported into your session.</span></span>

- <span data-ttu-id="b9fe0-124">Ausführen des Befehls</span><span class="sxs-lookup"><span data-stu-id="b9fe0-124">Run the Command</span></span>

  ```powershell
  Get-CimInstance Win32_OperatingSystem
  ```

- <span data-ttu-id="b9fe0-125">Befehl "Get"</span><span class="sxs-lookup"><span data-stu-id="b9fe0-125">Get the Command</span></span>

  ```powershell
  Get-Command Get-CimInstance
  ```

- <span data-ttu-id="b9fe0-126">Hilfe zum Befehl</span><span class="sxs-lookup"><span data-stu-id="b9fe0-126">Get Help for the Command</span></span>

  ```powershell
  Get-Help Get-CimInstance
  ```

<span data-ttu-id="b9fe0-127">`Get-Command` Befehle, die ein Platzhalter Zeichen () enthalten, werden `*` als zu erkennen, nicht zu verwenden und keine Module importiert.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-127">`Get-Command` commands that include a wildcard character (`*`) are considered to be for discovery, not use, and do not import any modules.</span></span>

<span data-ttu-id="b9fe0-128">Nur Module, die an dem von der psmodulepath-Umgebungsvariablen angegebenen Speicherort gespeichert sind, werden automatisch importiert.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-128">Only modules that are stored in the location specified by the PSModulePath environment variable are automatically imported.</span></span> <span data-ttu-id="b9fe0-129">Module an anderen Speicherorten müssen importiert werden, indem das `Import-Module` Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-129">Modules in other locations must be imported by running the `Import-Module` cmdlet.</span></span>

<span data-ttu-id="b9fe0-130">Außerdem importieren Befehle, die PowerShell-Anbieter verwenden, nicht automatisch ein Modul.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-130">Also, commands that use PowerShell providers do not automatically import a module.</span></span> <span data-ttu-id="b9fe0-131">Wenn Sie z. b. einen Befehl verwenden, der das WSMAN:-Laufwerk benötigt (z. b. das `Get-PSSessionConfiguration` Cmdlet), müssen Sie möglicherweise das `Import-Module` Cmdlet ausführen, um das **Microsoft. WSMAN. Management** -Modul zu importieren, das das `WSMan:` Laufwerk enthält.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-131">For example, if you use a command that requires the WSMan: drive, such as the `Get-PSSessionConfiguration` cmdlet, you might need to run the `Import-Module` cmdlet to import the **Microsoft.WSMan.Management** module that includes the `WSMan:` drive.</span></span>

<span data-ttu-id="b9fe0-132">Sie können weiterhin den `Import-Module` Befehl ausführen, um ein Modul zu importieren, und die `$PSModuleAutoloadingPreference` Variable verwenden, um das automatische Importieren von Modulen zu aktivieren, zu deaktivieren und zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-132">You can still run the `Import-Module` command to import a module and use the `$PSModuleAutoloadingPreference` variable to enable, disable and configure automatic importing of modules.</span></span> <span data-ttu-id="b9fe0-133">Weitere Informationen finden Sie unter [about_Preference_Variables](about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="b9fe0-133">For more information, see [about_Preference_Variables](about_Preference_Variables.md).</span></span>

## <a name="how-to-use-a-module"></a><span data-ttu-id="b9fe0-134">Verwenden eines Moduls</span><span class="sxs-lookup"><span data-stu-id="b9fe0-134">How to Use a Module</span></span>

<span data-ttu-id="b9fe0-135">Um ein Modul zu verwenden, führen Sie die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="b9fe0-135">To use a module, perform the following tasks:</span></span>

1. <span data-ttu-id="b9fe0-136">Installieren Sie das Modul.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-136">Install the module.</span></span> <span data-ttu-id="b9fe0-137">(Dies wird häufig für Sie durchgeführt.)</span><span class="sxs-lookup"><span data-stu-id="b9fe0-137">(This is often done for you.)</span></span>
1. <span data-ttu-id="b9fe0-138">Suchen Sie die Befehle, die das Modul hinzugefügt hat.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-138">Find the commands that the module added.</span></span>
1. <span data-ttu-id="b9fe0-139">Verwenden Sie die Befehle, die das Modul hinzugefügt hat.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-139">Use the commands that the module added.</span></span>

<span data-ttu-id="b9fe0-140">In diesem Thema wird erläutert, wie Sie diese Aufgaben ausführen.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-140">This topic explains how to perform these tasks.</span></span> <span data-ttu-id="b9fe0-141">Darüber hinaus gibt es weitere wichtige Informationen zur Verwaltung von Modulen.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-141">It also includes other useful information about managing modules.</span></span>

## <a name="how-to-install-a-module"></a><span data-ttu-id="b9fe0-142">Installieren eines Moduls</span><span class="sxs-lookup"><span data-stu-id="b9fe0-142">How to Install a Module</span></span>

<span data-ttu-id="b9fe0-143">Wenn Sie ein Modul als Ordner mit Dateien erhalten, müssen Sie es auf dem Computer installieren, bevor Sie es in PowerShell verwenden können.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-143">If you receive a module as a folder with files in it, you need to install it on your computer before you can use it in PowerShell.</span></span>

<span data-ttu-id="b9fe0-144">Die meisten Module werden für Sie installiert.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-144">Most modules are installed for you.</span></span> <span data-ttu-id="b9fe0-145">PowerShell verfügt über mehrere vorinstallierte Module, die manchmal auch als _Kern_ Module bezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-145">PowerShell comes with several preinstalled modules, sometimes called the _core_ modules.</span></span> <span data-ttu-id="b9fe0-146">Wenn auf Windows-basierten Computern Features, die im Betriebssystem enthalten sind, über Cmdlets zur Verwaltung verfügen, sind diese Module vorinstalliert.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-146">On Windows-based computers, if features that are included with the operating system have cmdlets to manage them, those modules are preinstalled.</span></span> <span data-ttu-id="b9fe0-147">Wenn Sie ein Windows-Feature wie z. b. den Assistenten zum Hinzufügen von Rollen und Features in Server-Manager oder das Dialogfeld Windows-Funktionen ein-oder ausschalten in der Systemsteuerung installieren, werden alle PowerShell-Module installiert, die Teil der Funktion sind.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-147">When you install a Windows feature, by using, for example, the Add Roles and Features Wizard in Server Manager, or the Turn Windows features on or off dialog box in Control Panel, any PowerShell modules that are part of the feature are installed.</span></span> <span data-ttu-id="b9fe0-148">Viele andere Module sind in einem Installationsprogramm oder Setup-Programm, mit dem das Modul installiert wird.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-148">Many other modules come in an installer or Setup program that installs the module.</span></span>

<span data-ttu-id="b9fe0-149">Verwenden Sie den folgenden Befehl, um ein **Modul** Verzeichnis für den aktuellen Benutzer zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="b9fe0-149">Use the following command to create a **Modules** directory for the current user:</span></span>

```powershell
New-Item -Type Directory -Path $HOME\Documents\PowerShell\Modules
```

<span data-ttu-id="b9fe0-150">Kopieren Sie den gesamten Modulordner in das Verzeichnis „Modules“.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-150">Copy the entire module folder into the Modules directory.</span></span> <span data-ttu-id="b9fe0-151">Sie können eine beliebige Methode verwenden, um den Ordner zu kopieren, einschließlich Windows Explorer und Cmd.exe sowie PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-151">You can use any method to copy the folder, including Windows Explorer and Cmd.exe, as well as PowerShell.</span></span> <span data-ttu-id="b9fe0-152">Verwenden Sie das `Copy-Item` Cmdlet in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-152">In PowerShell use the `Copy-Item` cmdlet.</span></span> <span data-ttu-id="b9fe0-153">Um beispielsweise den Ordner "MyModule" aus `C:\ps-test\MyModule` in das Verzeichnis "modules" zu kopieren, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="b9fe0-153">For example, to copy the MyModule folder from `C:\ps-test\MyModule` to the Modules directory, type:</span></span>

```powershell
Copy-Item -Path C:\ps-test\MyModule -Destination `
    $HOME\Documents\PowerShell\Modules
```

<span data-ttu-id="b9fe0-154">Sie können ein Modul an einem beliebigen Speicherort installieren, aber wenn Sie Ihre Module an einem Standardspeicherort installieren, sind sie leichter zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-154">You can install a module in any location, but installing your modules in a default module location makes them easier to manage.</span></span> <span data-ttu-id="b9fe0-155">Weitere Informationen zu den standardmäßigen Modul Speicherorten finden Sie im Abschnitt " [Module und DSC-Ressourcen Speicherorte" und "psmodulepath](#module-and-dsc-resource-locations-and-psmodulepath) ".</span><span class="sxs-lookup"><span data-stu-id="b9fe0-155">For more information about the default module locations, see the [Module and DSC Resource Locations, and PSModulePath](#module-and-dsc-resource-locations-and-psmodulepath) section.</span></span>

## <a name="how-to-find-installed-modules"></a><span data-ttu-id="b9fe0-156">So finden Sie installierte Module</span><span class="sxs-lookup"><span data-stu-id="b9fe0-156">How to Find Installed Modules</span></span>

<span data-ttu-id="b9fe0-157">Geben Sie Folgendes ein, um Module zu suchen, die an einem Modul-Standardspeicherort installiert sind, jedoch noch nicht in die Sitzung importiert wurden:</span><span class="sxs-lookup"><span data-stu-id="b9fe0-157">To find modules that are installed in a default module location, but not yet imported into your session, type:</span></span>

```powershell
Get-Module -ListAvailable
```

<span data-ttu-id="b9fe0-158">Geben Sie an der PowerShell-Eingabeaufforderung Folgendes ein, um die Module zu suchen, die bereits in die Sitzung importiert wurden:</span><span class="sxs-lookup"><span data-stu-id="b9fe0-158">To find the modules that have already been imported into your session, at the PowerShell prompt, type:</span></span>

```powershell
Get-Module
```

<span data-ttu-id="b9fe0-159">Weitere Informationen zum `Get-Module` Cmdlet finden [Sie unter Get-Module](xref:Microsoft.PowerShell.Core.Get-Module).</span><span class="sxs-lookup"><span data-stu-id="b9fe0-159">For more information about the `Get-Module` cmdlet, see [Get-Module](xref:Microsoft.PowerShell.Core.Get-Module).</span></span>

## <a name="how-to-find-the-commands-in-a-module"></a><span data-ttu-id="b9fe0-160">Suchen der Befehle in einem Modul</span><span class="sxs-lookup"><span data-stu-id="b9fe0-160">How to Find the Commands in a Module</span></span>

<span data-ttu-id="b9fe0-161">Verwenden `Get-Command` Sie das Cmdlet, um alle verfügbaren Befehle zu suchen.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-161">Use the `Get-Command` cmdlet to find all available commands.</span></span> <span data-ttu-id="b9fe0-162">Sie können die Parameter des `Get-Command` Cmdlets verwenden, um Befehle wie z. b. nach Modul, Namen und Nomen zu filtern.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-162">You can use the parameters of the `Get-Command` cmdlet to filter commands such as by module, name, and noun.</span></span>

<span data-ttu-id="b9fe0-163">Um alle Befehle in einem Modul zu suchen, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="b9fe0-163">To find all commands in a module, type:</span></span>

```powershell
Get-Command -Module <module-name>
```

<span data-ttu-id="b9fe0-164">Wenn Sie z. b. die Befehle im bitstransfer-Modul suchen möchten, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="b9fe0-164">For example, to find the commands in the BitsTransfer module, type:</span></span>

```powershell
Get-Command -Module BitsTransfer
```

<span data-ttu-id="b9fe0-165">Weitere Informationen zum `Get-Command` Cmdlet finden [Sie unter Get-Command](xref:Microsoft.PowerShell.Core.Get-Command).</span><span class="sxs-lookup"><span data-stu-id="b9fe0-165">For more information about the `Get-Command` cmdlet, see [Get-Command](xref:Microsoft.PowerShell.Core.Get-Command).</span></span>

## <a name="how-to-get-help-for-the-commands-in-a-module"></a><span data-ttu-id="b9fe0-166">So erhalten Sie Hilfe für die Befehle in einem Modul</span><span class="sxs-lookup"><span data-stu-id="b9fe0-166">How to Get Help for the Commands in a Module</span></span>

<span data-ttu-id="b9fe0-167">Wenn das Modul Hilfedateien für die Befehle enthält, die es exportiert, `Get-Help` zeigt das Cmdlet die Hilfe Themen an.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-167">If the module contains Help files for the commands that it exports, the `Get-Help` cmdlet will display the Help topics.</span></span> <span data-ttu-id="b9fe0-168">Verwenden Sie das gleiche `Get-Help` Befehls Format, das Sie verwenden, um Hilfe zu einem beliebigen Befehl in PowerShell zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-168">Use the same `Get-Help` command format that you would use to get help for any command in PowerShell.</span></span>

<span data-ttu-id="b9fe0-169">Ab PowerShell 3,0 können Sie Hilfedateien für ein Modul herunterladen und Updates in die Hilfedateien herunterladen, damit Sie nie veraltet sind.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-169">Beginning in PowerShell 3.0, you can download Help files for a module and download updates to the Help files so they are never obsolete.</span></span>

<span data-ttu-id="b9fe0-170">Um Hilfe für Befehle in einem Modul zu erhalten, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="b9fe0-170">To get help for a commands in a module, type:</span></span>

```powershell
Get-Help <command-name>
```

<span data-ttu-id="b9fe0-171">Um die Hilfe für den Befehl in einem Modul online zu erhalten, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="b9fe0-171">To get help online for command in a module, type:</span></span>

```powershell
Get-Help <command-name> -Online
```

<span data-ttu-id="b9fe0-172">Geben Sie Folgendes ein, um die Hilfedateien für die Befehle in einem Modul herunterzuladen und zu installieren:</span><span class="sxs-lookup"><span data-stu-id="b9fe0-172">To download and install the help files for the commands in a module, type:</span></span>

```powershell
Update-Help -Module <module-name>
```

<span data-ttu-id="b9fe0-173">Weitere Informationen finden Sie unter " [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) " und " [Update-Help](xref:Microsoft.PowerShell.Core.Update-Help)".</span><span class="sxs-lookup"><span data-stu-id="b9fe0-173">For more information, see [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) and [Update-Help](xref:Microsoft.PowerShell.Core.Update-Help).</span></span>

## <a name="how-to-import-a-module"></a><span data-ttu-id="b9fe0-174">Importieren eines Moduls</span><span class="sxs-lookup"><span data-stu-id="b9fe0-174">How to Import a Module</span></span>

<span data-ttu-id="b9fe0-175">Sie müssen möglicherweise ein Modul oder eine Moduldatei importieren.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-175">You might have to import a module or import a module file.</span></span> <span data-ttu-id="b9fe0-176">Der Import ist erforderlich, wenn ein Modul nicht an den von der **psmodulepath** -Umgebungsvariablen angegebenen Speicherorten installiert ist, `$env:PSModulePath` oder wenn das Modul aus einer Datei besteht (z. b. eine DLL-oder. psm1-Datei), anstelle eines typischen Moduls, das als Ordner übermittelt wird.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-176">Importing is required when a module is not installed in the locations specified by the **PSModulePath** environment variable, `$env:PSModulePath`, or the module consists of file, such as a .dll or .psm1 file, instead of typical module that is delivered as a folder.</span></span>

<span data-ttu-id="b9fe0-177">Sie können auch ein Modul importieren, sodass Sie die Parameter des Befehls verwenden können, z. b. `Import-Module` den prefix-Parameter, der den Substantiv Namen aller importierten Befehle ein eindeutiges Präfix hinzufügt, oder den **noClobber** -Parameter, der verhindert, dass das Modul Befehle hinzufügt, die vorhandene Befehle in der Sitzung ausblenden oder ersetzen würden.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-177">You might also choose to import a module so that you can use the parameters of the `Import-Module` command, such as the Prefix parameter, which adds a distinctive prefix to the noun names of all imported commands, or the **NoClobber** parameter, which prevents the module from adding commands that would hide or replace existing commands in the session.</span></span>

<span data-ttu-id="b9fe0-178">Verwenden Sie das-Cmdlet, um Module zu importieren `Import-Module` .</span><span class="sxs-lookup"><span data-stu-id="b9fe0-178">To import modules, use the `Import-Module` cmdlet.</span></span>

<span data-ttu-id="b9fe0-179">Verwenden Sie das folgende Befehlsformat, um Module an einen PSModulePath-Speicherort in der aktuellen Sitzung zu importieren.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-179">To import modules in a PSModulePath location into the current session, use the following command format.</span></span>

```powershell
Import-Module <module-name>
```

<span data-ttu-id="b9fe0-180">Mit dem folgenden Befehl importieren Sie beispielsweise das Modul "BitsTransfer" in die aktuelle Sitzung.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-180">For example, the following command imports the BitsTransfer module into the current session.</span></span>

```powershell
Import-Module BitsTransfer
```

<span data-ttu-id="b9fe0-181">Verwenden Sie zum Importieren eines Moduls, das sich nicht am Standard-Modulspeicherort befindet, den vollqualifizierten Pfad zum Modulordner im Befehl.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-181">To import a module that is not in a default module location, use the fully qualified path to the module folder in the command.</span></span>

<span data-ttu-id="b9fe0-182">Wenn Sie z. b. das Modul testcmdlets im Verzeichnis der Sitzung hinzufügen möchten, geben Sie Folgendes ein `C:\ps-test` :</span><span class="sxs-lookup"><span data-stu-id="b9fe0-182">For example, to add the TestCmdlets module in the `C:\ps-test` directory to your session, type:</span></span>

```powershell
Import-Module C:\ps-test\TestCmdlets
```

<span data-ttu-id="b9fe0-183">Um eine Moduldatei zu importieren, die nicht in einem Modulordner enthalten ist, verwenden Sie den vollqualifizierten Pfad der Moduldatei im Befehl.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-183">To import a module file that is not contained in a module folder, use the fully qualified path to the module file in the command.</span></span>

<span data-ttu-id="b9fe0-184">Wenn Sie z. b. der Sitzung das TestCmdlets.dll Modul im Verzeichnis hinzufügen möchten, geben Sie Folgendes ein `C:\ps-test` :</span><span class="sxs-lookup"><span data-stu-id="b9fe0-184">For example, to add the TestCmdlets.dll module in the `C:\ps-test` directory to your session, type:</span></span>

```powershell
Import-Module C:\ps-test\TestCmdlets.dll
```

<span data-ttu-id="b9fe0-185">Weitere Informationen zum Hinzufügen von Modulen zu Ihrer Sitzung finden Sie unter [Import-Module](xref:Microsoft.PowerShell.Core.Import-Module).</span><span class="sxs-lookup"><span data-stu-id="b9fe0-185">For more information about adding modules to your session, see [Import-Module](xref:Microsoft.PowerShell.Core.Import-Module).</span></span>

## <a name="how-to-import-a-module-into-every-session"></a><span data-ttu-id="b9fe0-186">Importieren eines Moduls in jede Sitzung</span><span class="sxs-lookup"><span data-stu-id="b9fe0-186">How to Import a Module into Every Session</span></span>

<span data-ttu-id="b9fe0-187">Der `Import-Module` Befehl importiert Module in Ihre aktuelle PowerShell-Sitzung.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-187">The `Import-Module` command imports modules into your current PowerShell session.</span></span> <span data-ttu-id="b9fe0-188">Wenn Sie ein Modul in jede PowerShell-Sitzung importieren möchten, die Sie starten, fügen Sie den `Import-Module` Befehl zu Ihrem PowerShell-Profil hinzu.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-188">To import a module into every PowerShell session that you start, add the `Import-Module` command to your PowerShell profile.</span></span>

<span data-ttu-id="b9fe0-189">Weitere Informationen zu Profilen finden Sie unter [about_Profiles](about_Profiles.md).</span><span class="sxs-lookup"><span data-stu-id="b9fe0-189">For more information about profiles, see [about_Profiles](about_Profiles.md).</span></span>

## <a name="how-to-remove-a-module"></a><span data-ttu-id="b9fe0-190">Entfernen eines Moduls</span><span class="sxs-lookup"><span data-stu-id="b9fe0-190">How to Remove a Module</span></span>

<span data-ttu-id="b9fe0-191">Wenn Sie ein Modul entfernen, werden die vom Modul hinzugefügten Befehle aus der Sitzung gelöscht.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-191">When you remove a module, the commands that the module added are deleted from the session.</span></span>

<span data-ttu-id="b9fe0-192">Verwenden Sie das folgende Befehls Format, um ein Modul aus der Sitzung zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-192">To remove a module from your session, use the following command format.</span></span>

```powershell
Remove-Module <module-name>
```

<span data-ttu-id="b9fe0-193">Mit dem folgenden Befehl wird beispielsweise das Modul "bitstransfer" aus der aktuellen Sitzung entfernt.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-193">For example, the following command removes the BitsTransfer module from the current session.</span></span>

```powershell
Remove-Module BitsTransfer
```

<span data-ttu-id="b9fe0-194">Entfernen einrd Moduld kehrt den Vorgang des Modulimports um.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-194">Removing a module reverses the operation of importing a module.</span></span> <span data-ttu-id="b9fe0-195">Beim Entfernen eines Moduls wird das Modul nicht deinstalliert.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-195">Removing a module does not uninstall the module.</span></span> <span data-ttu-id="b9fe0-196">Weitere Informationen finden Sie unter [Remove-Module](xref:Microsoft.PowerShell.Core.Remove-Module).</span><span class="sxs-lookup"><span data-stu-id="b9fe0-196">For more information, see [Remove-Module](xref:Microsoft.PowerShell.Core.Remove-Module).</span></span>

## <a name="module-and-dsc-resource-locations-and-psmodulepath"></a><span data-ttu-id="b9fe0-197">Modul-und DSC-Ressourcen Speicherorte und psmodulepath</span><span class="sxs-lookup"><span data-stu-id="b9fe0-197">Module and DSC Resource Locations, and PSModulePath</span></span>

<span data-ttu-id="b9fe0-198">Die `$env:PSModulePath` Umgebungsvariable enthält eine Liste der Ordner Speicherorte, die durchsucht werden, um Module und Ressourcen zu finden.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-198">The `$env:PSModulePath` environment variable contains a list of folder locations that are searched to find modules and resources.</span></span>

<span data-ttu-id="b9fe0-199">Standardmäßig sind die folgenden effektiven Speicherorte zugewiesen `$env:PSModulePath` :</span><span class="sxs-lookup"><span data-stu-id="b9fe0-199">By default, the effective locations assigned to `$env:PSModulePath` are:</span></span>

- <span data-ttu-id="b9fe0-200">System weite Standorte: `$PSHOME\Modules`</span><span class="sxs-lookup"><span data-stu-id="b9fe0-200">System-wide locations: `$PSHOME\Modules`</span></span>

  <span data-ttu-id="b9fe0-201">Diese Ordner enthalten Module, die mit Windows und PowerShell ausgeliefert werden.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-201">These folders contain modules that ship with Windows and PowerShell.</span></span>

  <span data-ttu-id="b9fe0-202">DSC-Ressourcen, die in PowerShell enthalten sind, werden im `$PSHOME\Modules\PSDesiredStateConfiguration\DSCResources` Ordner gespeichert.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-202">DSC resources that are included with PowerShell are stored in the `$PSHOME\Modules\PSDesiredStateConfiguration\DSCResources` folder.</span></span>

- <span data-ttu-id="b9fe0-203">Benutzerspezifische Module: Hierbei handelt es sich um Module, die vom Benutzer im Gültigkeitsbereich des Benutzers installiert werden.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-203">User-specific modules: These are modules installed by the user in the user's scope.</span></span> <span data-ttu-id="b9fe0-204">`Install-Module` verfügt über einen **Scope** -Parameter, mit dem Sie angeben können, ob das Modul für den aktuellen Benutzer oder für alle Benutzer installiert ist.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-204">`Install-Module` has a **Scope** parameter that allows you to specify whether the module is installed for the current user or for all users.</span></span> <span data-ttu-id="b9fe0-205">Weitere Informationen finden Sie unter [Install-Module](xref:PowerShellGet.Install-Module).</span><span class="sxs-lookup"><span data-stu-id="b9fe0-205">For more information, see [Install-Module](xref:PowerShellGet.Install-Module).</span></span>

  <span data-ttu-id="b9fe0-206">Der benutzerspezifische **CurrentUser** -Speicherort unter Windows ist der `PowerShell\Modules` Ordner im Speicherort der **Dokumente** in Ihrem Benutzerprofil.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-206">The user-specific **CurrentUser** location on Windows is the `PowerShell\Modules` folder located in the **Documents** location in your user profile.</span></span> <span data-ttu-id="b9fe0-207">Der spezifische Pfad dieses Standorts variiert je nach Version von Windows und ob Sie die Ordner Umleitung verwenden.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-207">The specific path of that location varies by version of Windows and whether or not you are using folder redirection.</span></span> <span data-ttu-id="b9fe0-208">Microsoft onedrive kann auch den Speicherort des Ordners " **Dokumente** " ändern.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-208">Microsoft OneDrive can also change the location of your **Documents** folder.</span></span>

  <span data-ttu-id="b9fe0-209">Standardmäßig ist dieser Speicherort unter Windows 10 `$HOME\Documents\PowerShell\Modules` .</span><span class="sxs-lookup"><span data-stu-id="b9fe0-209">By default, on Windows 10, that location is `$HOME\Documents\PowerShell\Modules`.</span></span> <span data-ttu-id="b9fe0-210">Unter Linux oder Mac lautet der **CurrentUser** -Speicherort `$HOME/.local/share/powershell/Modules` .</span><span class="sxs-lookup"><span data-stu-id="b9fe0-210">On Linux or Mac, the **CurrentUser** location is `$HOME/.local/share/powershell/Modules`.</span></span>

  > [!NOTE]
  > <span data-ttu-id="b9fe0-211">Sie können den Speicherort des Ordners " **Dokumente** " mithilfe des folgenden Befehls überprüfen: `[Environment]::GetFolderPath('MyDocuments')` .</span><span class="sxs-lookup"><span data-stu-id="b9fe0-211">You can verify the location of your **Documents** folder using the following command: `[Environment]::GetFolderPath('MyDocuments')`.</span></span>

- <span data-ttu-id="b9fe0-212">Der **ALLUSERS** -Speicherort ist `$env:PROGRAMFILES\PowerShell\Modules` unter Windows.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-212">The **AllUsers** location is `$env:PROGRAMFILES\PowerShell\Modules` on Windows.</span></span> <span data-ttu-id="b9fe0-213">Unter Linux oder Mac werden die Module unter gespeichert `/usr/local/share/powershell/Modules` .</span><span class="sxs-lookup"><span data-stu-id="b9fe0-213">On Linux or Mac the modules are stored at `/usr/local/share/powershell/Modules`.</span></span>

> [!NOTE]
> <span data-ttu-id="b9fe0-214">Um Dateien im Verzeichnis hinzuzufügen oder zu ändern `$env:Windir\System32` , starten Sie PowerShell mit der Option **als Administrator ausführen** .</span><span class="sxs-lookup"><span data-stu-id="b9fe0-214">To add or change files in the `$env:Windir\System32` directory, start PowerShell with the **Run as administrator** option.</span></span>

<span data-ttu-id="b9fe0-215">Sie können die standardmäßigen Modul Speicherorte auf dem System ändern, indem Sie den Wert der **psmodulepath** -Umgebungsvariablen ändern `$Env:PSModulePath` .</span><span class="sxs-lookup"><span data-stu-id="b9fe0-215">You can change the default module locations on your system by changing the value of the **PSModulePath** environment variable, `$Env:PSModulePath`.</span></span> <span data-ttu-id="b9fe0-216">Die Umgebungsvariable **psmodulepath** wird anhand der PATH-Umgebungsvariablen modelliert und weist das gleiche Format auf.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-216">The **PSModulePath** environment variable is modeled on the Path environment variable and has the same format.</span></span>

<span data-ttu-id="b9fe0-217">Um die Standardspeicherorte für das Modul anzuzeigen, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="b9fe0-217">To view the default module locations, type:</span></span>

```powershell
$Env:PSModulePath
```

<span data-ttu-id="b9fe0-218">Um einen Standardspeicherort für das Modul hinzuzufügen, verwenden Sie das folgende Befehlsformat.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-218">To add a default module location, use the following command format.</span></span>

```powershell
$Env:PSModulePath = $Env:PSModulePath + ";<path>"
```

<span data-ttu-id="b9fe0-219">Das Semikolon ( `;` ) im Befehl trennt den neuen Pfad von dem Pfad, der in der Liste vorangestellt ist.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-219">The semi-colon (`;`) in the command separates the new path from the path that precedes it in the list.</span></span>

<span data-ttu-id="b9fe0-220">Geben Sie z. b. Folgendes ein, um das Verzeichnis hinzuzufügen `C:\ps-test\Modules` :</span><span class="sxs-lookup"><span data-stu-id="b9fe0-220">For example, to add the `C:\ps-test\Modules` directory, type:</span></span>

```powershell
$Env:PSModulePath + ";C:\ps-test\Modules"
```

<span data-ttu-id="b9fe0-221">Verwenden Sie das folgende Befehls Format, um einen standardmäßigen Modul Speicherort unter Linux oder MacOS hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="b9fe0-221">To add a default module location on Linux or MacOS, use the following command format:</span></span>

```powershell
$Env:PSModulePath += ":<path>"
```

<span data-ttu-id="b9fe0-222">Wenn Sie z. b. das `/usr/local/Fabrikam/Modules` Verzeichnis dem Wert der **psmodulepath** -Umgebungsvariablen hinzufügen möchten, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="b9fe0-222">For example, to add the `/usr/local/Fabrikam/Modules` directory to the value of the **PSModulePath** environment variable, type:</span></span>

```powershell
$Env:PSModulePath += ":/usr/local/Fabrikam/Modules"
```

<span data-ttu-id="b9fe0-223">Unter Linux oder MacOS trennt der Doppelpunkt ( `:` ) im Befehl den neuen Pfad von dem Pfad, der in der Liste vorangestellt ist.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-223">On Linux or MacOS, the colon (`:`) in the command separates the new path from the path that precedes it in the list.</span></span>

<span data-ttu-id="b9fe0-224">Wenn Sie einen Pfad zu **psmodulepath** hinzufügen, `Get-Module` enthalten-und- `Import-Module` Befehle Module in diesem Pfad.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-224">When you add a path to **PSModulePath**, `Get-Module` and `Import-Module` commands include modules in that path.</span></span>

<span data-ttu-id="b9fe0-225">Der festgelegte Wert wirkt sich nur auf die aktuelle Sitzung aus.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-225">The value that you set affects only the current session.</span></span> <span data-ttu-id="b9fe0-226">Um die Änderung dauerhaft zu machen, fügen Sie den Befehl zu Ihrem PowerShell-Profil hinzu, oder verwenden Sie System in der Systemsteuerung, um den Wert der Umgebungsvariablen **psmodulepath** in der Registrierung zu ändern.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-226">To make the change persistent, add the command to your PowerShell profile or use System in Control Panel to change the value of the **PSModulePath** environment variable in the registry.</span></span>

<span data-ttu-id="b9fe0-227">Um die Änderung dauerhaft zu machen, können Sie auch die Methode " **stenvironmentvariable** " der **System. Environment** -Klasse verwenden, um einen Pfad zur **psmodulepath** -Umgebungsvariablen hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-227">Also, to make the change persistent, you can also use the **SetEnvironmentVariable** method of the **System.Environment** class to add a Path to the **PSModulePath** environment variable.</span></span>

<span data-ttu-id="b9fe0-228">Weitere Informationen zur **psmodulepath** -Variablen finden Sie unter [about_Environment_Variables](about_Environment_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="b9fe0-228">For more information about the **PSModulePath** variable, see [about_Environment_Variables](about_Environment_Variables.md).</span></span>

## <a name="modules-and-name-conflicts"></a><span data-ttu-id="b9fe0-229">Module und Namenskonflikte</span><span class="sxs-lookup"><span data-stu-id="b9fe0-229">Modules and Name Conflicts</span></span>

<span data-ttu-id="b9fe0-230">Namenskonflikte treten auf, wenn mehrere Befehle in der Sitzung denselben Namen haben.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-230">Name conflicts occur when more than one command in the session has the same name.</span></span> <span data-ttu-id="b9fe0-231">Das Importieren eines Moduls bewirkt einen Namenskonflikt, wenn Befehle im Modul die gleichen Namen wie die Befehle oder Elemente in der Sitzung haben.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-231">Importing a module causes a name conflict when commands in the module have the same names as commands or items in the session.</span></span>

<span data-ttu-id="b9fe0-232">Namenskonflikte können dazu führen, dass Befehle ausgeblendet oder ersetzt werden.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-232">Name conflicts can result in commands being hidden or replaced.</span></span>

### <a name="hidden"></a><span data-ttu-id="b9fe0-233">Ausgeblendet</span><span class="sxs-lookup"><span data-stu-id="b9fe0-233">Hidden</span></span>

<span data-ttu-id="b9fe0-234">Ein Befehl ist ausgeblendet, wenn er nicht ausgeführt wird, wenn Sie den Befehl eingeben, Sie ihn jedoch mithilfe einer anderen Methode ausführen können, wie z. B. den Befehlsnamen mit dem Namen des Moduls oder Snap-Ins zu qualifizieren, aus dem sie stammen.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-234">A command is hidden when it is not the command that runs when you type the command name, but you can run it by using another method, such as by qualifying the command name with the name of the module or snap-in in which it originated.</span></span>

### <a name="replaced"></a><span data-ttu-id="b9fe0-235">Ersetzt</span><span class="sxs-lookup"><span data-stu-id="b9fe0-235">Replaced</span></span>

<span data-ttu-id="b9fe0-236">Ein Befehl wurde ersetzt, wenn Sie ihn nicht ausführen können, weil er durch einen Befehl mit demselben Namen überschrieben wurde.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-236">A command is replaced when you cannot run it because it has been overwritten by a command with the same name.</span></span> <span data-ttu-id="b9fe0-237">Selbst wenn Sie das Modul entfernen, das den Konflikt verursacht hat, kann ein ersetzter Befehl nicht ausgeführt werden, sofern Sie die Sitzung nicht neu starten.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-237">Even when you remove the module that caused the conflict, you cannot run a replaced command unless you restart the session.</span></span>

<span data-ttu-id="b9fe0-238">`Import-Module` kann Befehle hinzufügen, die Befehle in der aktuellen Sitzung ausblenden und ersetzen.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-238">`Import-Module` might add commands that hide and replace commands in the current session.</span></span> <span data-ttu-id="b9fe0-239">Darüber hinaus können Befehle in der Sitzung Befehle ausblenden, die das Modul hinzugefügt hat.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-239">Also, commands in your session can hide commands that the module added.</span></span>

<span data-ttu-id="b9fe0-240">Verwenden Sie den **all** -Parameter des Cmdlets, um Namenskonflikte zu erkennen `Get-Command` .</span><span class="sxs-lookup"><span data-stu-id="b9fe0-240">To detect name conflicts, use the **All** parameter of the `Get-Command` cmdlet.</span></span> <span data-ttu-id="b9fe0-241">Ab PowerShell 3,0 ruft nur die Befehle ab, die ausgeführt werden, `Get-Command` Wenn Sie den Befehlsnamen eingeben.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-241">Beginning in PowerShell 3.0, `Get-Command` gets only that commands that run when you type the command name.</span></span> <span data-ttu-id="b9fe0-242">Der **all** -Parameter ruft alle Befehle mit dem angegebenen Namen in der Sitzung ab.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-242">The **All** parameter gets all commands with the specific name in the session.</span></span>

<span data-ttu-id="b9fe0-243">Um Namenskonflikte zu vermeiden, verwenden Sie die **noClobber** -oder **prefix** -Parameter des `Import-Module` Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-243">To prevent name conflicts, use the **NoClobber** or **Prefix** parameters of the `Import-Module` cmdlet.</span></span> <span data-ttu-id="b9fe0-244">Der **prefix** -Parameter fügt den Namen importierter Befehle ein Präfix hinzu, damit Sie in der Sitzung eindeutig sind.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-244">The **Prefix** parameter adds a prefix to the names of imported commands so that they are unique in the session.</span></span> <span data-ttu-id="b9fe0-245">Der **noClobber** -Parameter importiert keine Befehle, die vorhandene Befehle in der Sitzung ausblenden oder ersetzen würden.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-245">The **NoClobber** parameter does not import any commands that would hide or replace existing commands in the session.</span></span>

<span data-ttu-id="b9fe0-246">Sie können auch die Parameter **Alias**, **Cmdlet**, **Function** und **Variable** von verwenden, `Import-Module` um nur die Befehle auszuwählen, die Sie importieren möchten, und Sie können die Befehle ausschließen, die in Ihrer Sitzung zu Namenskonflikten führen.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-246">You can also use the **Alias**, **Cmdlet**, **Function**, and **Variable** parameters of `Import-Module` to select only the commands that you want to import, and you can exclude commands that cause name conflicts in your session.</span></span>

<span data-ttu-id="b9fe0-247">Modul Autoren können Namenskonflikte mithilfe der **defaultcommandprefix** -Eigenschaft des Modul Manifests verhindern, um allen Befehlsnamen ein Standard Präfix hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-247">Module authors can prevent name conflicts by using the **DefaultCommandPrefix** property of the module manifest to add a default prefix to all command names.</span></span>
<span data-ttu-id="b9fe0-248">Der Wert des **prefix** -Parameters hat Vorrang vor dem Wert von **defaultcommandprefix**.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-248">The value of the **Prefix** parameter takes precedence over the value of **DefaultCommandPrefix**.</span></span>

<span data-ttu-id="b9fe0-249">Selbst wenn ein Befehl ausgeblendet ist, können Sie ihn durch die Qualifizierung des Befehlsnamens mit dem Namen des Moduls oder des ursprüunglichen Snap-Ins ausführen.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-249">Even if a command is hidden, you can run it by qualifying the command name with the name of the module or snap-in in which it originated.</span></span>

<span data-ttu-id="b9fe0-250">Die Regeln der PowerShell-Befehls Rangfolge bestimmen, welcher Befehl ausgeführt wird, wenn die Sitzung Befehle mit demselben Namen enthält.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-250">The PowerShell command precedence rules determine which command runs when the session includes commands with the same name.</span></span>

<span data-ttu-id="b9fe0-251">Wenn eine Sitzung z. b. eine Funktion und ein Cmdlet mit dem gleichen Namen enthält, führt PowerShell die Funktion standardmäßig aus.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-251">For example, when a session includes a function and a cmdlet with the same name, PowerShell runs the function by default.</span></span> <span data-ttu-id="b9fe0-252">Wenn die Sitzung Befehle vom gleichen Typ mit dem gleichen Namen, z. B. zwei Cmdlets mit demselben Namen enthält, wird standardmäßig der zuletzt hinzugefügte Befehl ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-252">When the session includes commands of the same type with the same name, such as two cmdlets with the same name, by default, it runs the most recently added command.</span></span>

<span data-ttu-id="b9fe0-253">Weitere Informationen, einschließlich einer Erläuterung der Rang folgen Regeln und Anweisungen zum Ausführen von ausgeblendeten Befehlen, finden Sie unter [about_Command_Precedence](about_Command_Precedence.md).</span><span class="sxs-lookup"><span data-stu-id="b9fe0-253">For more information, including an explanation of the precedence rules and instructions for running hidden commands, see [about_Command_Precedence](about_Command_Precedence.md).</span></span>

## <a name="modules-and-snap-ins"></a><span data-ttu-id="b9fe0-254">Module und Snap-Ins</span><span class="sxs-lookup"><span data-stu-id="b9fe0-254">Modules and Snap-ins</span></span>

<span data-ttu-id="b9fe0-255">Sie können Ihrer Sitzung Befehle aus Modulen und Snap-Ins hinzufügen. Module können alle Arten von Befehlen, einschließlich Cmdlets, Anbieter, Funktionen und Elemente, wie z. b. Variablen, Aliase und PowerShell-Laufwerke, hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-255">You can add commands to your session from modules and snap-ins. Modules can add all types of commands, including cmdlets, providers, and functions, and items, such as variables, aliases, and PowerShell drives.</span></span> <span data-ttu-id="b9fe0-256">Snap-Ins können nur Cmdlets und Anbieter hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-256">Snap-ins can add only cmdlets and providers.</span></span>

<span data-ttu-id="b9fe0-257">Vor dem Entfernen eines Moduls oder Snap-Ins aus der Sitzung verwenden Sie die folgenden Befehle, um zu bestimmen, welche Befehle entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-257">Before removing a module or snap-in from your session, use the following commands to determine which commands will be removed.</span></span>

<span data-ttu-id="b9fe0-258">Um die Quelle eines Cmdlets in Ihrer Sitzung zu ermitteln, verwenden Sie das folgende Befehls Format:</span><span class="sxs-lookup"><span data-stu-id="b9fe0-258">To find the source of a cmdlet in your session, use the following command format:</span></span>

```powershell
Get-Command <cmdlet-name> | Format-List -Property verb,noun,pssnapin,module
```

<span data-ttu-id="b9fe0-259">Wenn Sie z. b. die Quelle des `Get-Date` Cmdlets ermitteln möchten, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="b9fe0-259">For example, to find the source of the `Get-Date` cmdlet, type:</span></span>

```powershell
Get-Command Get-Date | Format-List -Property verb,noun,module
```

## <a name="module-related-warnings-and-errors"></a><span data-ttu-id="b9fe0-260">Modul bezogene Warnungen und Fehler</span><span class="sxs-lookup"><span data-stu-id="b9fe0-260">Module-related Warnings and Errors</span></span>

<span data-ttu-id="b9fe0-261">Die Befehle, die ein Modul exportiert, müssen die Benennungs Regeln für den PowerShell-Befehl einhalten.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-261">The commands that a module exports should follow the PowerShell command naming rules.</span></span> <span data-ttu-id="b9fe0-262">Wenn das Modul, das Sie importieren, Cmdlets oder Funktionen exportiert, die nicht genehmigte Verben in ihren Namen haben, `Import-Module` zeigt das Cmdlet die folgende Warnmeldung an.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-262">If the module that you import exports cmdlets or functions that have unapproved verbs in their names, the `Import-Module` cmdlet displays the following warning message.</span></span>

> <span data-ttu-id="b9fe0-263">Warnung: einige importierte Befehlsnamen enthalten nicht genehmigte Verben, die Sie möglicherweise weniger auffallen machen.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-263">WARNING: Some imported command names include unapproved verbs which might make them less discoverable.</span></span> <span data-ttu-id="b9fe0-264">Verwenden Sie den Verbose-Parameter für weitere Details, oder geben Sie „Get-Verb“ ein, um die Liste der zulässigen Verben anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-264">Use the Verbose parameter for more detail or type Get-Verb to see the list of approved verbs.</span></span>

<span data-ttu-id="b9fe0-265">Diese Meldung ist nur eine Warnung.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-265">This message is only a warning.</span></span> <span data-ttu-id="b9fe0-266">Es wird trotzdem das gesamte Modul einschließlich nicht konformer Befehle importiert.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-266">The complete module is still imported, including the non-conforming commands.</span></span> <span data-ttu-id="b9fe0-267">Obwohl die Meldung für Modulbenutzer angezeigt wird, sollte das Namensproblem vom Modulautor behoben werden.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-267">Although the message is displayed to module users, the naming problem should be fixed by the module author.</span></span>

<span data-ttu-id="b9fe0-268">Um die Warnmeldung zu unterdrücken, verwenden Sie den **disablenamecheck** -Parameter des `Import-Module` Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-268">To suppress the warning message, use the **DisableNameChecking** parameter of the `Import-Module` cmdlet.</span></span>

## <a name="built-in-modules-and-snap-ins"></a><span data-ttu-id="b9fe0-269">Integrierte Module und Snap-Ins</span><span class="sxs-lookup"><span data-stu-id="b9fe0-269">Built-in Modules and Snap-ins</span></span>

<span data-ttu-id="b9fe0-270">In PowerShell 2,0 und älteren Host Programmen in PowerShell 3,0 und höher werden die Kern Befehle, die mit PowerShell installiert werden, in Snap-Ins verpackt, die automatisch zu jeder PowerShell-Sitzung hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-270">In PowerShell 2.0 and in older-style host programs in PowerShell 3.0 and later, the core commands that are installed with PowerShell are packaged in snap-ins that are added automatically to every PowerShell session.</span></span>

<span data-ttu-id="b9fe0-271">Ab PowerShell 3,0 wird für Host Programme, die die `InitialSessionState.CreateDefault2` erste Sitzungs Status-API implementieren, das Microsoft. PowerShell. Core-Snap-in jeder Sitzung standardmäßig hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-271">Beginning in PowerShell 3.0, for host programs that implement the `InitialSessionState.CreateDefault2` initial session state API the Microsoft.PowerShell.Core snap-in is added to every session by default.</span></span> <span data-ttu-id="b9fe0-272">Module werden automatisch bei der ersten Verwendung geladen.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-272">Modules are loaded automatically on first-use.</span></span>

> [!NOTE]
> <span data-ttu-id="b9fe0-273">Remote Sitzungen, einschließlich Sitzungen, die mithilfe des `New-PSSession` Cmdlets gestartet werden, sind Sitzungen älterer Sitzungen, in denen die integrierten Befehle in Snap-Ins verpackt werden.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-273">Remote sessions, including sessions that are started by using the `New-PSSession` cmdlet, are older-style sessions in which the built-in commands are packaged in snap-ins.</span></span>

<span data-ttu-id="b9fe0-274">Die folgenden Module (oder Snap-Ins) werden mit PowerShell installiert.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-274">The following modules (or snap-ins) are installed with PowerShell.</span></span>

- <span data-ttu-id="b9fe0-275">CimCmdlets</span><span class="sxs-lookup"><span data-stu-id="b9fe0-275">CimCmdlets</span></span>
- <span data-ttu-id="b9fe0-276">Microsoft.PowerShell.Archive</span><span class="sxs-lookup"><span data-stu-id="b9fe0-276">Microsoft.PowerShell.Archive</span></span>
- <span data-ttu-id="b9fe0-277">Microsoft.PowerShell.Core</span><span class="sxs-lookup"><span data-stu-id="b9fe0-277">Microsoft.PowerShell.Core</span></span>
- <span data-ttu-id="b9fe0-278">Microsoft.PowerShell.Diagnostics</span><span class="sxs-lookup"><span data-stu-id="b9fe0-278">Microsoft.PowerShell.Diagnostics</span></span>
- <span data-ttu-id="b9fe0-279">Microsoft.PowerShell.Host</span><span class="sxs-lookup"><span data-stu-id="b9fe0-279">Microsoft.PowerShell.Host</span></span>
- <span data-ttu-id="b9fe0-280">Microsoft.PowerShell.Management</span><span class="sxs-lookup"><span data-stu-id="b9fe0-280">Microsoft.PowerShell.Management</span></span>
- <span data-ttu-id="b9fe0-281">Microsoft.PowerShell.Security</span><span class="sxs-lookup"><span data-stu-id="b9fe0-281">Microsoft.PowerShell.Security</span></span>
- <span data-ttu-id="b9fe0-282">Microsoft.PowerShell.Utility</span><span class="sxs-lookup"><span data-stu-id="b9fe0-282">Microsoft.PowerShell.Utility</span></span>
- <span data-ttu-id="b9fe0-283">Microsoft.WSMan.Management</span><span class="sxs-lookup"><span data-stu-id="b9fe0-283">Microsoft.WSMan.Management</span></span>
- <span data-ttu-id="b9fe0-284">PackageManagement</span><span class="sxs-lookup"><span data-stu-id="b9fe0-284">PackageManagement</span></span>
- <span data-ttu-id="b9fe0-285">PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="b9fe0-285">PowerShellGet</span></span>
- <span data-ttu-id="b9fe0-286">PSDesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="b9fe0-286">PSDesiredStateConfiguration</span></span>
- <span data-ttu-id="b9fe0-287">PSDiagnostics</span><span class="sxs-lookup"><span data-stu-id="b9fe0-287">PSDiagnostics</span></span>
- <span data-ttu-id="b9fe0-288">PSReadline</span><span class="sxs-lookup"><span data-stu-id="b9fe0-288">PSReadline</span></span>

## <a name="logging-module-events"></a><span data-ttu-id="b9fe0-289">Protokollieren von Modul Ereignissen</span><span class="sxs-lookup"><span data-stu-id="b9fe0-289">Logging Module Events</span></span>

<span data-ttu-id="b9fe0-290">Ab PowerShell 3,0 können Sie Ausführungs Ereignisse für die Cmdlets und Funktionen in PowerShell-Modulen und-Snap-Ins aufzeichnen, indem Sie die **logpipelineexecutiondetails** -Eigenschaft von Modulen und Snap-Ins auf festlegen `$True` .</span><span class="sxs-lookup"><span data-stu-id="b9fe0-290">Beginning in PowerShell 3.0, you can record execution events for the cmdlets and functions in PowerShell modules and snap-ins by setting the **LogPipelineExecutionDetails** property of modules and snap-ins to `$True`.</span></span>
<span data-ttu-id="b9fe0-291">Sie können auch eine Gruppenrichtlinie Einstellung, die Modul Protokollierung aktivieren, verwenden, um die Modul Protokollierung in allen PowerShell-Sitzungen zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-291">You can also use a Group Policy setting, Turn on Module Logging, to enable module logging in all PowerShell sessions.</span></span> <span data-ttu-id="b9fe0-292">Weitere Informationen finden Sie in den Artikeln Protokollierung und Gruppenrichtlinie.</span><span class="sxs-lookup"><span data-stu-id="b9fe0-292">For more information, see the logging and group policy articles.</span></span>

## <a name="see-also"></a><span data-ttu-id="b9fe0-293">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b9fe0-293">See Also</span></span>

[<span data-ttu-id="b9fe0-294">about_Logging_Windows</span><span class="sxs-lookup"><span data-stu-id="b9fe0-294">about_Logging_Windows</span></span>](about_Logging_Windows.md)

[<span data-ttu-id="b9fe0-295">about_Logging_Non-Windows</span><span class="sxs-lookup"><span data-stu-id="b9fe0-295">about_Logging_Non-Windows</span></span>](about_Logging_Non-Windows.md)

[<span data-ttu-id="b9fe0-296">about_Group_Policy_Settings</span><span class="sxs-lookup"><span data-stu-id="b9fe0-296">about_Group_Policy_Settings</span></span>](about_Group_Policy_Settings.md)

[<span data-ttu-id="b9fe0-297">about_Command_Precedence</span><span class="sxs-lookup"><span data-stu-id="b9fe0-297">about_Command_Precedence</span></span>](about_Command_Precedence.md)

[<span data-ttu-id="b9fe0-298">about_Group_Policy_Settings</span><span class="sxs-lookup"><span data-stu-id="b9fe0-298">about_Group_Policy_Settings</span></span>](about_Group_Policy_Settings.md)

[<span data-ttu-id="b9fe0-299">Get-Command</span><span class="sxs-lookup"><span data-stu-id="b9fe0-299">Get-Command</span></span>](xref:Microsoft.PowerShell.Core.Get-Command)

[<span data-ttu-id="b9fe0-300">Get-Help</span><span class="sxs-lookup"><span data-stu-id="b9fe0-300">Get-Help</span></span>](xref:Microsoft.PowerShell.Core.Get-Help)

[<span data-ttu-id="b9fe0-301">Get-Module</span><span class="sxs-lookup"><span data-stu-id="b9fe0-301">Get-Module</span></span>](xref:Microsoft.PowerShell.Core.Get-Module)

[<span data-ttu-id="b9fe0-302">Import-Module</span><span class="sxs-lookup"><span data-stu-id="b9fe0-302">Import-Module</span></span>](xref:Microsoft.PowerShell.Core.Import-Module)

[<span data-ttu-id="b9fe0-303">Remove-Module</span><span class="sxs-lookup"><span data-stu-id="b9fe0-303">Remove-Module</span></span>](xref:Microsoft.PowerShell.Core.Remove-Module)
