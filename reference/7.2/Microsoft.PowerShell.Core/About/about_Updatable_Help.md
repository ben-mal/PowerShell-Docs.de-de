---
description: Beschreibt das aktualisierbare Hilfesystem in PowerShell.
Locale: en-US
ms.date: 08/04/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_updatable_help?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Updatable_Help
ms.openlocfilehash: d688448b5aab8ec35ab5d57b444ad9902b8e8ecd
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599450"
---
# <a name="about-updatable-help"></a><span data-ttu-id="6d64c-103">Informationen zur aktualisierbaren Hilfe</span><span class="sxs-lookup"><span data-stu-id="6d64c-103">About Updatable Help</span></span>

## <a name="short-description"></a><span data-ttu-id="6d64c-104">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6d64c-104">Short description</span></span>
<span data-ttu-id="6d64c-105">Beschreibt das aktualisierbare Hilfesystem in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6d64c-105">Describes the updatable help system in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="6d64c-106">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6d64c-106">Long description</span></span>

<span data-ttu-id="6d64c-107">PowerShell bietet verschiedene Möglichkeiten, auf die aktuellsten Hilfe Themen für PowerShell-Cmdlets und-Konzepte zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="6d64c-107">PowerShell provides several different ways to access the most up-to-date help topics for PowerShell cmdlets and concepts.</span></span>

<span data-ttu-id="6d64c-108">Das aktualisierbare Hilfesystem, das in PowerShell 3,0 eingeführt wurde, soll sicherstellen, dass Sie immer über die neuesten Hilfe Themen auf dem lokalen Computer verfügen, damit Sie Sie in der Befehlszeile lesen können.</span><span class="sxs-lookup"><span data-stu-id="6d64c-108">The Updatable Help system, introduced in PowerShell 3.0, is designed to assure that you always have the newest help topics on your local computer so that you can read them at the command line.</span></span> <span data-ttu-id="6d64c-109">Es erleichtert das herunterladen und Installieren von Hilfedateien und das Aktualisieren, wenn neuere Hilfedateien verfügbar werden.</span><span class="sxs-lookup"><span data-stu-id="6d64c-109">It makes it easy to download and install help files and to update them whenever newer help files become available.</span></span>

<span data-ttu-id="6d64c-110">Zum Bereitstellen der aktualisierten Hilfe für mehrere Computer in einem Unternehmen und für Computer, die keinen Internet Zugriff haben, können Sie mit der aktualisierbaren Hilfe Hilfedateien in ein Dateisystem Verzeichnis oder eine Dateifreigabe herunterladen und dann die Hilfedateien aus der Dateifreigabe installieren.</span><span class="sxs-lookup"><span data-stu-id="6d64c-110">To provide updated help for multiple computers in an enterprise and for computers that do not have access to the internet, Updatable Help lets you download help files to a filesystem directory or file share, and then install the help files from the file share.</span></span>

