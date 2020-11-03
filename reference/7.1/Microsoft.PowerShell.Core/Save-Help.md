---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/save-help?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Save-Help
ms.openlocfilehash: f98684b4d10a9755428b4798f2f03d944e4bbb84
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93217012"
---
# <span data-ttu-id="ceeef-103">Save-Help</span><span class="sxs-lookup"><span data-stu-id="ceeef-103">Save-Help</span></span>

## <span data-ttu-id="ceeef-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="ceeef-104">SYNOPSIS</span></span>
<span data-ttu-id="ceeef-105">Lädt die neuesten Hilfedateien herunter und speichert sie in einem Dateisystemverzeichnis.</span><span class="sxs-lookup"><span data-stu-id="ceeef-105">Downloads and saves the newest help files to a file system directory.</span></span>

## <span data-ttu-id="ceeef-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ceeef-106">SYNTAX</span></span>

### <span data-ttu-id="ceeef-107">Pfad (Standard)</span><span class="sxs-lookup"><span data-stu-id="ceeef-107">Path (Default)</span></span>

```
Save-Help [-DestinationPath] <String[]> [[-Module] <PSModuleInfo[]>]
 [-FullyQualifiedModule <ModuleSpecification[]>] [[-UICulture] <CultureInfo[]>]
 [-Credential <PSCredential>] [-UseDefaultCredentials] [-Force] [-Scope <UpdateHelpScope>]
 [<CommonParameters>]
```

### <span data-ttu-id="ceeef-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="ceeef-108">LiteralPath</span></span>

```
Save-Help -LiteralPath <String[]> [[-Module] <PSModuleInfo[]>]
 [-FullyQualifiedModule <ModuleSpecification[]>] [[-UICulture] <CultureInfo[]>]
 [-Credential <PSCredential>] [-UseDefaultCredentials] [-Force] [-Scope <UpdateHelpScope>]
 [<CommonParameters>]
```

## <span data-ttu-id="ceeef-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="ceeef-109">DESCRIPTION</span></span>

<span data-ttu-id="ceeef-110">Das **Save-Help-** Cmdlet lädt die neuesten Hilfedateien für PowerShell-Module herunter und speichert Sie in einem von Ihnen angegebenen Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="ceeef-110">The **Save-Help** cmdlet downloads the newest help files for PowerShell modules and saves them to a directory that you specify.</span></span>
<span data-ttu-id="ceeef-111">Mit dieser Funktion können Sie die Hilfedateien auf Computern aktualisieren, die keinen Internetzugriff haben, und sie vereinfacht die Aktualisierung der Hilfedateien auf mehreren Computern.</span><span class="sxs-lookup"><span data-stu-id="ceeef-111">This feature lets you update the help files on computers that do not have access to the Internet, and makes it easier to update the help files on multiple computers.</span></span>

<span data-ttu-id="ceeef-112">In Windows PowerShell 3,0 funktionierte **Save-Help** nur für Module, die auf dem lokalen Computer installiert sind.</span><span class="sxs-lookup"><span data-stu-id="ceeef-112">In Windows PowerShell 3.0, **Save-Help** worked only for modules that are installed on the local computer.</span></span>
<span data-ttu-id="ceeef-113">Obwohl es möglich war, ein Modul von einem Remote Computer zu importieren oder einen Verweis auf ein **psmoduleinfo** -Objekt von einem Remote Computer mithilfe von PowerShell-Remoting abzurufen, wurde die **helpinfouri** -Eigenschaft nicht beibehalten, und **Save-Help** funktionierte nicht für die Remote Modul-Hilfe.</span><span class="sxs-lookup"><span data-stu-id="ceeef-113">Although it was possible to import a module from a remote computer, or obtain a reference to a **PSModuleInfo** object from a remote computer by using PowerShell remoting, the **HelpInfoUri** property was not preserved, and **Save-Help** would not work for remote module Help.</span></span>

<span data-ttu-id="ceeef-114">In Windows PowerShell 4,0 wird die **helpinfouri** -Eigenschaft über PowerShell-Remoting beibehalten, sodass **Save-Help** für Module funktioniert, die auf Remote Computern installiert sind.</span><span class="sxs-lookup"><span data-stu-id="ceeef-114">In Windows PowerShell 4.0, the **HelpInfoUri** property is preserved over PowerShell remoting, which enables **Save-Help** to work for modules that are installed on remote computers.</span></span>
<span data-ttu-id="ceeef-115">Es ist auch möglich, ein **psmoduleinfo** -Objekt auf einem Datenträger oder Wechselmedium zu speichern, indem Export-Clixml auf einem Computer ausgeführt wird, der nicht über Internet Zugriff verfügt, das Objekt auf einem Computer mit Internet Zugriff zu importieren und dann **Save-Help** auf dem **psmoduleinfo** -Objekt auszuführen.</span><span class="sxs-lookup"><span data-stu-id="ceeef-115">It is also possible to save a **PSModuleInfo** object to disk or removable media by running Export-Clixml on a computer that does not have Internet access, import the object on a computer that does have Internet access, and then run **Save-Help** on the **PSModuleInfo** object.</span></span>
<span data-ttu-id="ceeef-116">Die gespeicherte Hilfe kann mithilfe von Wechselmedien (z. b. einem USB-Laufwerk) auf den Remote Computer übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="ceeef-116">The saved help can be transported to the remote computer by using removable storage media, such as a USB drive.</span></span>
<span data-ttu-id="ceeef-117">Die Hilfe kann durch Ausführen von **Update-Help** auf dem Remote Computer installiert werden.</span><span class="sxs-lookup"><span data-stu-id="ceeef-117">The help can be installed on the remote computer by running **Update-Help**.</span></span>
<span data-ttu-id="ceeef-118">Dieser Prozess kann zum Installieren der Hilfe auf Computern verwendet werden, die überhaupt keinen Zugriff auf das Netzwerk haben.</span><span class="sxs-lookup"><span data-stu-id="ceeef-118">This process can be used to install help on computers that do not have any kind of network access.</span></span>

<span data-ttu-id="ceeef-119">Führen Sie zum Installieren gespeicherter Hilfedateien das Update-Help-Cmdlet aus.</span><span class="sxs-lookup"><span data-stu-id="ceeef-119">To install saved help files, run the Update-Help cmdlet.</span></span>
<span data-ttu-id="ceeef-120">Fügen Sie seinen *SourcePath* -Parameter hinzu, um den Ordner anzugeben, in dem Sie die Hilfedateien gespeichert haben.</span><span class="sxs-lookup"><span data-stu-id="ceeef-120">Add its *SourcePath* parameter to specify the folder in which you saved the Help files.</span></span>

<span data-ttu-id="ceeef-121">Ohne Parameter lädt ein **Save-Help** -Befehl die neueste Hilfe für alle Module in der Sitzung und für Module herunter, die auf dem Computer an einem in der **PSModulePath** -Umgebungsvariablen aufgeführten Speicherort installiert sind.</span><span class="sxs-lookup"><span data-stu-id="ceeef-121">Without parameters, a **Save-Help** command downloads the newest help for all modules in the session and for modules that are installed on the computer in a location listed in the **PSModulePath** environment variable.</span></span>
<span data-ttu-id="ceeef-122">Diese Aktion überspringt Module, die eine aktualisierbare Hilfe ohne Warnung nicht unterstützen.</span><span class="sxs-lookup"><span data-stu-id="ceeef-122">This action skips modules that do not support Updatable Help without warning.</span></span>

<span data-ttu-id="ceeef-123">Das **Save-Help-** Cmdlet überprüft die Version der Hilfedateien im Zielordner.</span><span class="sxs-lookup"><span data-stu-id="ceeef-123">The **Save-Help** cmdlet checks the version of any help files in the destination folder.</span></span>
<span data-ttu-id="ceeef-124">Wenn neuere Hilfedateien verfügbar sind, lädt dieses Cmdlet die neuesten Hilfedateien aus dem Internet herunter und speichert Sie anschließend im Ordner.</span><span class="sxs-lookup"><span data-stu-id="ceeef-124">If newer help files are available, this cmdlet downloads the newest help files from the Internet, and then saves them in the folder.</span></span>
<span data-ttu-id="ceeef-125">Das **Save-Help-** Cmdlet funktioniert genauso wie das Update-Help-Cmdlet, mit dem Unterschied, dass es die heruntergeladenen CAB-Dateien speichert, anstatt die Hilfedateien aus den CAB-Dateien zu extrahieren und auf dem Computer zu installieren.</span><span class="sxs-lookup"><span data-stu-id="ceeef-125">The **Save-Help** cmdlet works just like the Update-Help cmdlet, except that it saves the downloaded cabinet (.cab) files, instead of extracting the help files from the cabinet files and installing them on the computer.</span></span>

<span data-ttu-id="ceeef-126">Die gespeicherte Hilfe für jedes Modul besteht aus einer Hilfe Informationsdatei (helpinfo XML) und einer CAB-Datei für die Hilfedateien jeder Benutzeroberflächen Kultur.</span><span class="sxs-lookup"><span data-stu-id="ceeef-126">The saved help for each module consists of one help information (HelpInfo XML) file and one cabinet (.cab) file for the help files each UI culture.</span></span>
<span data-ttu-id="ceeef-127">Sie müssen die Hilfedateien nicht aus der CAB-Datei extrahieren.</span><span class="sxs-lookup"><span data-stu-id="ceeef-127">You do not have to extract the help files from the cabinet file.</span></span>
<span data-ttu-id="ceeef-128">Das **Update-Help-** Cmdlet extrahiert die Hilfedateien, überprüft den XML-Code auf Sicherheit und installiert dann die Hilfedateien und die Hilfe Informationsdatei in einem sprachspezifischen Unterordner des Modul Ordners.</span><span class="sxs-lookup"><span data-stu-id="ceeef-128">The **Update-Help** cmdlet extracts the help files, validates the XML for safety, and then installs the help files and the help information file in a language-specific subfolder of the module folder.</span></span>

<span data-ttu-id="ceeef-129">Um die Hilfedateien für Module im PowerShell-Installationsordner ($PSHome \modules) zu speichern, starten Sie PowerShell mit der Option als Administrator ausführen.</span><span class="sxs-lookup"><span data-stu-id="ceeef-129">To save the help files for modules in the PowerShell installation folder ($pshome\Modules), start PowerShell by using the Run as administrator option.</span></span>
<span data-ttu-id="ceeef-130">Sie müssen ein Mitglied der Gruppe „Administratoren“ auf dem Computer sein, um die Hilfedateien für diese Module herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="ceeef-130">You must be a member of the Administrators group on the computer to download the help files for these modules.</span></span>

<span data-ttu-id="ceeef-131">Dieses Cmdlet wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="ceeef-131">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="ceeef-132">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="ceeef-132">EXAMPLES</span></span>

### <span data-ttu-id="ceeef-133">Beispiel 1: Speichern der Hilfe für das dhcpserver-Modul</span><span class="sxs-lookup"><span data-stu-id="ceeef-133">Example 1: Save the help for the DhcpServer module</span></span>

```powershell
# Option 1: Run Invoke-Command to get the PSModuleInfo object for the remote DHCP Server module, save the PSModuleInfo object in the variable $m, and then run Save-Help.

$m = Invoke-Command -ComputerName RemoteServer -ScriptBlock { Get-Module -Name DhcpServer -ListAvailable }
Save-Help -Module $m -DestinationPath "C:\SavedHelp"


# Option 2: Open a PSSession--targeted at the remote computer that is running the DhcpServer module--to get the PSModuleInfo object for the remote module, and then run Save-Help.

$s = New-PSSession -ComputerName "RemoteServer"
$m = Get-Module -PSSession $s -Name "DhcpServer" -ListAvailable
Save-Help -Module $m -DestinationPath "C:\SavedHelp"


# Option 3: Open a CIM session--targeted at the remote computer that is running the DhcpServer module--to get the PSModuleInfo object for the remote module, and then run Save-Help.

$c = New-CimSession -ComputerName "RemoteServer"
$m = Get-Module -CimSession $c -Name "DhcpServer" -ListAvailable
Save-Help -Module $m -DestinationPath "C:\SavedHelp"
```