<span data-ttu-id="6d64c-111">In PowerShell 4,0 wird die **helpinfouri** -Eigenschaft über Windows PowerShell-Remoting beibehalten, wodurch die Verwendung von Modulen möglich ist, die `Save-Help` auf einem Remote Computer installiert sind, aber nicht unbedingt auf dem lokalen Computer installiert sind.</span><span class="sxs-lookup"><span data-stu-id="6d64c-111">In PowerShell 4.0, the **HelpInfoUri** property is preserved over Windows PowerShell remoting, which allows `Save-Help` to work for modules that are installed on a remote computer, but are not necessarily installed on the local computer.</span></span> <span data-ttu-id="6d64c-112">Sie können ein **psmoduleinfo** -Objekt auf einem Datenträger oder einem Wechselmedium (z. b. einem USB-Laufwerk) speichern, indem Sie `Export-Clixml` auf einem Computer ausführen, der nicht über Internet Zugriff verfügt, das **psmoduleinfo** -Objekt auf einem Computer mit Internet Zugriff importieren und dann `Save-Help` auf dem **psmoduleinfo** -Objekt ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="6d64c-112">You can save a **PSModuleInfo** object to disk or removable media (such as a USB drive) by running `Export-Clixml` on a computer that does not have internet access, importing the **PSModuleInfo** object on a computer that does have internet access, and then running `Save-Help` on the **PSModuleInfo** object.</span></span> <span data-ttu-id="6d64c-113">Die gespeicherte Hilfe kann mithilfe von Wechselmedien auf den Remote Computer und den getrennten Computer kopiert und dann durch Ausführen von installiert werden `Update-Help` .</span><span class="sxs-lookup"><span data-stu-id="6d64c-113">The saved help can be copied to the remote, disconnected computer by using removable media, and then installed by running `Update-Help`.</span></span> <span data-ttu-id="6d64c-114">Mit diesen Verbesserungen bei `Save-Help` der-Funktionalität können Sie die Hilfe auf Computern installieren, die ohne Netzwerk Zugriff sind.</span><span class="sxs-lookup"><span data-stu-id="6d64c-114">These improvements in `Save-Help` functionality let you install help on computers that are without any kind of network access.</span></span> <span data-ttu-id="6d64c-115">Ein Beispiel für die Verwendung der neuen `Save-Help` Funktionalität finden Sie unter Vorgehens [Weise beim Aktualisieren der Hilfe aus einer Dateifreigabe](#how-to-update-help-from-a-file-share) in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="6d64c-115">For an example of how to use the new `Save-Help` functionality, see [How to update help from a file share](#how-to-update-help-from-a-file-share) in this topic.</span></span>

<span data-ttu-id="6d64c-116">Die aktualisierbare Hilfe unterstützt auch den Online Zugriff auf die neuesten Hilfe Themen und die grundlegende Hilfe für Cmdlets, auch wenn keine Hilfedateien auf dem Computer vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="6d64c-116">Updatable Help also supports online access to the newest help topics and basic help for cmdlets, even when there are no help files on the computer.</span></span>

<span data-ttu-id="6d64c-117">PowerShell 3,0 enthält keine Hilfedateien.</span><span class="sxs-lookup"><span data-stu-id="6d64c-117">PowerShell 3.0 does not come with Help files.</span></span> <span data-ttu-id="6d64c-118">Sie können das Feature "aktualisierbare Hilfe" verwenden, um die Hilfedateien für alle Befehle zu installieren, die standardmäßig in PowerShell und für alle Windows-Module enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="6d64c-118">You can use the Updatable Help feature to install the help files for all of the commands that are included by default in PowerShell and for all Windows modules.</span></span>

## <a name="updatable-help-cmdlets"></a><span data-ttu-id="6d64c-119">Aktualisierbare Help-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="6d64c-119">Updatable help cmdlets</span></span>

- <span data-ttu-id="6d64c-120">`Update-Help`: Lädt die neuesten Hilfedateien aus dem Internet oder einer Dateifreigabe herunter und installiert Sie auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="6d64c-120">`Update-Help`: Downloads the newest help files from the internet or a file share, and installs them on the local computer.</span></span>

- <span data-ttu-id="6d64c-121">`Save-Help`: Lädt die neuesten Hilfedateien aus dem Internet herunter und speichert Sie in einem Dateisystem Verzeichnis oder einer Dateifreigabe.</span><span class="sxs-lookup"><span data-stu-id="6d64c-121">`Save-Help`: Downloads the newest help files from the internet and saves them in a filesystem directory or file share.</span></span> <span data-ttu-id="6d64c-122">Verwenden Sie, um die Hilfedateien auf Computern zu installieren `Update-Help` .</span><span class="sxs-lookup"><span data-stu-id="6d64c-122">To install the help files on computers, use `Update-Help`.</span></span>

- <span data-ttu-id="6d64c-123">`Get-Help`: Zeigt Hilfe Themen in der Befehlszeile an.</span><span class="sxs-lookup"><span data-stu-id="6d64c-123">`Get-Help`: Displays help topics at the command line.</span></span> <span data-ttu-id="6d64c-124">Ruft Hilfe aus den Hilfedateien auf dem Computer ab.</span><span class="sxs-lookup"><span data-stu-id="6d64c-124">Gets help from the help files on the computer.</span></span> <span data-ttu-id="6d64c-125">Zeigt die automatisch generierte Hilfe für Cmdlets und Funktionen an, die keine Hilfedateien enthalten.</span><span class="sxs-lookup"><span data-stu-id="6d64c-125">Displays auto-generated help for cmdlets and functions that do not have help files.</span></span> <span data-ttu-id="6d64c-126">Öffnet Online Hilfe Themen für Cmdlets, Funktionen, Skripts und Workflows in Ihrem standardmäßigen Internetbrowser.</span><span class="sxs-lookup"><span data-stu-id="6d64c-126">Opens online help topics for cmdlets, functions, scripts, and workflows in your default internet browser.</span></span>

## <a name="auto-generated-help-help-without-help-files"></a><span data-ttu-id="6d64c-127">Automatisch generierte Hilfe: Hilfe ohne Hilfedateien</span><span class="sxs-lookup"><span data-stu-id="6d64c-127">Auto-generated help: help without help files</span></span>

<span data-ttu-id="6d64c-128">Wenn Sie nicht über die Hilfedatei für ein Cmdlet, eine Funktion oder einen Workflow auf dem Computer verfügen, `Get-Help` zeigt das Cmdlet automatisch generierte Hilfe an und fordert Sie auf, die Hilfedateien herunterzuladen oder online zu lesen.</span><span class="sxs-lookup"><span data-stu-id="6d64c-128">If you do not have the help file for a cmdlet, function, or workflow on the computer, the `Get-Help` cmdlet displays auto-generated help and prompts you to download the help files or read them online.</span></span>

<span data-ttu-id="6d64c-129">Die automatisch generierte Hilfe umfasst Syntax und Aliase sowie Hinweise, die erläutern, wie Sie die aktualisierbaren Hilfe-Cmdlets verwenden und auf die Online Hilfe Themen zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="6d64c-129">Auto-generated help includes syntax and aliases, and remarks that explain how to use the Updatable Help cmdlets and to access the online help topics.</span></span>

<span data-ttu-id="6d64c-130">Der folgende Befehl ruft beispielsweise die grundlegende Hilfe für das `Get-Culture` Cmdlet ab.</span><span class="sxs-lookup"><span data-stu-id="6d64c-130">For example, the following command gets basic help for the `Get-Culture` cmdlet.</span></span> <span data-ttu-id="6d64c-131">Die Ausgabe zeigt die `Get-Help` Anzeige an, wenn keine Hilfedateien auf dem Computer vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="6d64c-131">The output shows the `Get-Help` display when there are no help files on the computer.</span></span>

```powershell
Get-Help Get-Culture
```

```output
NAME
    Get-Culture

SYNTAX
    Get-Culture [<CommonParameters>]

ALIASES
    None

REMARKS
    To get the latest Help content including descriptions and examples
    type: Update-Help.
```

## <a name="help-files-for-modules"></a><span data-ttu-id="6d64c-132">Hilfedateien für Module</span><span class="sxs-lookup"><span data-stu-id="6d64c-132">Help files for modules</span></span>

<span data-ttu-id="6d64c-133">Die kleinste Einheit der aktualisierbaren Hilfe ist die Hilfe für ein Modul.</span><span class="sxs-lookup"><span data-stu-id="6d64c-133">The smallest unit of Updatable Help is help for a module.</span></span> <span data-ttu-id="6d64c-134">Die Modul Hilfe enthält Hilfe für alle Cmdlets, Funktionen, Workflows, Anbieter, Skripts und Konzepte in einem Modul.</span><span class="sxs-lookup"><span data-stu-id="6d64c-134">Module help includes help for all of the cmdlets, functions, workflows, providers, scripts, and concepts in a module.</span></span> <span data-ttu-id="6d64c-135">Sie können die Hilfe für alle Module aktualisieren, die auf dem Computer installiert sind, auch wenn Sie nicht in die aktuelle Sitzung importiert werden.</span><span class="sxs-lookup"><span data-stu-id="6d64c-135">You can update help for all modules that are installed on the computer, even if they are not imported into the current session.</span></span>

<span data-ttu-id="6d64c-136">Sie können die Hilfe für das gesamte Modul aktualisieren, aber Sie können die Hilfe nicht für einzelne Cmdlets aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="6d64c-136">You can update help for the entire module, but you cannot update help for individual cmdlets.</span></span>

<span data-ttu-id="6d64c-137">Um das Modul zu suchen, das ein bestimmtes Cmdlet enthält, verwenden Sie das folgende Befehls Format:</span><span class="sxs-lookup"><span data-stu-id="6d64c-137">To find the module that contains a particular cmdlet, use the following command format:</span></span>

```powershell
(Get-Command <cmdlet-name>).ModuleName
```

<span data-ttu-id="6d64c-138">Wenn Sie z. b. das Modul suchen möchten, das das `Set-ExecutionPolicy` Cmdlet enthält, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="6d64c-138">For example, to find the module that contains the `Set-ExecutionPolicy` cmdlet, type:</span></span>

```powershell
(Get-Command Set-ExecutionPolicy).ModuleName
```

<span data-ttu-id="6d64c-139">Um die Hilfe für ein bestimmtes Modul zu aktualisieren, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="6d64c-139">To update help for a particular module, type:</span></span>

```powershell
Update-Help -Module <ModuleName>
```

<span data-ttu-id="6d64c-140">Geben Sie beispielsweise Folgendes ein, um die Hilfe für das Modul zu aktualisieren, das das Cmdlet "Set-ExecutionPolicy" enthält:</span><span class="sxs-lookup"><span data-stu-id="6d64c-140">For example, to update help for the module that contains the Set-ExecutionPolicy cmdlet, type:</span></span>

```powershell
Update-Help -Module Microsoft.PowerShell.Security
```

## <a name="permissions-for-updatable-help"></a><span data-ttu-id="6d64c-141">Berechtigungen für aktualisierbare Hilfe</span><span class="sxs-lookup"><span data-stu-id="6d64c-141">Permissions for updatable help</span></span>

<span data-ttu-id="6d64c-142">Um die Hilfe für die Module im Verzeichnis zu aktualisieren `$pshome/Modules` , müssen Sie Mitglied der Gruppe "Administratoren" auf dem Computer sein.</span><span class="sxs-lookup"><span data-stu-id="6d64c-142">To update help for the modules in the directory `$pshome/Modules`, you must be member of the Administrators group on the computer.</span></span>

<span data-ttu-id="6d64c-143">Wenn Sie kein Mitglied der Gruppe "Administratoren" sind, können Sie die Hilfe für diese Module nicht aktualisieren. Wenn Sie jedoch über Internetzugang verfügen, können Sie die Hilfe online anzeigen.</span><span class="sxs-lookup"><span data-stu-id="6d64c-143">If you are not a member of the Administrators group, you cannot update help for these modules; but if you have internet access, you can view help online.</span></span>

<span data-ttu-id="6d64c-144">Zum Aktualisieren der Hilfe für Module im Verzeichnis `$home/Documents/PowerShell/Modules` oder in den Modulen in anderen Unterverzeichnissen des `$home` Verzeichnisses sind keine speziellen Berechtigungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="6d64c-144">Updating help for modules in the directory `$home/Documents/PowerShell/Modules` or modules in other subdirectories of the `$home` directory does not require special permissions.</span></span>

<span data-ttu-id="6d64c-145">Die `Update-Help` -und- `Save-Help` Cmdlets verfügen über einen **usedefault-Anmelde** Informations Parameter, der die expliziten Anmelde Informationen des aktuellen Benutzers bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="6d64c-145">The `Update-Help` and `Save-Help` cmdlets have a **UseDefaultCredentials** parameter that provides the explicit credentials of the current user.</span></span> <span data-ttu-id="6d64c-146">Dieser Parameter ist für den Zugriff auf sichere Internet Speicherorte konzipiert.</span><span class="sxs-lookup"><span data-stu-id="6d64c-146">This parameter is designed for accessing secure internet locations.</span></span>

<span data-ttu-id="6d64c-147">Die `Update-Help` `Save-Help` Cmdlets und verfügen ebenfalls über einen **Credential** -Parameter, mit dem Sie den Befehl auf einem Remote Computer ausführen und auf eine Dateifreigabe auf einem dritten Computer zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="6d64c-147">The `Update-Help` and `Save-Help` cmdlets also have a **Credential** parameter that allows you to run the command on a remote computer and access a file share on a third computer.</span></span> <span data-ttu-id="6d64c-148">Der **Credential** -Parameter ist nur gültig, wenn Sie den SourcePath-Parameter oder den **literalpath** -Parameter von `Update-Help` und die **DestinationPath** -oder **literalpath** -Parameter von verwenden `Save-Help` .</span><span class="sxs-lookup"><span data-stu-id="6d64c-148">The **Credential** parameter is valid only when you use the SourcePath or **LiteralPath** parameters of `Update-Help` and the **DestinationPath** or **LiteralPath** parameters of `Save-Help`.</span></span>

## <a name="how-to-install-and-update-help-files"></a><span data-ttu-id="6d64c-149">Installieren und Aktualisieren von Hilfedateien</span><span class="sxs-lookup"><span data-stu-id="6d64c-149">How to install and update help files</span></span>

<span data-ttu-id="6d64c-150">Verwenden Sie das-Cmdlet, um Hilfedateien zum ersten Mal herunterzuladen und zu installieren oder um die Hilfedateien auf Ihrem Computer zu aktualisieren `Update-Help` .</span><span class="sxs-lookup"><span data-stu-id="6d64c-150">To download and install help files for the first time, or to update the help files on your computer, use the `Update-Help` cmdlet.</span></span>

<span data-ttu-id="6d64c-151">Mit dem- `Update-Help` Cmdlet werden alle hart arbeiten ausgeführt, einschließlich der folgenden Aufgaben.</span><span class="sxs-lookup"><span data-stu-id="6d64c-151">The `Update-Help` cmdlet does all of the hard work for you, including the following tasks.</span></span>

- <span data-ttu-id="6d64c-152">Bestimmt, welche Module aktualisierbare Hilfe unterstützen.</span><span class="sxs-lookup"><span data-stu-id="6d64c-152">Determines which modules support Updatable Help.</span></span>
- <span data-ttu-id="6d64c-153">Sucht den Internet Speicherort, an dem jedes Modul seine aktualisierbaren Hilfedateien speichert.</span><span class="sxs-lookup"><span data-stu-id="6d64c-153">Finds the internet location where each module stores its Updatable Help files.</span></span>
- <span data-ttu-id="6d64c-154">Vergleicht die Hilfedateien für jedes Modul auf dem Computer mit den neuesten Hilfedateien, die für die einzelnen Module verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="6d64c-154">Compares the help files for each module on your computer to the newest help files that are available for each module.</span></span>
- <span data-ttu-id="6d64c-155">Hiermit werden die neuen Dateien aus dem Internet heruntergeladen.</span><span class="sxs-lookup"><span data-stu-id="6d64c-155">Downloads the new files from the internet.</span></span>
- <span data-ttu-id="6d64c-156">Entpackt das Hilfedatei Paket.</span><span class="sxs-lookup"><span data-stu-id="6d64c-156">Unwraps the help file package.</span></span>
- <span data-ttu-id="6d64c-157">Überprüft, ob es sich bei den Dateien um gültige Hilfedateien handelt.</span><span class="sxs-lookup"><span data-stu-id="6d64c-157">Verifies that the files are valid help files.</span></span>
- <span data-ttu-id="6d64c-158">Installiert die Hilfedateien im sprachspezifischen Unterverzeichnis des Modul Verzeichnisses.</span><span class="sxs-lookup"><span data-stu-id="6d64c-158">Installs the help files in the language-specific subdirectory of the module directory.</span></span>

<span data-ttu-id="6d64c-159">Verwenden Sie das-Cmdlet, um auf die neuen Hilfe Themen zuzugreifen `Get-Help` .</span><span class="sxs-lookup"><span data-stu-id="6d64c-159">To access the new help topics, use the `Get-Help` cmdlet.</span></span> <span data-ttu-id="6d64c-160">PowerShell muss nicht neu gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="6d64c-160">You do not need to restart PowerShell.</span></span>

<span data-ttu-id="6d64c-161">Um die Hilfe für alle Module auf dem Computer zu installieren oder zu aktualisieren, der die aktualisierbare Hilfe unterstützt, geben Sie</span><span class="sxs-lookup"><span data-stu-id="6d64c-161">To install or update help for all modules on the computer that supports Updatable Help, type:</span></span>

```powershell
Update-Help
```

<span data-ttu-id="6d64c-162">Um die Hilfe für bestimmte Module zu aktualisieren, fügen Sie den **Module** -Parameter von hinzu `Update-Help` .</span><span class="sxs-lookup"><span data-stu-id="6d64c-162">To update help for particular modules, add the **Module** parameter of `Update-Help`.</span></span> <span data-ttu-id="6d64c-163">Platzhalter Zeichen sind im Modulnamen zulässig.</span><span class="sxs-lookup"><span data-stu-id="6d64c-163">Wildcard characters are permitted in the module name.</span></span>

<span data-ttu-id="6d64c-164">Wenn Sie z. b. die Hilfe für das Server Manager-Modul aktualisieren möchten, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="6d64c-164">For example, to update help for the ServerManager module, type:</span></span>

```powershell
Update-Help -Module ServerManager
```

<span data-ttu-id="6d64c-165">Ohne Parameter `Update-Help` aktualisiert die Hilfe für alle Module in der Sitzung und für alle installierten Module, die die aktualisierbare Hilfe unterstützen.</span><span class="sxs-lookup"><span data-stu-id="6d64c-165">Without parameters, `Update-Help` updates help for all modules in the session and for all installed modules that support Updatable Help.</span></span> <span data-ttu-id="6d64c-166">Module müssen in Verzeichnissen installiert werden, die im Wert der psmodulepath-Umgebungsvariablen aufgelistet sind.</span><span class="sxs-lookup"><span data-stu-id="6d64c-166">To be included, modules must be installed in directories that are listed in the value of the PSModulePath environment variable.</span></span> <span data-ttu-id="6d64c-167">Dabei handelt es sich auch um Module, die von einem Get-Help-listavailable-Befehl zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="6d64c-167">These are also modules that are returned by a "Get-Help -ListAvailable" command.</span></span>

<span data-ttu-id="6d64c-168">Wenn der Wert des **Module** -Parameters `*` (alle) lautet, versucht, die `Update-Help` Hilfe für alle installierten Module zu aktualisieren, einschließlich der Module, die die aktualisierbare Hilfe nicht unterstützen.</span><span class="sxs-lookup"><span data-stu-id="6d64c-168">If the value of the **Module** parameter is `*` (all), `Update-Help` attempts to update help for all installed modules, including modules that do not support Updatable Help.</span></span> <span data-ttu-id="6d64c-169">Dieser Befehl generiert in der Regel viele Fehler, da das Cmdlet auf Module trifft, die eine aktualisierbare Hilfe nicht unterstützen.</span><span class="sxs-lookup"><span data-stu-id="6d64c-169">This command typically generates many errors as the cmdlet encounters modules that do not support Updatable Help.</span></span>

## <a name="how-to-update-help-from-a-file-share"></a><span data-ttu-id="6d64c-170">Aktualisieren der Hilfe aus einer Dateifreigabe</span><span class="sxs-lookup"><span data-stu-id="6d64c-170">How to update help from a file share</span></span>

<span data-ttu-id="6d64c-171">Verwenden Sie das-Cmdlet, um Computer zu unterstützen, die nicht mit dem Internet verbunden sind, oder um die Aktualisierung von Hilfe in einem Unternehmen zu steuern oder zu optimieren `Save-Help` .</span><span class="sxs-lookup"><span data-stu-id="6d64c-171">To support computers that are not connected to the internet, or to control or streamline help updating in an enterprise, use the `Save-Help` cmdlet.</span></span> <span data-ttu-id="6d64c-172">Das `Save-Help` Cmdlet lädt Hilfedateien aus dem Internet herunter und speichert Sie in einem Dateisystem Verzeichnis, das Sie angeben.</span><span class="sxs-lookup"><span data-stu-id="6d64c-172">The `Save-Help` cmdlet downloads help files from the internet and saves them in a filesystem directory that you specify.</span></span>

<span data-ttu-id="6d64c-173">`Save-Help` Vergleicht die Hilfedateien im angegebenen Verzeichnis mit den neuesten Hilfedateien, die für die einzelnen Module verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="6d64c-173">`Save-Help` compares the help files in the specified directory to the newest help files that are available for each module.</span></span> <span data-ttu-id="6d64c-174">Wenn das Verzeichnis keine Hilfedateien enthält oder neuere Hilfedateien für das Modul verfügbar sind, `Save-Help` lädt das Cmdlet die neuen Dateien aus dem Internet herunter.</span><span class="sxs-lookup"><span data-stu-id="6d64c-174">If the directory has no help files or newer help files are available for the module, the `Save-Help` cmdlet downloads the new files from the internet.</span></span> <span data-ttu-id="6d64c-175">Die Hilfedateien werden jedoch nicht entpackt oder installiert.</span><span class="sxs-lookup"><span data-stu-id="6d64c-175">However, it does not unwrap or install the help files.</span></span>

<span data-ttu-id="6d64c-176">Verwenden Sie den **SourcePath** -Parameter des Cmdlets, um die Hilfedateien auf einem Computer aus Hilfedateien zu installieren oder zu aktualisieren, die in einem Dateisystem Verzeichnis gespeichert wurden `Update-Help` .</span><span class="sxs-lookup"><span data-stu-id="6d64c-176">To install or update the help files on a computer from help files that were saved to a filesystem directory, use the **SourcePath** parameter of the `Update-Help` cmdlet.</span></span> <span data-ttu-id="6d64c-177">Das `Update-Help` Cmdlet identifiziert die neuesten Hilfedateien, entpackt und überprüft Sie und installiert Sie in den sprachspezifischen Unterverzeichnissen der Modul Verzeichnisse.</span><span class="sxs-lookup"><span data-stu-id="6d64c-177">The `Update-Help` cmdlet identifies the newest help files, unwraps and validates them, and installs them in the language-specific subdirectories of the module directories.</span></span>

<span data-ttu-id="6d64c-178">Wenn Sie z. b. die Hilfe für alle installierten Module im Verzeichnis speichern möchten, geben Sie Folgendes ein `\\Server\Share` :</span><span class="sxs-lookup"><span data-stu-id="6d64c-178">For example, to save help for all installed modules to the `\\Server\Share` directory, type:</span></span>

```powershell
Save-Help -DestinationPath \\Server\Share
```

<span data-ttu-id="6d64c-179">Um die Hilfe aus dem Verzeichnis zu aktualisieren, geben Sie Folgendes ein `\\Server\Share` :</span><span class="sxs-lookup"><span data-stu-id="6d64c-179">Then, to update help from the `\\Server\Share` directory, type:</span></span>

```powershell
Update-Help -SourcePath \\Server\Share
```

<span data-ttu-id="6d64c-180">In den folgenden Beispielen wird die Verwendung von veranschaulicht `Save-Help` , um die Hilfe für Module zu speichern, die nicht auf dem lokalen Computer installiert sind.</span><span class="sxs-lookup"><span data-stu-id="6d64c-180">The following examples show the use of `Save-Help` to save help for modules that are not installed on the local computer.</span></span> <span data-ttu-id="6d64c-181">In diesem Beispiel führt der Administrator `Save-Help` aus, um die Hilfe für das dhcpserver-Modul von einem Client Computer mit Internetverbindung zu speichern, ohne das dhcpserver-Modul oder die DHCP-Server Rolle auf dem lokalen Computer zu installieren.</span><span class="sxs-lookup"><span data-stu-id="6d64c-181">In this example, the administrator runs `Save-Help` to save the help for the DhcpServer module from an internet-connected client computer, without installing the DhcpServer module or DHCP Server role on the local computer.</span></span>

<span data-ttu-id="6d64c-182">Option 1: führen Sie `Invoke-Command` aus, um das **psmoduleinfo** -Objekt für das Remote Modul abzurufen, speichern Sie es in einer Variablen, `$m` und führen Sie dann das `Save-Help` **psmoduleinfo** -Objekt aus, indem Sie die Variable `$m` als Modulnamen angeben.</span><span class="sxs-lookup"><span data-stu-id="6d64c-182">Option 1: Run `Invoke-Command` to get the **PSModuleInfo** object for the remote module, save it in a variable, `$m`, and then run `Save-Help` on the **PSModuleInfo** object by specifying the variable `$m` as the module name.</span></span>

```powershell
$m = Invoke-Command -ComputerName RemoteServer -ScriptBlock
{ Get-Module -Name DhcpServer -ListAvailable }
Save-Help -Module $m -DestinationPath C:\SavedHelp
```

<span data-ttu-id="6d64c-183">Option 2: Öffnen Sie eine PSSession für den Computer, auf dem das DHCP-Server Modul ausgeführt wird, um das **psmoduleinfo** -Objekt für das Modul abzurufen, speichern Sie es in einer Variablen `$m` , und führen Sie dann `Save-Help` für das Objekt aus, das in der Variablen gespeichert ist `$m` .</span><span class="sxs-lookup"><span data-stu-id="6d64c-183">Option 2: Open a PSSession targeted at the computer that is running the DHCP Server module, to get the **PSModuleInfo** object for the module, save it in a variable `$m`, and then run `Save-Help` on the object that is saved in the `$m` variable.</span></span>

```powershell
$s = New-PSSession -ComputerName RemoteServer
$m = Get-Module -PSSession $s -Name DhcpServer -ListAvailable
Save-Help -Module $m -DestinationPath C:\SavedHelp
```

<span data-ttu-id="6d64c-184">Option 3: Öffnen Sie eine CIM-Sitzung, die auf den Computer ausgerichtet ist, auf dem das DHCP-Server Modul ausgeführt wird, um das **psmoduleinfo** -Objekt für das Modul abzurufen, speichern Sie es in einer Variablen `$m` , und führen Sie dann `Save-Help` für das in der Variablen gespeicherte Objekt aus `$m` .</span><span class="sxs-lookup"><span data-stu-id="6d64c-184">Option 3: Open a CIM session, targeted at the computer that is running the DHCP Server module, to get the **PSModuleInfo** object for the module, save it in a variable `$m`, and then run `Save-Help` on the object that is saved in the `$m` variable.</span></span>

```powershell
$c = New-CimSession -ComputerName RemoteServer
$m = Get-Module -CimSession $c -Name DhcpServer -ListAvailable
Save-Help -Module $m -DestinationPath C:\SavedHelp
```

<span data-ttu-id="6d64c-185">Im folgenden Beispiel installiert der Administrator die Hilfe für das DHCP-Server Modul auf einem Computer, der keinen Netzwerk Zugriff hat.</span><span class="sxs-lookup"><span data-stu-id="6d64c-185">In the following example, the administrator installs help for the DHCP Server module on a computer that does not have network access.</span></span>

<span data-ttu-id="6d64c-186">Führen Sie zuerst aus, `Export-Clixml` um das **psmoduleinfo** -Objekt in einen freigegebenen Ordner oder ein Wechselmedium zu exportieren.</span><span class="sxs-lookup"><span data-stu-id="6d64c-186">First, run `Export-Clixml` to export the **PSModuleInfo** object to a shared folder or to removable media.</span></span>

```powershell
$m = Get-Module -Name DhcpServer -ListAvailable
Export-Clixml -Path E:\UsbFlashDrive\DhcpModule.xml -InputObject $m
```

<span data-ttu-id="6d64c-187">Als nächstes transportieren Sie das Wechselmedium auf einen Computer, der über Internet Zugriff verfügt, und importieren dann das **psmoduleinfo** -Objekt mit `Import-Clixml` .</span><span class="sxs-lookup"><span data-stu-id="6d64c-187">Next, transport the removable media to a computer that has internet access, and then import the **PSModuleInfo** object with `Import-Clixml`.</span></span> <span data-ttu-id="6d64c-188">Führen `Save-Help` Sie aus, um die Hilfe für das importierte dhcpserver-Modul **psmoduleinfo** -Objekt zu speichern.</span><span class="sxs-lookup"><span data-stu-id="6d64c-188">Run `Save-Help` to save the Help for the imported DhcpServer module **PSModuleInfo** object.</span></span>

```powershell
$deserialized_m = Import-Clixml E:\UsbFlashDrive\DhcpModule.xml
Save-Help -Module $deserialized_m -DestinationPath E:\UsbFlashDrive\SavedHelp
```

<span data-ttu-id="6d64c-189">Transportieren Sie schließlich das Wechselmedium zurück an den Computer, der keinen Netzwerk Zugriff hat, und installieren Sie die Hilfe, indem Sie Ausführen `Update-Help` .</span><span class="sxs-lookup"><span data-stu-id="6d64c-189">Finally, transport the removable media back to the computer that does not have network access, and then install the help by running `Update-Help`.</span></span>

```powershell
Update-Help -Module DhcpServer -SourcePath E:\UsbFlashDrive\SavedHelp
```

<span data-ttu-id="6d64c-190">Ohne Parameter `Save-Help` lädt die Hilfe für alle Module in der Sitzung und für alle installierten Module herunter, die die aktualisierbare Hilfe unterstützen.</span><span class="sxs-lookup"><span data-stu-id="6d64c-190">Without parameters, `Save-Help` downloads help for all modules in the session and for all installed modules that support Updatable Help.</span></span> <span data-ttu-id="6d64c-191">Module müssen auf `$env:PSModulePath` dem lokalen Computer oder auf einem Remote Computer, für den Sie die Hilfe speichern möchten, in Verzeichnissen installiert werden, die im Wert der Umgebungsvariablen aufgelistet sind.</span><span class="sxs-lookup"><span data-stu-id="6d64c-191">To be included, modules must be installed in directories that are listed in the value of the `$env:PSModulePath` environment variable, on either the local computer or on a remote computer for which you want to save help.</span></span> <span data-ttu-id="6d64c-192">Dies sind auch Module, die durch Ausführen eines-Befehls zurückgegeben werden `Get-Help -ListAvailable` .</span><span class="sxs-lookup"><span data-stu-id="6d64c-192">These are also modules that are returned by running a `Get-Help -ListAvailable` command.</span></span>

## <a name="how-to-update-help-files-in-different-languages"></a><span data-ttu-id="6d64c-193">Aktualisieren von Hilfedateien in verschiedenen Sprachen</span><span class="sxs-lookup"><span data-stu-id="6d64c-193">How to update help files in different languages</span></span>

<span data-ttu-id="6d64c-194">Standardmäßig laden die `Update-Help` -und- `Save-Help` Cmdlets die-Hilfe in die Benutzeroberflächen Kultur und-Sprache herunter, die für Windows auf dem lokalen Computer festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="6d64c-194">By default, the `Update-Help` and `Save-Help` cmdlets download help in the UI culture and language that is set for Windows on the local computer.</span></span> <span data-ttu-id="6d64c-195">, Wenn Hilfedateien für die angegebenen Module in der lokalen Benutzeroberflächen Kultur nicht verfügbar sind, `Update-Help` und `Save-Help` verwenden Sie die Windows-Regeln für die Fall Back Regel, um die beste unterstützte Sprache zu finden.</span><span class="sxs-lookup"><span data-stu-id="6d64c-195">If help files for the specified modules are not available in the local UI culture, `Update-Help` and `Save-Help` use the Windows language fallback rules to find the best supported language.</span></span>

<span data-ttu-id="6d64c-196">Sie können jedoch die **UICulture** -Parameter der `Update-Help` -und- `Save-Help` Cmdlets verwenden, um Hilfedateien in alle Benutzeroberflächen Kulturen herunterzuladen und zu installieren, in denen Sie verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="6d64c-196">However, you can use the **UICulture** parameters of the `Update-Help` and `Save-Help` cmdlets to download and install help files in any UI cultures in which they are available.</span></span>

<span data-ttu-id="6d64c-197">Um beispielsweise die neuesten Hilfedateien für alle Module in der Sitzung in Japanisch (ja-JP) und Französisch (fr-FR) zu speichern, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="6d64c-197">For example, to save the newest help files for all modules on the session in Japanese (Ja-jp) and French (fr-FR), type:</span></span>

```powershell
Save-Help -Path \Server\Share -UICulture ja-jp, fr-fr
```

<span data-ttu-id="6d64c-198">Wenn Hilfedateien für die Module in den von Ihnen angegebenen Sprachen nicht verfügbar sind, `Update-Help` geben die-und- `Save-Help` Cmdlets eine Fehlermeldung zurück, in der die Sprachen aufgelistet sind, in denen die Hilfe für die einzelnen Module verfügbar ist, sodass Sie die Alternative auswählen können, die Ihren Anforderungen am besten entspricht.</span><span class="sxs-lookup"><span data-stu-id="6d64c-198">If help files for the modules are not available in the languages that you specified, the `Update-Help` and `Save-Help` cmdlets return an error message that lists the languages in which help for each module is available so you can choose the alternative that best meets your needs.</span></span>

> [!NOTE]
> <span data-ttu-id="6d64c-199">Aktuell werden aktualisierbare Hilfe Inhalte nur in englischer Sprache (en-US) veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="6d64c-199">Currently, Updateable Help content is only published in English (en-US).</span></span> <span data-ttu-id="6d64c-200">Auf einigen nicht-Windows-Systemen müssen Sie den **UICulture** -Parameter verwenden, um den Inhalt explizit anzufordern `en-US` .</span><span class="sxs-lookup"><span data-stu-id="6d64c-200">On some non-Windows systems you must use the **UICulture** parameter to explicitly request the `en-US` content.</span></span>

## <a name="how-to-use-online-help"></a><span data-ttu-id="6d64c-201">Verwenden der Online Hilfe</span><span class="sxs-lookup"><span data-stu-id="6d64c-201">How to use online help</span></span>

<span data-ttu-id="6d64c-202">Wenn Sie die Hilfedateien auf dem lokalen Computer nicht aktualisieren können, können Sie die neuesten Hilfedateien weiterhin online erhalten.</span><span class="sxs-lookup"><span data-stu-id="6d64c-202">If you cannot or choose not to update the help files on your local computer, you can still get the newest help files online.</span></span>

<span data-ttu-id="6d64c-203">Verwenden Sie zum Öffnen des Online Hilfe Themas für ein beliebiges Cmdlet oder eine Funktion den **Online-** Parameter des `Get-Help` Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="6d64c-203">To open the online help topic for any cmdlet or function, use the **Online** parameter of the `Get-Help` cmdlet.</span></span>

<span data-ttu-id="6d64c-204">Der folgende Befehl öffnet z. b. das Online Hilfethema für das `Get-Job` Cmdlet in Ihrem Standard Internetbrowser:</span><span class="sxs-lookup"><span data-stu-id="6d64c-204">For example, the following command opens the online help topic for the `Get-Job` cmdlet in your default internet browser:</span></span>

```powershell
Get-Help Get-Job -Online
```

<span data-ttu-id="6d64c-205">Um Online Hilfe für ein Skript zu erhalten, verwenden Sie den **Online-** Parameter und den vollständigen Pfad zum Skript.</span><span class="sxs-lookup"><span data-stu-id="6d64c-205">To get online help for a script, use the **Online** parameter and the full path to the script.</span></span>

<span data-ttu-id="6d64c-206">Der **Online-** Parameter funktioniert nicht mit Informationen zu Themen.</span><span class="sxs-lookup"><span data-stu-id="6d64c-206">The **Online** parameter does not work with About topics.</span></span> <span data-ttu-id="6d64c-207">Informationen zu den Themen zu PowerShell, einschließlich der Hilfe Themen zur PowerShell-Sprache, finden Sie unter [PowerShell about topics](about.md).</span><span class="sxs-lookup"><span data-stu-id="6d64c-207">To see the about topics for PowerShell, including help topics about the PowerShell language, see [PowerShell About Topics](about.md).</span></span>

## <a name="how-to-minimize-or-prevent-internet-downloads"></a><span data-ttu-id="6d64c-208">Minimieren oder verhindern von Internet Downloads</span><span class="sxs-lookup"><span data-stu-id="6d64c-208">How to minimize or prevent internet downloads</span></span>

<span data-ttu-id="6d64c-209">Verwenden Sie das-Cmdlet, um Internet Downloads zu minimieren und Benutzern, die nicht mit dem Internet verbunden sind, eine aktualisierbare Hilfe zu bieten `Save-Help` .</span><span class="sxs-lookup"><span data-stu-id="6d64c-209">To minimize internet downloads and provide Updatable Help to users who are not connected to the internet, use the `Save-Help` cmdlet.</span></span> <span data-ttu-id="6d64c-210">Laden Sie die Hilfe aus dem Internet herunter, und speichern Sie Sie auf einer Netzwerkfreigabe.</span><span class="sxs-lookup"><span data-stu-id="6d64c-210">Download help from the internet and save it to a network share.</span></span> <span data-ttu-id="6d64c-211">Erstellen Sie dann eine Gruppenrichtlinie Einstellung oder einen geplanten Auftrag, der `Update-Help` auf allen Computern einen Befehl ausführt.</span><span class="sxs-lookup"><span data-stu-id="6d64c-211">Then, create a Group Policy setting or scheduled job that runs an `Update-Help` command on all computers.</span></span> <span data-ttu-id="6d64c-212">Legen Sie den Wert des **SourcePath** -Parameters des `Update-Help` Cmdlets auf die Netzwerkfreigabe fest.</span><span class="sxs-lookup"><span data-stu-id="6d64c-212">Set the value of the **SourcePath** parameter of the `Update-Help` cmdlet to the network share.</span></span>

<span data-ttu-id="6d64c-213">Um zu verhindern, dass Benutzer, die über Internet Zugriff verfügen, eine aktualisierbare Hilfe aus dem Internet herunterladen, verwenden Sie die Einstellung **Standard Quellpfad für Update-Hilfe Gruppenrichtlinie festlegen** .</span><span class="sxs-lookup"><span data-stu-id="6d64c-213">To prevent users who have internet access from downloading Updatable Help from the internet, use the **Set the default source path for Update-Help** Group Policy setting.</span></span>

<span data-ttu-id="6d64c-214">Diese Gruppenrichtlinie Einstellung fügt implizit den **SourcePath** -Parameter, dem Dateisystem Speicherort, den Sie angeben, für jeden `Update-Help` Befehl auf allen betroffenen Computern hinzu.</span><span class="sxs-lookup"><span data-stu-id="6d64c-214">This Group Policy setting implicitly adds the **SourcePath** parameter, with the filesystem location that you specify, to every `Update-Help` command on every affected computer.</span></span> <span data-ttu-id="6d64c-215">Benutzer können den **SourcePath** -Parameter explizit verwenden, um einen anderen Dateisystem Speicherort anzugeben, Sie können den **SourcePath** -Parameter jedoch nicht ausschließen und die Hilfe aus dem Internet herunterladen.</span><span class="sxs-lookup"><span data-stu-id="6d64c-215">Users can use the **SourcePath** parameter explicitly to specify a different filesystem location, but they cannot exclude the **SourcePath** parameter and download help from the internet.</span></span>

> [!NOTE]
> <span data-ttu-id="6d64c-216">Die Gruppenrichtlinien Einstellung **Standard Quellpfad für Update-Hilfe festlegen** wird unter **Computer Konfiguration** und **Benutzerkonfiguration** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6d64c-216">The **Set the default source path for Update-Help** group policy setting appears under **Computer Configuration** and **User Configuration**.</span></span> <span data-ttu-id="6d64c-217">Allerdings ist nur die Richtlinien Einstellung unter **Computer Konfiguration** wirksam.</span><span class="sxs-lookup"><span data-stu-id="6d64c-217">However, only the policy setting under **Computer Configuration** is effective.</span></span> <span data-ttu-id="6d64c-218">Die Richtlinien Einstellung unter **Benutzerkonfiguration** wird ignoriert.</span><span class="sxs-lookup"><span data-stu-id="6d64c-218">The policy setting under **User Configuration** is ignored.</span></span>

<span data-ttu-id="6d64c-219">Weitere Informationen finden Sie unter [about_Group_Policy_Settings](about_Group_Policy_Settings.md).</span><span class="sxs-lookup"><span data-stu-id="6d64c-219">For more information, see [about_Group_Policy_Settings](about_Group_Policy_Settings.md).</span></span>

## <a name="how-to-update-help-for-non-standard-modules"></a><span data-ttu-id="6d64c-220">Aktualisieren der Hilfe für nicht standardmäßige Module</span><span class="sxs-lookup"><span data-stu-id="6d64c-220">How to update help for non-standard modules</span></span>

<span data-ttu-id="6d64c-221">Um die Hilfe für ein Modul zu aktualisieren oder zu speichern, das nicht durch den **listavailable** -Parameter des `Get-Module` Cmdlets zurückgegeben wird, importieren Sie das Modul in die aktuelle Sitzung, bevor Sie einen- `Update-Help` Befehl oder- `Save-Help` Befehl ausführen.</span><span class="sxs-lookup"><span data-stu-id="6d64c-221">To update or save help for a module that is not returned by the **ListAvailable** parameter of the `Get-Module` cmdlet, import the module into the current session before running an `Update-Help` or `Save-Help` command.</span></span> <span data-ttu-id="6d64c-222">Importieren Sie das Modul vor dem Ausführen des Befehls auf einem Remote Computer `Save-Help` in die aktuelle Sitzung bzw `Invoke-Command` . den Skriptblock, der mit dem Remote Computer verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="6d64c-222">On a remote computer, before running the `Save-Help` command, import the module into the current Session, or `Invoke-Command` script block, that is connected to the remote computer.</span></span>

<span data-ttu-id="6d64c-223">Wenn das Modul in der aktuellen Sitzung ausgeführt wird, führen `Update-Help` `Save-Help` Sie die Cmdlets oder ohne Parameter aus, oder verwenden Sie den **Module** -Parameter, um den Modulnamen anzugeben.</span><span class="sxs-lookup"><span data-stu-id="6d64c-223">When the module is in the current session, run the `Update-Help` or `Save-Help` cmdlets without parameters, or use the **Module** parameter to specify the module name.</span></span>

<span data-ttu-id="6d64c-224">Die **Modul** Parameter der `Update-Help` -und- `Save-Help` Cmdlets akzeptieren nur einen Modulnamen.</span><span class="sxs-lookup"><span data-stu-id="6d64c-224">The **Module** parameters of the `Update-Help` and `Save-Help` cmdlets accept only a module name.</span></span> <span data-ttu-id="6d64c-225">Sie akzeptieren nicht den Pfad zu einer Modul Datei.</span><span class="sxs-lookup"><span data-stu-id="6d64c-225">They do not accept the path to a module file.</span></span>

<span data-ttu-id="6d64c-226">Verwenden Sie dieses Verfahren, um die Hilfe für alle Module zu aktualisieren oder zu speichern, die nicht durch den **listavailable** -Parameter des `Get-Module` Cmdlets zurückgegeben werden. beispielsweise ein Modul, das an einem Speicherort installiert ist, der nicht in der `$env:PSModulePath` Umgebungsvariablen aufgeführt ist, oder ein Modul, das nicht wohl geformt ist (das Modul Verzeichnis enthält nicht mindestens eine Datei, deren basename mit dem Verzeichnisnamen identisch ist).</span><span class="sxs-lookup"><span data-stu-id="6d64c-226">Use this technique to update or save help for any module that is not returned by the **ListAvailable** parameter of the `Get-Module` cmdlet, such as a module that is installed in a location that is not listed in the `$env:PSModulePath` environment variable, or a module that is not well-formed (the module directory does not contain at least one file whose basename is the same as the directory name).</span></span>

## <a name="how-to-support-updatable-help"></a><span data-ttu-id="6d64c-227">So unterstützen Sie die aktualisierbare Hilfe</span><span class="sxs-lookup"><span data-stu-id="6d64c-227">How to support updatable help</span></span>

<span data-ttu-id="6d64c-228">Wenn Sie ein Modul erstellen, können Sie die Online Hilfe und die aktualisierbare Hilfe für Ihre Module unterstützen.</span><span class="sxs-lookup"><span data-stu-id="6d64c-228">If you author a module, you can support online help and Updatable Help for your modules.</span></span> <span data-ttu-id="6d64c-229">Weitere Informationen finden Sie [unter unterstützen der aktualisierbaren Hilfe](/powershell/scripting/developer/help/supporting-updatable-help) und [unterstützen der Online Hilfe](/powershell/scripting/developer/module/supporting-online-help) in der Microsoft-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="6d64c-229">For more information, see [Supporting Updatable Help](/powershell/scripting/developer/help/supporting-updatable-help) and [Supporting Online Help](/powershell/scripting/developer/module/supporting-online-help) in the Microsoft Docs.</span></span>

<span data-ttu-id="6d64c-230">Aktualisierbare Hilfe ist für PowerShell-Snap-Ins oder Kommentar basierte Hilfe nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="6d64c-230">Updatable help not available for PowerShell snap-ins or comment-based help.</span></span>

## <a name="remarks"></a><span data-ttu-id="6d64c-231">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="6d64c-231">Remarks</span></span>

<span data-ttu-id="6d64c-232">Die `Update-Help` `Save-Help` Cmdlets und werden auf Windows Preinstallation Environment (Windows PE) nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="6d64c-232">The `Update-Help` and `Save-Help` cmdlets are not supported on Windows Preinstallation Environment (Windows PE).</span></span>

## <a name="see-also"></a><span data-ttu-id="6d64c-233">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6d64c-233">See also</span></span>

[<span data-ttu-id="6d64c-234">Get-Help</span><span class="sxs-lookup"><span data-stu-id="6d64c-234">Get-Help</span></span>](xref:Microsoft.PowerShell.Core.Get-Help)

[<span data-ttu-id="6d64c-235">Save-Help</span><span class="sxs-lookup"><span data-stu-id="6d64c-235">Save-Help</span></span>](xref:Microsoft.PowerShell.Core.Save-Help)

[<span data-ttu-id="6d64c-236">Update-Help</span><span class="sxs-lookup"><span data-stu-id="6d64c-236">Update-Help</span></span>](xref:Microsoft.PowerShell.Core.Update-Help)