<span data-ttu-id="ceeef-134">Dieses Beispiel zeigt drei verschiedene Möglichkeiten, **Save-Help** zu verwenden, um die Hilfe für das **DHCPServer** -Modul von einem Client Computer mit Internet Verbindung zu speichern, ohne das **DHCPServer** -Modul oder die DHCP-Server Rolle auf dem lokalen Computer zu installieren.</span><span class="sxs-lookup"><span data-stu-id="ceeef-134">This example shows three different ways to use **Save-Help** to save the help for the **DhcpServer** module from an Internet-connected client computer, without installing the **DhcpServer** module or the DHCP Server role on the local computer.</span></span>

### <span data-ttu-id="ceeef-135">Beispiel 2: Installieren der Hilfe für das dhcpserver-Modul</span><span class="sxs-lookup"><span data-stu-id="ceeef-135">Example 2: Install help for the DhcpServer module</span></span>

```powershell
# First, run Export-CliXml to export the PSModuleInfo object to a shared folder or to removable media.

$m = Get-Module -Name "DhcpServer" -ListAvailable
Export-CliXml -Path "E:\UsbFlashDrive\DhcpModule.xml" -InputObject $m

# Next, transport the removable media to a computer that has Internet access, and then import the PSModuleInfo object with Import-CliXml. Run Save-Help to save the Help for the imported DhcpServer module PSModuleInfo object.

$deserialized_m = Import-CliXml "E:\UsbFlashDrive\DhcpModule.xml"
Save-Help -Module $deserialized_m -DestinationPath "E:\UsbFlashDrive\SavedHelp"

# Finally, transport the removable media back to the computer that does not have network access, and then install the help by running Update-Help.

Update-Help -Module DhcpServer -SourcePath "E:\UsbFlashDrive\SavedHelp"
```

<span data-ttu-id="ceeef-136">In diesem Beispiel wird gezeigt, wie die Hilfe, die Sie in Beispiel 1 für das **DHCPServer** -Modul gespeichert haben, auf einem Computer installiert wird, der nicht über Internet Zugriff verfügt.</span><span class="sxs-lookup"><span data-stu-id="ceeef-136">This example shows how to install help that you saved in Example 1 for the **DhcpServer** module on a computer that does not have Internet access.</span></span>

### <span data-ttu-id="ceeef-137">Beispiel 3: Speichern der Hilfe für alle Module</span><span class="sxs-lookup"><span data-stu-id="ceeef-137">Example 3: Save help for all modules</span></span>

```powershell
Save-Help -DestinationPath "\\Server01\FileShare01"
```

<span data-ttu-id="ceeef-138">Mit diesem Befehl werden die neuesten Hilfedateien für alle Module in der Benutzeroberflächenkultur für Windows auf den lokalen Computer heruntergeladen.</span><span class="sxs-lookup"><span data-stu-id="ceeef-138">This command downloads the newest help files for all modules in the UI culture set for Windows on the local computer.</span></span>
<span data-ttu-id="ceeef-139">Die Hilfedateien werden im \\ \\ Ordner Server01\Fileshare01 gespeichert.</span><span class="sxs-lookup"><span data-stu-id="ceeef-139">It saves the help files in the \\\\Server01\Fileshare01 folder.</span></span>

### <span data-ttu-id="ceeef-140">Beispiel 4: Speichern der Hilfe für ein Modul auf dem Computer</span><span class="sxs-lookup"><span data-stu-id="ceeef-140">Example 4: Save help for a module on the computer</span></span>

```powershell
Save-Help -Module ServerManager -DestinationPath "\\Server01\FileShare01" -Credential Domain01/Admin01
```

<span data-ttu-id="ceeef-141">Mit diesem Befehl werden die neuesten Hilfedateien für das **Server Manager** -Modul heruntergeladen und dann im \\ \\ Ordner Server01\Fileshare01 gespeichert.</span><span class="sxs-lookup"><span data-stu-id="ceeef-141">This command downloads the newest help files for the **ServerManager** module, and then saves them in the \\\\Server01\Fileshare01 folder.</span></span>

<span data-ttu-id="ceeef-142">Wenn ein Modul auf dem Computer installiert ist, können Sie den Namen des Moduls als Wert des *Module* -Parameters eingeben, auch wenn das Modul nicht in die aktuelle Sitzung importiert wird.</span><span class="sxs-lookup"><span data-stu-id="ceeef-142">When a module is installed on the computer, you can type the module name as the value of the *Module* parameter, even if the module is not imported into the current session.</span></span>

<span data-ttu-id="ceeef-143">Der Befehl verwendet den *Credential* -Parameter, um die Anmeldeinformationen eines Benutzers anzugeben, der über die Berechtigung zum Schreiben in der Dateifreigabe verfügt.</span><span class="sxs-lookup"><span data-stu-id="ceeef-143">The command uses the *Credential* parameter to supply the credentials of a user who has permission to write to the file share.</span></span>

### <span data-ttu-id="ceeef-144">Beispiel 5: Speichern der Hilfe für ein Modul auf einem anderen Computer</span><span class="sxs-lookup"><span data-stu-id="ceeef-144">Example 5: Save help for a module on a different computer</span></span>

```powershell
Invoke-Command -ComputerName Server02 {Get-Module -Name CustomSQL -ListAvailable} | Save-Help -DestinationPath \\Server01\FileShare01 -Credential Domain01\Admin01
```

<span data-ttu-id="ceeef-145">Mit diesen Befehlen werden die neuesten Hilfedateien für das **customsql** -Modul heruntergeladen und im \\ \\ Ordner Server01\Fileshare01 gespeichert.</span><span class="sxs-lookup"><span data-stu-id="ceeef-145">These commands download the newest help files for the **CustomSQL** module and save them in the \\\\Server01\Fileshare01 folder.</span></span>

<span data-ttu-id="ceeef-146">Da das **customsql** -Modul nicht auf dem Computer installiert ist, enthält die Sequenz einen Invoke-Command Befehl, mit dem das Modul Objekt für das customsql-Modul vom Server02-Computer abgerufen und dann das Modul Objekt an das **Save-Help-** Cmdlet weitergeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="ceeef-146">Because the **CustomSQL** module is not installed on the computer, the sequence includes an Invoke-Command command that gets the module object for the CustomSQL module from the Server02 computer and then pipes the module object to the **Save-Help** cmdlet.</span></span>

<span data-ttu-id="ceeef-147">Wenn ein Modul nicht auf dem Computer installiert ist, benötigt **Save-Help** das Modulobjekt, das Informationen über den Speicherort der neuesten Hilfedateien enthält.</span><span class="sxs-lookup"><span data-stu-id="ceeef-147">When a module is not installed on the computer, **Save-Help** needs the module object, which includes information about the location of the newest help files.</span></span>

### <span data-ttu-id="ceeef-148">Beispiel 6: Speichern der Hilfe für ein Modul in mehreren Sprachen</span><span class="sxs-lookup"><span data-stu-id="ceeef-148">Example 6: Save help for a module in multiple languages</span></span>

```powershell
Save-Help -Module Microsoft.PowerShell* -UICulture de-DE, en-US, fr-FR, ja-JP -DestinationPath "D:\Help"
```

<span data-ttu-id="ceeef-149">Dieser Befehl speichert die Hilfe für die PowerShell-Kernmodule in vier verschiedenen Benutzeroberflächen Kulturen.</span><span class="sxs-lookup"><span data-stu-id="ceeef-149">This command saves help for the PowerShell Core modules in four different UI cultures.</span></span>
<span data-ttu-id="ceeef-150">Die Sprachpakete für diese Gebiets Schemas müssen nicht auf dem Computer installiert werden.</span><span class="sxs-lookup"><span data-stu-id="ceeef-150">The language packs for these locales do not have to be installed on the computer.</span></span>

<span data-ttu-id="ceeef-151">Mit **Save-Help** können Hilfedateien für Module in verschiedenen Benutzeroberflächen Kulturen nur heruntergeladen werden, wenn der Modul Besitzer die übersetzten Dateien im Internet verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="ceeef-151">**Save-Help** can download help files for modules in different UI cultures only when the module owner makes the translated files available on the Internet.</span></span>

### <span data-ttu-id="ceeef-152">Beispiel 7: Speichern Sie die Hilfe mehr als einmal täglich.</span><span class="sxs-lookup"><span data-stu-id="ceeef-152">Example 7: Save help more than one time each day</span></span>

```powershell
Save-Help -Force -DestinationPath "\\Server3\AdminShare\Help"
```

<span data-ttu-id="ceeef-153">Dieser Befehl speichert die Hilfe für alle Module, die auf dem Computer installiert sind.</span><span class="sxs-lookup"><span data-stu-id="ceeef-153">This command saves help for all modules that are installed on the computer.</span></span>
<span data-ttu-id="ceeef-154">Der Befehl gibt den *Force* -Parameter an, um die Regel zu überschreiben, die verhindert, dass das **Save-Help-** Cmdlet die Hilfe mehr als einmal in jedem 24-Stunden-Zeitraum herunterlädt.</span><span class="sxs-lookup"><span data-stu-id="ceeef-154">The command specifies the *Force* parameter to override the rule that prevents the **Save-Help** cmdlet from downloading help more than once in each 24-hour period.</span></span>

<span data-ttu-id="ceeef-155">Der *Force* -Parameter überschreibt auch die 1 GB-Einschränkung und umgeht die Versions Überprüfung.</span><span class="sxs-lookup"><span data-stu-id="ceeef-155">The *Force* parameter also overrides the 1 GB restriction and circumvents version checking.</span></span>
<span data-ttu-id="ceeef-156">Daher können Sie Dateien auch dann herunterladen, wenn die Version nicht höher als die Version im Zielordner ist.</span><span class="sxs-lookup"><span data-stu-id="ceeef-156">Therefore, you can download files even if the version is not later than the version in the destination folder.</span></span>

<span data-ttu-id="ceeef-157">Der Befehl verwendet das **Save-Help-** Cmdlet zum herunterladen und Speichern der Hilfedateien im angegebenen Ordner.</span><span class="sxs-lookup"><span data-stu-id="ceeef-157">The command uses the **Save-Help** cmdlet to download and save the help files to the specified folder.</span></span>
<span data-ttu-id="ceeef-158">Der *Force* -Parameter ist erforderlich, wenn Sie einen **Save-Help-** Befehl mehrmals täglich ausführen müssen.</span><span class="sxs-lookup"><span data-stu-id="ceeef-158">The *Force* parameter is required when you have to run a **Save-Help** command more than one time each day.</span></span>

## <span data-ttu-id="ceeef-159">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ceeef-159">PARAMETERS</span></span>

### <span data-ttu-id="ceeef-160">-Credential</span><span class="sxs-lookup"><span data-stu-id="ceeef-160">-Credential</span></span>

<span data-ttu-id="ceeef-161">Gibt Benutzer Anmelde Informationen an.</span><span class="sxs-lookup"><span data-stu-id="ceeef-161">Specifies a user credential.</span></span> <span data-ttu-id="ceeef-162">Dieses Cmdlet führt den Befehl mithilfe der Anmelde Informationen eines Benutzers aus, der über die Berechtigung zum Zugreifen auf den Dateisystem Speicherort verfügt, der durch den **DestinationPath** -Parameter angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="ceeef-162">This cmdlet runs the command by using credentials of a user who has permission to access the file system location specified by the **DestinationPath** parameter.</span></span> <span data-ttu-id="ceeef-163">Dieser Parameter ist nur gültig, wenn der **DestinationPath** -Parameter oder der **literalpath** -Parameter im Befehl verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ceeef-163">This parameter is valid only when the **DestinationPath** or **LiteralPath** parameter is used in the command.</span></span>

<span data-ttu-id="ceeef-164">Mit diesem Parameter können Sie `Save-Help` Befehle ausführen, die den **DestinationPath** -Parameter auf Remote Computern verwenden.</span><span class="sxs-lookup"><span data-stu-id="ceeef-164">This parameter enables you to run `Save-Help` commands that use the **DestinationPath** parameter on remote computers.</span></span> <span data-ttu-id="ceeef-165">Durch die Angabe expliziter Anmelde Informationen können Sie den Befehl auf einem Remote Computer ausführen und auf eine Dateifreigabe auf einem dritten Computer zugreifen, ohne dass ein Zugriffs Verweigerungs Fehler aufgetreten ist oder die Verwendung der-Authentifizierung zum Delegieren von Anmelde Informationen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ceeef-165">By providing explicit credentials, you can run the command on a remote computer and access a file share on a third computer without encountering an access denied error or using CredSSP authentication to delegate credentials.</span></span>

<span data-ttu-id="ceeef-166">Geben Sie einen Benutzernamen ein, z. b. **USER01** oder **Domain01\User01** , oder geben Sie ein **PSCredential** -Objekt ein, das vom `Get-Credential` Cmdlet generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="ceeef-166">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="ceeef-167">Wenn Sie einen Benutzernamen eingeben, werden Sie zur Eingabe des Kennworts aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="ceeef-167">If you type a user name, you're prompted to enter the password.</span></span>

<span data-ttu-id="ceeef-168">Anmelde Informationen werden in einem [PSCredential](/dotnet/api/system.management.automation.pscredential) -Objekt gespeichert, und das Kennwort wird als [SecureString](/dotnet/api/system.security.securestring)gespeichert.</span><span class="sxs-lookup"><span data-stu-id="ceeef-168">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="ceeef-169">Weitere Informationen zum Schutz von **SecureString** -Daten finden Sie unter [wie sicher ist SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="ceeef-169">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ceeef-170">-DestinationPath</span><span class="sxs-lookup"><span data-stu-id="ceeef-170">-DestinationPath</span></span>

<span data-ttu-id="ceeef-171">Gibt den Pfad des Ordners an, in dem die Hilfedateien gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="ceeef-171">Specifies the path of the folder in which the help files are saved.</span></span>
<span data-ttu-id="ceeef-172">Geben Sie keinen Dateinamen und keine Dateierweiterung an.</span><span class="sxs-lookup"><span data-stu-id="ceeef-172">Do not specify a file name or file name extension.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases: Path

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ceeef-173">-Force</span><span class="sxs-lookup"><span data-stu-id="ceeef-173">-Force</span></span>

<span data-ttu-id="ceeef-174">Gibt an, dass dieses Cmdlet nicht die einmal pro Tag-Einschränkung befolgt, die Versions Überprüfung überspringt und Dateien herunterlädt, die den Grenzwert von 1 GB überschreiten.</span><span class="sxs-lookup"><span data-stu-id="ceeef-174">Indicates that this cmdlet does not follow the once-per-day limitation, skips version checking, and downloads files that exceed the 1 GB limit.</span></span>

<span data-ttu-id="ceeef-175">Ohne diesen Parameter ist der **Save-Help** -Befehl nur einmal alle 24 Stunden für jedes Modul zulässig, Downloads sind auf 1 GB an nicht komprimiertem Inhalt pro Modul beschränkt, und Hilfedateien für ein Modul werden nur installiert, wenn sie neuer sind als die Dateien auf dem Computer.</span><span class="sxs-lookup"><span data-stu-id="ceeef-175">Without this parameter, only one **Save-Help** command for each module is permitted in each 24-hour period, downloads are limited to 1 GB of uncompressed content per module, and help files for a module are installed only when they are newer than the files on the computer.</span></span>

<span data-ttu-id="ceeef-176">Der Grenzwert von einmal täglich schützt die Server, die die Hilfedateien hosten, und ermöglicht es Ihnen, Ihrem PowerShell-Profil einen **Save-Help-** Befehl hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="ceeef-176">The once-per-day limit protects the servers that host the help files, and makes it practical for you to add a **Save-Help** command to your PowerShell profile.</span></span>

<span data-ttu-id="ceeef-177">Um die Hilfe für ein Modul in mehreren Benutzeroberflächen Kulturen ohne den *Force* -Parameter zu speichern, schließen Sie alle Benutzeroberflächen Kulturen in denselben Befehl ein, z. b.: `Save-Help -Module PSScheduledJobs -UICulture en-US, fr-FR, pt-BR`</span><span class="sxs-lookup"><span data-stu-id="ceeef-177">To save help for a module in multiple UI cultures without the *Force* parameter, include all UI cultures in the same command, such as: `Save-Help -Module PSScheduledJobs -UICulture en-US, fr-FR, pt-BR`</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ceeef-178">-Fullyqualifiedmodule</span><span class="sxs-lookup"><span data-stu-id="ceeef-178">-FullyQualifiedModule</span></span>

<span data-ttu-id="ceeef-179">Gibt Module an, deren Namen in Form von modulespecification-Objekten angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="ceeef-179">Specifies modules with names that are specified in the form of ModuleSpecification objects.</span></span>
<span data-ttu-id="ceeef-180">Dies wird im Abschnitt "Hinweise" des [modulespecification-Konstruktors (Hash Tabelle)](https://msdn.microsoft.com/library/jj136290) in der MSDN Library beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ceeef-180">This is described in the Remarks section of [ModuleSpecification Constructor (Hashtable)](https://msdn.microsoft.com/library/jj136290) in the MSDN library.</span></span>
<span data-ttu-id="ceeef-181">Der *fullyqualifiedmodule* -Parameter nimmt z. b. einen Modulnamen an, der im Format @ {ModuleName = "ModuleName" angegeben ist; Moduleversion = "version_number"} oder @ {ModuleName = "ModuleName"; Moduleversion = "version_number"; GUID = "GUID"}.</span><span class="sxs-lookup"><span data-stu-id="ceeef-181">For example, the *FullyQualifiedModule* parameter accepts a module name that is specified in the format @{ModuleName = "modulename"; ModuleVersion = "version_number"} or @{ModuleName = "modulename"; ModuleVersion = "version_number"; Guid = "GUID"}.</span></span>
<span data-ttu-id="ceeef-182">**ModuleName** und **ModuleVersion** sind erforderlich, aber **Guid** ist optional.</span><span class="sxs-lookup"><span data-stu-id="ceeef-182">**ModuleName** and **ModuleVersion** are required, but **Guid** is optional.</span></span>

<span data-ttu-id="ceeef-183">Sie können den *fullyqualifiedmodule* -Parameter nicht im selben Befehl wie einen *Modul* Parameter angeben.</span><span class="sxs-lookup"><span data-stu-id="ceeef-183">You cannot specify the *FullyQualifiedModule* parameter in the same command as a *Module* parameter.</span></span>

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

### <span data-ttu-id="ceeef-184">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="ceeef-184">-LiteralPath</span></span>

<span data-ttu-id="ceeef-185">Gibt den Pfad des Ziel Ordners an.</span><span class="sxs-lookup"><span data-stu-id="ceeef-185">Specifies a path of the destination folder.</span></span>
<span data-ttu-id="ceeef-186">Im Gegensatz zum Wert des *DestinationPath* -Parameters wird der Wert des *literalpath* -Parameters genau so verwendet, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="ceeef-186">Unlike the value of the *DestinationPath* parameter, the value of the *LiteralPath* parameter is used exactly as it is typed.</span></span>
<span data-ttu-id="ceeef-187">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="ceeef-187">No characters are interpreted as wildcard characters.</span></span>
<span data-ttu-id="ceeef-188">Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="ceeef-188">If the path includes escape characters, enclose it in single quotation marks.</span></span>
<span data-ttu-id="ceeef-189">Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="ceeef-189">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ceeef-190">-Modul</span><span class="sxs-lookup"><span data-stu-id="ceeef-190">-Module</span></span>

<span data-ttu-id="ceeef-191">Gibt Module an, für die dieses Cmdlet die Hilfe herunterlädt.</span><span class="sxs-lookup"><span data-stu-id="ceeef-191">Specifies modules for which this cmdlet downloads help.</span></span>
<span data-ttu-id="ceeef-192">Geben Sie mindestens einen Modulnamen oder ein Namensmuster in eine durch Trennzeichen getrennte Liste oder in eine Datei ein, die in jeder Zeile über einen Modulnamen verfügt.</span><span class="sxs-lookup"><span data-stu-id="ceeef-192">Enter one or more module names or name patters in a comma-separated list or in a file that has one module name on each line.</span></span>
<span data-ttu-id="ceeef-193">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="ceeef-193">Wildcard characters are permitted.</span></span>
<span data-ttu-id="ceeef-194">Sie können Modul Objekte auch über das Cmdlet "Get-Module" an **Save-Help** übergeben.</span><span class="sxs-lookup"><span data-stu-id="ceeef-194">You can also pipe module objects from the Get-Module cmdlet to **Save-Help**.</span></span>

<span data-ttu-id="ceeef-195">Standardmäßig lädt **Save-Help** die Hilfe für alle Module herunter, die die aktualisierbare Hilfe unterstützen und die auf dem lokalen Computer in einem in der **PSModulePath** -Umgebungsvariablen aufgeführten Verzeichnis installiert sind.</span><span class="sxs-lookup"><span data-stu-id="ceeef-195">By default, **Save-Help** downloads help for all modules that support Updatable Help and are installed on the local computer in a location listed in the **PSModulePath** environment variable.</span></span>

<span data-ttu-id="ceeef-196">Um die Hilfe für Module zu speichern, die nicht auf dem Computer installiert sind, führen **Sie einen Get-Module-** Befehl auf einem Remote Computer aus.</span><span class="sxs-lookup"><span data-stu-id="ceeef-196">To save help for modules that are not installed on the computer, run a **Get-Module** command on a remote computer.</span></span>
<span data-ttu-id="ceeef-197">Übergeben Sie die resultierenden Modulobjekte über die Pipeline an das **Save-Help** -Cmdlet, oder senden Sie die Modulobjekte als Wert der *Module* - oder *InputObject* -Parameter.</span><span class="sxs-lookup"><span data-stu-id="ceeef-197">Then pipe the resulting module objects to the **Save-Help** cmdlet or submit the module objects as the value of the *Module* or *InputObject* parameters.</span></span>

<span data-ttu-id="ceeef-198">Wenn das angegebene Modul auf dem Computer installiert ist, können Sie den Modulnamen oder ein Modulobjekt eingeben.</span><span class="sxs-lookup"><span data-stu-id="ceeef-198">If the module that you specify is installed on the computer, you can enter the module name or a module object.</span></span>
<span data-ttu-id="ceeef-199">Wenn das Modul nicht auf dem Computer installiert ist, müssen Sie ein Modulobjekt eingeben, z. B. ein vom **Get-Module** -Cmdlet zurückgegebenes Objekt.</span><span class="sxs-lookup"><span data-stu-id="ceeef-199">If the module is not installed on the computer, you must enter a module object, such as one returned by the **Get-Module** cmdlet.</span></span>

<span data-ttu-id="ceeef-200">Der *Modul* Parameter des **Save-Help-** Cmdlets akzeptiert nicht den vollständigen Pfad einer Modul Datei oder Modul Manifest-Datei.</span><span class="sxs-lookup"><span data-stu-id="ceeef-200">The *Module* parameter of the **Save-Help** cmdlet does not accept the full path of a module file or module manifest file.</span></span>
<span data-ttu-id="ceeef-201">Um die Hilfe für ein Modul zu speichern, das sich nicht an einem **psmodulepath** -Speicherort befindet, importieren Sie das Modul in die aktuelle Sitzung, bevor Sie den **Save-Help-** Befehl ausführen.</span><span class="sxs-lookup"><span data-stu-id="ceeef-201">To save help for a module that is not in a **PSModulePath** location, import the module into the current session before you run the **Save-Help** command.</span></span>

<span data-ttu-id="ceeef-202">Der Wert "\*" (alle) versucht, die Hilfe für alle Module zu aktualisieren, die auf dem Computer installiert sind.</span><span class="sxs-lookup"><span data-stu-id="ceeef-202">A value of "\*" (all) attempts to update help for all modules that are installed on the computer.</span></span>
<span data-ttu-id="ceeef-203">Dies schließt Module ein, die die aktualisierbare Hilfe nicht unterstützen.</span><span class="sxs-lookup"><span data-stu-id="ceeef-203">This includes modules that do not support Updatable Help.</span></span>
<span data-ttu-id="ceeef-204">Dieser Wert generiert möglicherweise Fehler, wenn der Befehl Module erkennt, die die aktualisierbare Hilfe nicht unterstützen.</span><span class="sxs-lookup"><span data-stu-id="ceeef-204">This value might generate errors when the command encounters modules that do not support Updatable Help.</span></span>

```yaml
Type: System.Management.Automation.PSModuleInfo[]
Parameter Sets: (All)
Aliases: Name

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="ceeef-205">-UICulture</span><span class="sxs-lookup"><span data-stu-id="ceeef-205">-UICulture</span></span>

<span data-ttu-id="ceeef-206">Gibt Werte für die Benutzeroberflächen Kultur an, für die dieses Cmdlet aktualisierte Hilfedateien abruft.</span><span class="sxs-lookup"><span data-stu-id="ceeef-206">Specifies UI culture values for which this cmdlet gets updated help files.</span></span>
<span data-ttu-id="ceeef-207">Geben Sie einen oder mehrere Sprachcodes ein, z. b. es-es, eine Variable, die Kultur Objekte enthält, oder einen Befehl, der Kultur Objekte abruft, z. b. einen Get-Culture oder Get-UICulture Befehl.</span><span class="sxs-lookup"><span data-stu-id="ceeef-207">Enter one or more language codes, such as es-ES, a variable that contains culture objects, or a command that gets culture objects, such as a Get-Culture or Get-UICulture command.</span></span>

<span data-ttu-id="ceeef-208">Platzhalterzeichen sind nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="ceeef-208">Wildcard characters are not permitted.</span></span>
<span data-ttu-id="ceeef-209">Geben Sie keinen partiellen Sprachcode, z. b. "de", an.</span><span class="sxs-lookup"><span data-stu-id="ceeef-209">Do not specify a partial language code, such as "de".</span></span>

<span data-ttu-id="ceeef-210">Standardmäßig ruft **Save-Help** Hilfedateien in der Benutzeroberflächen Kultur ab, die für Windows oder die zugehörige Fall backkultur festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="ceeef-210">By default, **Save-Help** gets help files in the UI culture set for Windows or its fallback culture.</span></span>
<span data-ttu-id="ceeef-211">Wenn Sie den *UICulture* -Parameter angeben, sucht **Save-Help** nur nach Hilfe für die angegebene Benutzeroberflächen Kultur, nicht in einer Fall backkultur.</span><span class="sxs-lookup"><span data-stu-id="ceeef-211">If you specify the *UICulture* parameter, **Save-Help** looks for help only for the specified UI culture, not in any fallback culture.</span></span>

```yaml
Type: System.Globalization.CultureInfo[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: Current UI culture
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ceeef-212">-Usedefault-Anmelde Informationen</span><span class="sxs-lookup"><span data-stu-id="ceeef-212">-UseDefaultCredentials</span></span>

<span data-ttu-id="ceeef-213">Gibt an, dass dieses Cmdlet den Befehl, einschließlich des Webdownloads, mit den Anmelde Informationen des aktuellen Benutzers ausführt.</span><span class="sxs-lookup"><span data-stu-id="ceeef-213">Indicates that this cmdlet runs the command, including the web download, with the credentials of the current user.</span></span>
<span data-ttu-id="ceeef-214">Standardmäßig wird der Befehl ohne explizite Anmeldeinformationen ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="ceeef-214">By default, the command runs without explicit credentials.</span></span>

<span data-ttu-id="ceeef-215">Dieser Parameter gilt nur, wenn der Webdownload eine NTLM-, Negotiate- oder Kerberos-basierte Authentifizierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="ceeef-215">This parameter is effective only when the web download uses NTLM, negotiate, or Kerberos-based authentication.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ceeef-216">-Bereich</span><span class="sxs-lookup"><span data-stu-id="ceeef-216">-Scope</span></span>

<span data-ttu-id="ceeef-217">Dieser Parameter führt in diesem Cmdlet keine Aktion aus.</span><span class="sxs-lookup"><span data-stu-id="ceeef-217">This paramater does nothing in this cmdlet.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.UpdateHelpScope
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="ceeef-218">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="ceeef-218">CommonParameters</span></span>

<span data-ttu-id="ceeef-219">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="ceeef-219">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ceeef-220">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="ceeef-220">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="ceeef-221">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="ceeef-221">INPUTS</span></span>

### <span data-ttu-id="ceeef-222">System. Management. Automation. psmoduleinfo</span><span class="sxs-lookup"><span data-stu-id="ceeef-222">System.Management.Automation.PSModuleInfo</span></span>

<span data-ttu-id="ceeef-223">Sie können ein Modul Objekt aus dem **Get-Module-** Cmdlet an den *Module* -Parameter von **Save-Help** übergeben.</span><span class="sxs-lookup"><span data-stu-id="ceeef-223">You can pipe a module object from the **Get-Module** cmdlet to the *Module* parameter of **Save-Help**.</span></span>

## <span data-ttu-id="ceeef-224">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="ceeef-224">OUTPUTS</span></span>

### <span data-ttu-id="ceeef-225">Keine</span><span class="sxs-lookup"><span data-stu-id="ceeef-225">None</span></span>

<span data-ttu-id="ceeef-226">Dieses Cmdlet generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="ceeef-226">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="ceeef-227">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="ceeef-227">NOTES</span></span>

* <span data-ttu-id="ceeef-228">Um die Hilfe für Module im Ordner "$PSHome \modules" zu speichern, starten Sie PowerShell mithilfe der Option als Administrator ausführen.</span><span class="sxs-lookup"><span data-stu-id="ceeef-228">To save help for modules in the $pshome\Modules folder, start PowerShell by using the Run as administrator option.</span></span> <span data-ttu-id="ceeef-229">Nur Mitglieder der Gruppe "Administratoren" auf dem Computer können die Hilfe für Module im Ordner "$PSHome \modules" herunterladen.</span><span class="sxs-lookup"><span data-stu-id="ceeef-229">Only members of the Administrators group on the computer can download help for modules in the $pshome\Modules folder.</span></span>
* <span data-ttu-id="ceeef-230">Die gespeicherte Hilfe für jedes Modul besteht aus einer Hilfe Informationsdatei (helpinfo XML) und einer CAB-Datei für die Hilfedateien jeder Benutzeroberflächen Kultur.</span><span class="sxs-lookup"><span data-stu-id="ceeef-230">The saved help for each module consists of one help information (HelpInfo XML) file and one cabinet (.cab) file for the help files each UI culture.</span></span> <span data-ttu-id="ceeef-231">Sie müssen die Hilfedateien nicht aus der CAB-Datei extrahieren.</span><span class="sxs-lookup"><span data-stu-id="ceeef-231">You do not have to extract the help files from the cabinet file.</span></span> <span data-ttu-id="ceeef-232">Das Update-Help-Cmdlet extrahiert die Hilfedateien, überprüft den XML-Code und installiert dann die Hilfedateien und die Hilfe Informationsdatei in einem sprachspezifischen Unterordner des Modul Ordners.</span><span class="sxs-lookup"><span data-stu-id="ceeef-232">The Update-Help cmdlet extracts the help files, validates the XML, and then installs the help files and the help information file in a language-specific subfolder of the module folder.</span></span>
* <span data-ttu-id="ceeef-233">Das **Save-Help** -Cmdlet kann die Hilfe für Module speichern, die nicht auf dem Computer installiert sind.</span><span class="sxs-lookup"><span data-stu-id="ceeef-233">The **Save-Help** cmdlet can save help for modules that are not installed on the computer.</span></span> <span data-ttu-id="ceeef-234">Da jedoch Hilfedateien im Modul Ordner installiert werden, kann das **Update-Help-** Cmdlet die aktualisierte Hilfedatei nur für Module installieren, die auf dem Computer installiert sind.</span><span class="sxs-lookup"><span data-stu-id="ceeef-234">However, because help files are installed in the module folder, the **Update-Help** cmdlet can install updated help file only for modules that are installed on the computer.</span></span>
* <span data-ttu-id="ceeef-235">Wenn **Save-Help** keine aktualisierten Hilfedateien für ein Modul oder aktualisierte Hilfedateien in der angegebenen Sprache finden kann, wird es weiterhin im Hintergrund ausgeführt, ohne eine Fehlermeldung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="ceeef-235">If **Save-Help** cannot find updated help files for a module, or cannot find updated help files in the specified language, it continues silently without displaying an error message.</span></span> <span data-ttu-id="ceeef-236">Um anzuzeigen, welche Dateien durch den Befehl gespeichert wurden, geben Sie den *verbose* -Parameter an.</span><span class="sxs-lookup"><span data-stu-id="ceeef-236">To see which files were saved by the command, specify the *Verbose* parameter.</span></span>
* <span data-ttu-id="ceeef-237">Module sind die kleinste Einheit der aktualisierbaren Hilfe.</span><span class="sxs-lookup"><span data-stu-id="ceeef-237">Modules are the smallest unit of updatable help.</span></span> <span data-ttu-id="ceeef-238">Sie können die Hilfe nicht für ein bestimmtes Cmdlet speichern, sondern nur für alle Cmdlets im Modul.</span><span class="sxs-lookup"><span data-stu-id="ceeef-238">You cannot save help for a particular cmdlet, only for all cmdlets in module.</span></span> <span data-ttu-id="ceeef-239">Um das Modul zu suchen, das ein bestimmtes Cmdlet enthält, verwenden Sie die **ModuleName** -Eigenschaft in Verbindung mit dem Get-Command-Cmdlet, z. b. `(Get-Command \<cmdlet-name\>).ModuleName`</span><span class="sxs-lookup"><span data-stu-id="ceeef-239">To find the module that contains a particular cmdlet, use the **ModuleName** property together with the Get-Command cmdlet, for example, `(Get-Command \<cmdlet-name\>).ModuleName`</span></span>
* <span data-ttu-id="ceeef-240">**Save-Help** unterstützt alle Module und die PowerShell-Kern-Snap-Ins. Es werden keine anderen Snap-Ins unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ceeef-240">**Save-Help** supports all modules and the PowerShell Core snap-ins. It does not support any other snap-ins.</span></span>
* <span data-ttu-id="ceeef-241">Die Cmdlets " **Update-Help** " und " **Save-Help** " verwenden die folgenden Ports, um Hilfedateien herunterzuladen: Port 80 für http und Port 443 für HTTPS.</span><span class="sxs-lookup"><span data-stu-id="ceeef-241">The **Update-Help** and **Save-Help** cmdlets use the following ports to download help files: Port 80 for HTTP and port 443 for HTTPS.</span></span>
* <span data-ttu-id="ceeef-242">Die Cmdlets **Update-Help** und **Save-Help** werden unter Windows Preinstallation Environment (Windows PE) nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ceeef-242">The **Update-Help** and **Save-Help** cmdlets are not supported on Windows Preinstallation Environment (Windows PE).</span></span>

## <span data-ttu-id="ceeef-243">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="ceeef-243">RELATED LINKS</span></span>

[<span data-ttu-id="ceeef-244">Get-Help</span><span class="sxs-lookup"><span data-stu-id="ceeef-244">Get-Help</span></span>](Get-Help.md)

[<span data-ttu-id="ceeef-245">Get-Module</span><span class="sxs-lookup"><span data-stu-id="ceeef-245">Get-Module</span></span>](Get-Module.md)

[<span data-ttu-id="ceeef-246">Update-Help</span><span class="sxs-lookup"><span data-stu-id="ceeef-246">Update-Help</span></span>](Update-Help.md)

