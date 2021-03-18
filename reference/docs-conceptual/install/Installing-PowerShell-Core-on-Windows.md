---
title: Installieren von PowerShell unter Windows
description: Informationen zur Installation von PowerShell unter Windows
ms.date: 02/02/2021
ms.openlocfilehash: bd3643c1ca6beb60a8727478a1ae612dcb34c7fb
ms.sourcegitcommit: 080c8b05a1242348c365fe1684457e873325f11e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2021
ms.locfileid: "103483435"
---
# <a name="installing-powershell-on-windows"></a><span data-ttu-id="afbb3-103">Installieren von PowerShell unter Windows</span><span class="sxs-lookup"><span data-stu-id="afbb3-103">Installing PowerShell on Windows</span></span>

<span data-ttu-id="afbb3-104">Es gibt mehrere Möglichkeiten zum Installieren von PowerShell unter Windows.</span><span class="sxs-lookup"><span data-stu-id="afbb3-104">There are multiple ways to install PowerShell in Windows.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="afbb3-105">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="afbb3-105">Prerequisites</span></span>

<span data-ttu-id="afbb3-106">Die neueste Version von PowerShell wird unter Windows 7 SP1, Windows Server 2008 R2 und höheren Versionen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="afbb3-106">The latest release of PowerShell is supported on Windows 7 SP1, Server 2008 R2, and later versions.</span></span>

<span data-ttu-id="afbb3-107">Zum Aktivieren des PowerShell-Remoting über WSMan müssen die folgenden Voraussetzungen erfüllt sein:</span><span class="sxs-lookup"><span data-stu-id="afbb3-107">To enable PowerShell remoting over WSMan, the following prerequisites need to be met:</span></span>

- <span data-ttu-id="afbb3-108">[Universal C-Runtime](https://www.microsoft.com/download/details.aspx?id=50410) muss unter Windows-Versionen vor Windows 10 installiert sein.</span><span class="sxs-lookup"><span data-stu-id="afbb3-108">Install the [Universal C Runtime](https://www.microsoft.com/download/details.aspx?id=50410) on Windows versions predating Windows 10.</span></span> <span data-ttu-id="afbb3-109">Die Runtime ist über einen direkten Download oder Windows-Update verfügbar.</span><span class="sxs-lookup"><span data-stu-id="afbb3-109">It's available via direct download or Windows Update.</span></span> <span data-ttu-id="afbb3-110">Auf vollständig gepatchten Systemen ist dieses Paket bereits installiert.</span><span class="sxs-lookup"><span data-stu-id="afbb3-110">Fully patched systems already have this package installed.</span></span>
- <span data-ttu-id="afbb3-111">Installieren Sie Windows Management Framework (WMF) 4.0 oder höher auf Windows 7 und Windows Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="afbb3-111">Install the Windows Management Framework (WMF) 4.0 or newer on Windows 7 and Windows Server 2008 R2.</span></span> <span data-ttu-id="afbb3-112">Weitere Informationen zu WMF erhalten Sie in der [WMF-Übersicht](/powershell/scripting/wmf/overview).</span><span class="sxs-lookup"><span data-stu-id="afbb3-112">For more information about WMF, see [WMF Overview](/powershell/scripting/wmf/overview).</span></span>

## <a name="download-the-installer-package"></a><span data-ttu-id="afbb3-113">Herunterladen des Installationspakets</span><span class="sxs-lookup"><span data-stu-id="afbb3-113">Download the installer package</span></span>

<span data-ttu-id="afbb3-114">Laden Sie zum Installieren von PowerShell unter Windows das [neueste][] Installationspaket von GitHub herunter.</span><span class="sxs-lookup"><span data-stu-id="afbb3-114">To install PowerShell on Windows, download the [latest][] install package from GitHub.</span></span> <span data-ttu-id="afbb3-115">Sie können auch die neueste [Vorschauversion][] herunterladen.</span><span class="sxs-lookup"><span data-stu-id="afbb3-115">You can also find the latest [preview][] version.</span></span> <span data-ttu-id="afbb3-116">Scrollen Sie auf der Seite „Release“ nach unten zum Abschnitt **Assets**.</span><span class="sxs-lookup"><span data-stu-id="afbb3-116">Scroll down to the **Assets** section of the Release page.</span></span> <span data-ttu-id="afbb3-117">Der Abschnitt **Assets** ist möglicherweise zugeklappt, sodass Sie darauf klicken müssen, um ihn aufzuklappen.</span><span class="sxs-lookup"><span data-stu-id="afbb3-117">The **Assets** section may be collapsed, so you may need to click to expand it.</span></span>

## <a name="installing-the-msi-package"></a><span data-ttu-id="afbb3-118"><a id="msi" />Installieren des MSI-Pakets</span><span class="sxs-lookup"><span data-stu-id="afbb3-118"><a id="msi" />Installing the MSI package</span></span>

<span data-ttu-id="afbb3-119">Die MSI-Datei sieht so aus: `PowerShell-<version>-win-<os-arch>.msi`.</span><span class="sxs-lookup"><span data-stu-id="afbb3-119">The MSI file looks like `PowerShell-<version>-win-<os-arch>.msi`.</span></span> <span data-ttu-id="afbb3-120">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="afbb3-120">For example:</span></span>

- `PowerShell-7.1.3-win-x64.msi`
- `PowerShell-7.1.3-win-x86.msi`

<span data-ttu-id="afbb3-121">Sobald sie heruntergeladen wurde, führen Sie den Installer mit einem Doppelklick aus und befolgen die Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="afbb3-121">Once downloaded, double-click the installer and follow the prompts.</span></span>

<span data-ttu-id="afbb3-122">Das Installationsprogramm erstellt eine Verknüpfung im Windows-Startmenü.</span><span class="sxs-lookup"><span data-stu-id="afbb3-122">The installer creates a shortcut in the Windows Start Menu.</span></span>

- <span data-ttu-id="afbb3-123">Das Paket wird standardmäßig unter `$env:ProgramFiles\PowerShell\<version>` installiert</span><span class="sxs-lookup"><span data-stu-id="afbb3-123">By default the package is installed to `$env:ProgramFiles\PowerShell\<version>`</span></span>
- <span data-ttu-id="afbb3-124">Sie können PowerShell über das Startmenü oder über `$env:ProgramFiles\PowerShell\<version>\pwsh.exe` starten</span><span class="sxs-lookup"><span data-stu-id="afbb3-124">You can launch PowerShell via the Start Menu or `$env:ProgramFiles\PowerShell\<version>\pwsh.exe`</span></span>

> [!NOTE]
> <span data-ttu-id="afbb3-125">PowerShell 7.1 wird in ein neues Verzeichnis installiert und parallel mit Windows PowerShell 5.1 ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="afbb3-125">PowerShell 7.1 installs to a new directory and runs side-by-side with Windows PowerShell 5.1.</span></span>
> <span data-ttu-id="afbb3-126">PowerShell 7.1 ist ein direktes Upgrade, das PowerShell 6.x.</span><span class="sxs-lookup"><span data-stu-id="afbb3-126">PowerShell 7.1 is an in-place upgrade that replaces PowerShell 6.x.</span></span> <span data-ttu-id="afbb3-127">oder PowerShell 7.0 ersetzt.</span><span class="sxs-lookup"><span data-stu-id="afbb3-127">or PowerShell 7.0.</span></span>
>
> - <span data-ttu-id="afbb3-128">PowerShell 7.1 wird in `$env:ProgramFiles\PowerShell\7` installiert.</span><span class="sxs-lookup"><span data-stu-id="afbb3-128">PowerShell 7.1 is installed to `$env:ProgramFiles\PowerShell\7`</span></span>
> - <span data-ttu-id="afbb3-129">Der Ordner `$env:ProgramFiles\PowerShell\7` wird `$env:PATH` hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="afbb3-129">The `$env:ProgramFiles\PowerShell\7` folder is added to `$env:PATH`</span></span>
> - <span data-ttu-id="afbb3-130">Der Ordner `$env:ProgramFiles\PowerShell\6` wird gelöscht.</span><span class="sxs-lookup"><span data-stu-id="afbb3-130">The `$env:ProgramFiles\PowerShell\6` folder is deleted</span></span>
>
> <span data-ttu-id="afbb3-131">Wenn PowerShell 7.1 parallel mit anderen Versionen ausgeführt werden muss, installieren Sie die andere Version mit der Methode unter [Installieren des ZIP-Pakets](#zip) in einem anderen Ordner.</span><span class="sxs-lookup"><span data-stu-id="afbb3-131">If you need to run PowerShell 7.1 side-by-side with other versions, use the [ZIP install](#zip) method to install the other version to a different folder.</span></span>

### <a name="administrative-install-from-the-command-line"></a><span data-ttu-id="afbb3-132">Administrative Installation über die Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="afbb3-132">Administrative install from the command line</span></span>

<span data-ttu-id="afbb3-133">MSI-Pakete können über die Befehlszeile installiert werden, sodass Administratoren Pakete ohne Benutzerinteraktion bereitstellen können.</span><span class="sxs-lookup"><span data-stu-id="afbb3-133">MSI packages can be installed from the command line allowing administrators to deploy packages without user interaction.</span></span> <span data-ttu-id="afbb3-134">Das MSI-Paket enthält die folgenden Eigenschaften zum Steuern der Installationsoptionen:</span><span class="sxs-lookup"><span data-stu-id="afbb3-134">The MSI package includes the following properties to control the installation options:</span></span>

- <span data-ttu-id="afbb3-135">**ADD_EXPLORER_CONTEXT_MENU_OPENPOWERSHELL** – Diese Eigenschaft steuert die Option zum Hinzufügen des Elements **PowerShell öffnen** zum Kontextmenü im Windows-Explorer.</span><span class="sxs-lookup"><span data-stu-id="afbb3-135">**ADD_EXPLORER_CONTEXT_MENU_OPENPOWERSHELL** - This property controls the option for adding the **Open PowerShell** item to the context menu in Windows Explorer.</span></span>
- <span data-ttu-id="afbb3-136">**ADD_FILE_CONTEXT_MENU_RUNPOWERSHELL**: Diese Eigenschaft steuert das Hinzufügen der Option **Mit PowerShell ausführen** zum Kontextmenü im Windows-Explorer.</span><span class="sxs-lookup"><span data-stu-id="afbb3-136">**ADD_FILE_CONTEXT_MENU_RUNPOWERSHELL** - This property controls the option for adding the **Run with PowerShell** item to the context menu in Windows Explorer.</span></span>
- <span data-ttu-id="afbb3-137">**ENABLE_PSREMOTING** – Diese Eigenschaft steuert die Option zum Aktivieren von PowerShell-Remoting während der Installation.</span><span class="sxs-lookup"><span data-stu-id="afbb3-137">**ENABLE_PSREMOTING** - This property controls the option for enabling PowerShell remoting during installation.</span></span>
- <span data-ttu-id="afbb3-138">**REGISTER_MANIFEST** – Diese Eigenschaft steuert die Option zum Registrieren des Manifests für Windows-Ereignisprotokollierung.</span><span class="sxs-lookup"><span data-stu-id="afbb3-138">**REGISTER_MANIFEST** - This property controls the option for registering the Windows Event Logging manifest.</span></span>

<span data-ttu-id="afbb3-139">Das folgenden Beispiel zeigt, wie PowerShell mit allen aktivierten Installationsoptionen im Hintergrund installiert wird.</span><span class="sxs-lookup"><span data-stu-id="afbb3-139">The following example shows how to silently install PowerShell with all the install options enabled.</span></span>

```powershell
msiexec.exe /package PowerShell-7.1.3-win-x64.msi /quiet ADD_EXPLORER_CONTEXT_MENU_OPENPOWERSHELL=1 ENABLE_PSREMOTING=1 REGISTER_MANIFEST=1
```

<span data-ttu-id="afbb3-140">Eine vollständige Liste der Befehlszeilenoptionen für `Msiexec.exe` finden Sie unter [Befehlszeilenoptionen](/windows/desktop/Msi/command-line-options).</span><span class="sxs-lookup"><span data-stu-id="afbb3-140">For a full list of command-line options for `Msiexec.exe`, see [Command line options](/windows/desktop/Msi/command-line-options).</span></span>

### <a name="registry-keys-created-during-installation"></a><span data-ttu-id="afbb3-141">Während der Installation erstellte Registrierungsschlüssel</span><span class="sxs-lookup"><span data-stu-id="afbb3-141">Registry keys created during installation</span></span>

<span data-ttu-id="afbb3-142">Ab PowerShell 7.1 erstellt das MSI-Paket Registrierungsschlüssel, die den Installationsort und die PowerShell-Version speichern.</span><span class="sxs-lookup"><span data-stu-id="afbb3-142">Beginning in PowerShell 7.1, the MSI package creates registry keys that store the installation location and version of PowerShell.</span></span> <span data-ttu-id="afbb3-143">Diese Werte befinden sich in `HKLM\Software\Microsoft\PowerShellCore\InstalledVersions\<GUID>`.</span><span class="sxs-lookup"><span data-stu-id="afbb3-143">These values are located in `HKLM\Software\Microsoft\PowerShellCore\InstalledVersions\<GUID>`.</span></span> <span data-ttu-id="afbb3-144">Der Wert von `<GUID>` ist für jeden Buildtyp (Release oder Vorschau), Hauptversion und Architektur eindeutig.</span><span class="sxs-lookup"><span data-stu-id="afbb3-144">The value of `<GUID>` is unique for each build type (release or preview), major version, and architecture.</span></span>

|    <span data-ttu-id="afbb3-145">Release</span><span class="sxs-lookup"><span data-stu-id="afbb3-145">Release</span></span>    | <span data-ttu-id="afbb3-146">Aufbau</span><span class="sxs-lookup"><span data-stu-id="afbb3-146">Architecture</span></span> |                                          <span data-ttu-id="afbb3-147">Registrierungsschlüssel</span><span class="sxs-lookup"><span data-stu-id="afbb3-147">Registry Key</span></span>                                           |
| ------------- | :----------: | ----------------------------------------------------------------------------------------------- |
| <span data-ttu-id="afbb3-148">Release 7.1.x</span><span class="sxs-lookup"><span data-stu-id="afbb3-148">7.1.x Release</span></span> |     <span data-ttu-id="afbb3-149">x86</span><span class="sxs-lookup"><span data-stu-id="afbb3-149">x86</span></span>      | `HKLM\Software\Microsoft\PowerShellCore\InstalledVersions\1d00683b-0f84-4db8-a64f-2f98ad42fe06` |
| <span data-ttu-id="afbb3-150">Release 7.1.x</span><span class="sxs-lookup"><span data-stu-id="afbb3-150">7.1.x Release</span></span> |     <span data-ttu-id="afbb3-151">x64</span><span class="sxs-lookup"><span data-stu-id="afbb3-151">x64</span></span>      | `HKLM\Software\Microsoft\PowerShellCore\InstalledVersions\31ab5147-9a97-4452-8443-d9709f0516e1` |
| <span data-ttu-id="afbb3-152">Vorschau 7.1.x</span><span class="sxs-lookup"><span data-stu-id="afbb3-152">7.1.x Preview</span></span> |     <span data-ttu-id="afbb3-153">x86</span><span class="sxs-lookup"><span data-stu-id="afbb3-153">x86</span></span>      | `HKLM\Software\Microsoft\PowerShellCore\InstalledVersions\86abcfbd-1ccc-4a88-b8b2-0facfde29094` |
| <span data-ttu-id="afbb3-154">Vorschau 7.1.x</span><span class="sxs-lookup"><span data-stu-id="afbb3-154">7.1.x Preview</span></span> |     <span data-ttu-id="afbb3-155">x64</span><span class="sxs-lookup"><span data-stu-id="afbb3-155">x64</span></span>      | `HKLM\Software\Microsoft\PowerShellCore\InstalledVersions\39243d76-adaf-42b1-94fb-16ecf83237c8` |

<span data-ttu-id="afbb3-156">Dies kann von Administratoren und Entwicklern verwendet werden, um den Pfad zu PowerShell zu finden.</span><span class="sxs-lookup"><span data-stu-id="afbb3-156">This can be used by administrators and developers to find the path to PowerShell.</span></span> <span data-ttu-id="afbb3-157">Die `<GUID>`-Werte sind für alle Vorschau- und Nebenversionen identisch.</span><span class="sxs-lookup"><span data-stu-id="afbb3-157">The `<GUID>` values will be the same for all preview and minor version releases.</span></span> <span data-ttu-id="afbb3-158">Die `<GUID>`-Werte werden für jede Hauptversion geändert.</span><span class="sxs-lookup"><span data-stu-id="afbb3-158">The `<GUID>` values are changed for each major release.</span></span>

## <a name="installing-the-zip-package"></a><span data-ttu-id="afbb3-159"><a id="zip" />Installieren des ZIP-Pakets</span><span class="sxs-lookup"><span data-stu-id="afbb3-159"><a id="zip" />Installing the ZIP package</span></span>

<span data-ttu-id="afbb3-160">Binäre PowerShell ZIP-Archive werden zur Verfügung gestellt, um erweiterte Bereitstellungsszenarios zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="afbb3-160">PowerShell binary ZIP archives are provided to enable advanced deployment scenarios.</span></span> <span data-ttu-id="afbb3-161">Laden Sie eines der folgenden ZIP-Archive von der Seite [Releases][Releases] herunter.</span><span class="sxs-lookup"><span data-stu-id="afbb3-161">Download one of the following ZIP archives from the [releases][releases] page.</span></span>

- <span data-ttu-id="afbb3-162">PowerShell-7.1.3-win-x64.zip</span><span class="sxs-lookup"><span data-stu-id="afbb3-162">PowerShell-7.1.3-win-x64.zip</span></span>
- <span data-ttu-id="afbb3-163">PowerShell-7.1.3-win-x86.zip</span><span class="sxs-lookup"><span data-stu-id="afbb3-163">PowerShell-7.1.3-win-x86.zip</span></span>
- <span data-ttu-id="afbb3-164">PowerShell-7.1.3-win-arm64.zip</span><span class="sxs-lookup"><span data-stu-id="afbb3-164">PowerShell-7.1.3-win-arm64.zip</span></span>
- <span data-ttu-id="afbb3-165">PowerShell-7.1.3-win-arm32.zip</span><span class="sxs-lookup"><span data-stu-id="afbb3-165">PowerShell-7.1.3-win-arm32.zip</span></span>

<span data-ttu-id="afbb3-166">Je nachdem, wie Sie die Datei herunterladen, müssen Sie die Blockierung der Datei mit dem Cmdlet `Unblock-File` aufheben.</span><span class="sxs-lookup"><span data-stu-id="afbb3-166">Depending on how you download the file you may need to unblock the file using the `Unblock-File` cmdlet.</span></span> <span data-ttu-id="afbb3-167">Entpacken Sie den Inhalt an den Speicherort Ihrer Wahl, und führen Sie `pwsh.exe` von dort aus.</span><span class="sxs-lookup"><span data-stu-id="afbb3-167">Unzip the contents to the location of your choice and run `pwsh.exe` from there.</span></span> <span data-ttu-id="afbb3-168">Anders als bei der Installation der MSI-Pakete erfolgt bei der Installation des ZIP-Archivs keine Prüfung auf Voraussetzungen.</span><span class="sxs-lookup"><span data-stu-id="afbb3-168">Unlike installing the MSI packages, installing the ZIP archive doesn't check for prerequisites.</span></span> <span data-ttu-id="afbb3-169">Damit Remoting über WSMan einwandfrei funktioniert, müssen die [Voraussetzungen](#prerequisites) unbedingt erfüllt sein.</span><span class="sxs-lookup"><span data-stu-id="afbb3-169">For remoting over WSMan to work properly, ensure that you've met the [prerequisites](#prerequisites).</span></span>

<span data-ttu-id="afbb3-170">Installieren Sie mit dieser Methode die ARM-basierte Version von PowerShell auf Computern wie Microsoft Surface Pro X. Die besten Ergebnisse erzielen Sie, wenn Sie PowerShell im Ordner `$env:ProgramFiles\PowerShell\7` installieren.</span><span class="sxs-lookup"><span data-stu-id="afbb3-170">Use this method to install the ARM-based version of PowerShell on computers like the Microsoft Surface Pro X. For best results, install PowerShell to the to `$env:ProgramFiles\PowerShell\7` folder.</span></span>

> [!NOTE]
> <span data-ttu-id="afbb3-171">Sie können diese Methode verwenden, um eine beliebige Version von PowerShell zu installieren, einschließlich der neuesten:</span><span class="sxs-lookup"><span data-stu-id="afbb3-171">You can use this method to install any version of PowerShell including the latest:</span></span>
> - <span data-ttu-id="afbb3-172">Stabiles Release: [https://aka.ms/powershell-release?tag=stable](https://aka.ms/powershell-release?tag=stable)</span><span class="sxs-lookup"><span data-stu-id="afbb3-172">Stable release: [https://aka.ms/powershell-release?tag=stable](https://aka.ms/powershell-release?tag=stable)</span></span>
> - <span data-ttu-id="afbb3-173">Vorschaurelease: [https://aka.ms/powershell-release?tag=preview](https://aka.ms/powershell-release?tag=preview)</span><span class="sxs-lookup"><span data-stu-id="afbb3-173">Preview release: [https://aka.ms/powershell-release?tag=preview](https://aka.ms/powershell-release?tag=preview)</span></span>
> - <span data-ttu-id="afbb3-174">LTS-Release: [https://aka.ms/powershell-release?tag=lts](https://aka.ms/powershell-release?tag=lts)</span><span class="sxs-lookup"><span data-stu-id="afbb3-174">LTS release: [https://aka.ms/powershell-release?tag=lts](https://aka.ms/powershell-release?tag=lts)</span></span>

## <a name="deploying-on-windows-10-iot-enterprise"></a><span data-ttu-id="afbb3-175">Bereitstellung unter Windows 10 IoT Enterprise</span><span class="sxs-lookup"><span data-stu-id="afbb3-175">Deploying on Windows 10 IoT Enterprise</span></span>

<span data-ttu-id="afbb3-176">Bei Windows 10 IoT Enterprise ist Windows PowerShell bereits im Funktionsumfang enthalten, sodass PowerShell 7 bereitgestellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="afbb3-176">Windows 10 IoT Enterprise comes with Windows PowerShell, which we can use to deploy PowerShell 7.</span></span>

1. <span data-ttu-id="afbb3-177">Erstellen Sie `PSSession` auf dem Zielgerät.</span><span class="sxs-lookup"><span data-stu-id="afbb3-177">Create `PSSession` to target device</span></span>

   ```powershell
   Set-Item -Path WSMan:\localhost\Client\TrustedHosts <deviceip>
   $S = New-PSSession -ComputerName <deviceIp> -Credential Administrator
   ```

1. <span data-ttu-id="afbb3-178">Kopieren Sie das ZIP-Paket auf das Gerät.</span><span class="sxs-lookup"><span data-stu-id="afbb3-178">Copy the ZIP package to the device</span></span>

   ```powershell
   # change the destination to however you had partitioned it with sufficient
   # space for the zip and the unzipped contents
   # the path should be local to the device
   Copy-Item .\PowerShell-<version>-win-<os-arch>.zip -Destination u:\users\administrator\Downloads -ToSession $s
   ```

1. <span data-ttu-id="afbb3-179">Stellen Sie eine Verbindung mit dem Gerät her, und erweitern Sie das Archiv.</span><span class="sxs-lookup"><span data-stu-id="afbb3-179">Connect to the device and expand the archive</span></span>

   ```powershell
   Enter-PSSession $s
   Set-Location u:\users\administrator\downloads
   Expand-Archive .\PowerShell-<version>-win-<os-arch>.zip
   ```

1. <span data-ttu-id="afbb3-180">Richten Sie Remoting für PowerShell 7 ein.</span><span class="sxs-lookup"><span data-stu-id="afbb3-180">Set up remoting to PowerShell 7</span></span>

   ```powershell
   Set-Location .\PowerShell-<version>-win-<os-arch>
   # Be sure to use the -PowerShellHome parameter otherwise it'll try to create a new
   # endpoint with Windows PowerShell 5.1
   .\Install-PowerShellRemoting.ps1 -PowerShellHome .
   # You'll get an error message and will be disconnected from the device because
   # it has to restart WinRM
   ```

1. <span data-ttu-id="afbb3-181">Stellen Sie eine Verbindung mit dem PowerShell 7-Endpunkt auf dem Gerät her.</span><span class="sxs-lookup"><span data-stu-id="afbb3-181">Connect to PowerShell 7 endpoint on device</span></span>

   ```powershell
   # Be sure to use the -Configuration parameter. If you omit it, you will connect to Windows PowerShell 5.1
   Enter-PSSession -ComputerName <deviceIp> -Credential Administrator -Configuration powershell.<version>
   ```

## <a name="deploying-on-windows-10-iot-core"></a><span data-ttu-id="afbb3-182">Bereitstellung unter Windows 10 IoT Core</span><span class="sxs-lookup"><span data-stu-id="afbb3-182">Deploying on Windows 10 IoT Core</span></span>

<span data-ttu-id="afbb3-183">Bei Windows 10 IoT Core wird Windows PowerShell hinzugefügt, wenn Sie das Feature _IOT_POWERSHELL_ aufnehmen. Über dieses Feature kann PowerShell 7 bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="afbb3-183">Windows 10 IoT Core adds Windows PowerShell when you include _IOT_POWERSHELL_ feature, which we can use to deploy PowerShell 7.</span></span> <span data-ttu-id="afbb3-184">Die oben beschriebenen Schritte für Windows 10 IoT Enterprise können auch für IoT Core ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="afbb3-184">The steps defined above for Windows 10 IoT Enterprise can be followed for IoT Core as well.</span></span>

<span data-ttu-id="afbb3-185">Verwenden Sie zum Hinzufügen der aktuellen PowerShell-Version im Image den Befehl [Import-PSCoreRelease][]. Mit diesem Befehl wird das Paket im Arbeitsbereich eingefügt und das Feature _OPENSRC_POWERSHELL_ zu Ihrem Image hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="afbb3-185">For adding the latest PowerShell in the shipping image, use [Import-PSCoreRelease][] command to include the package in the workarea and add _OPENSRC_POWERSHELL_ feature to your image.</span></span>

> [!NOTE]
> <span data-ttu-id="afbb3-186">Bei der ARM64-Architektur wird Windows PowerShell nicht hinzugefügt, wenn Sie _IOT_POWERSHELL_ einfügen.</span><span class="sxs-lookup"><span data-stu-id="afbb3-186">For ARM64 architecture, Windows PowerShell is not added when you include _IOT_POWERSHELL_.</span></span> <span data-ttu-id="afbb3-187">Daher funktioniert die ZIP-basierte Installation nicht.</span><span class="sxs-lookup"><span data-stu-id="afbb3-187">So the zip based install will not work.</span></span> <span data-ttu-id="afbb3-188">Sie müssen den Befehl `Import-PSCoreRelease` verwenden, um ihn im Image hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="afbb3-188">You will need to use `Import-PSCoreRelease` command to add it in the image.</span></span>

## <a name="deploying-on-nano-server"></a><span data-ttu-id="afbb3-189">Bereitstellen auf Nano Server</span><span class="sxs-lookup"><span data-stu-id="afbb3-189">Deploying on Nano Server</span></span>

<span data-ttu-id="afbb3-190">Diese Anweisungen gehen davon aus, dass der Nano Server ein „monitorloses“ Betriebssystem ist, unter dem bereits eine Version von PowerShell ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="afbb3-190">These instructions assume that the Nano Server is a "headless" OS that has a version of PowerShell is already running on it.</span></span> <span data-ttu-id="afbb3-191">Weitere Informationen finden Sie in der [Dokumentation zu Nano Server Image Builder](/windows-server/get-started/deploy-nano-server).</span><span class="sxs-lookup"><span data-stu-id="afbb3-191">For more information, see the [Nano Server Image Builder](/windows-server/get-started/deploy-nano-server) documentation.</span></span>

<span data-ttu-id="afbb3-192">PowerShell-Binärdateien können auf zwei verschiedene Arten bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="afbb3-192">PowerShell binaries can be deployed using two different methods.</span></span>

1. <span data-ttu-id="afbb3-193">Offline: Binden Sie die Nano Server-VHD ein, und entpacken Sie den Inhalt der ZIP-Datei an dem von Ihnen gewünschten Speicherort in dem eingebundenen Image.</span><span class="sxs-lookup"><span data-stu-id="afbb3-193">Offline - Mount the Nano Server VHD and unzip the contents of the zip file to your chosen location within the mounted image.</span></span>
1. <span data-ttu-id="afbb3-194">Online: Übertragen Sie die ZIP-Datei über eine PowerShell-Sitzung, und entpacken Sie sie an dem von Ihnen gewünschten Speicherort.</span><span class="sxs-lookup"><span data-stu-id="afbb3-194">Online - Transfer the zip file over a PowerShell Session and unzip it in your chosen location.</span></span>

<span data-ttu-id="afbb3-195">In beiden Fällen benötigen Sie das ZIP-Releasepaket für Windows 10 x64.</span><span class="sxs-lookup"><span data-stu-id="afbb3-195">In both cases, you need the Windows 10 x64 ZIP release package.</span></span> <span data-ttu-id="afbb3-196">Führen Sie die Befehle in einer „Administrator“-Instanz von PowerShell aus.</span><span class="sxs-lookup"><span data-stu-id="afbb3-196">Run the commands within an "Administrator" instance of PowerShell.</span></span>

### <a name="offline-deployment-of-powershell"></a><span data-ttu-id="afbb3-197">Offlinebereitstellung von PowerShell</span><span class="sxs-lookup"><span data-stu-id="afbb3-197">Offline Deployment of PowerShell</span></span>

1. <span data-ttu-id="afbb3-198">Verwenden Sie Ihr bevorzugtes ZIP-Hilfsprogramm, um das Paket in ein Verzeichnis im eingebundenen Nano Server-Image zu entpacken.</span><span class="sxs-lookup"><span data-stu-id="afbb3-198">Use your favorite zip utility to unzip the package to a directory within the mounted Nano Server image.</span></span>
1. <span data-ttu-id="afbb3-199">Heben Sie die Bereitstellung des Images auf, und starten Sie es.</span><span class="sxs-lookup"><span data-stu-id="afbb3-199">Unmount the image and boot it.</span></span>
1. <span data-ttu-id="afbb3-200">Stellen Sie eine Verbindung mit der integrierten Instanz von Windows PowerShell her.</span><span class="sxs-lookup"><span data-stu-id="afbb3-200">Connect to the built-in instance of Windows PowerShell.</span></span>
1. <span data-ttu-id="afbb3-201">Befolgen Sie die Anweisungen, um einen Remoting-Endpunkt mithilfe der [„Andere Instanz-Methode“][] zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="afbb3-201">Follow the instructions to create a remoting endpoint using the ["another instance technique"][].</span></span>

### <a name="online-deployment-of-powershell"></a><span data-ttu-id="afbb3-202">Onlinebereitstellung von PowerShell</span><span class="sxs-lookup"><span data-stu-id="afbb3-202">Online Deployment of PowerShell</span></span>

<span data-ttu-id="afbb3-203">Stellen Sie PowerShell mithilfe der folgenden Schritte für Nano Server bereit.</span><span class="sxs-lookup"><span data-stu-id="afbb3-203">Deploy PowerShell to Nano Server using the following steps.</span></span>

- <span data-ttu-id="afbb3-204">Herstellen einer Verbindung mit der integrierten Instanz von Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="afbb3-204">Connect to the built-in instance of Windows PowerShell</span></span>

  ```powershell
  $session = New-PSSession -ComputerName <Nano Server IP address> -Credential <An Administrator account on the system>
  ```

- <span data-ttu-id="afbb3-205">Kopieren Sie die Datei in die Nano Server-Instanz.</span><span class="sxs-lookup"><span data-stu-id="afbb3-205">Copy the file to the Nano Server instance</span></span>

  ```powershell
  Copy-Item <local PS Core download location>\powershell-<version>-win-x64.zip c:\ -ToSession $session
  ```

- <span data-ttu-id="afbb3-206">Geben Sie die Sitzung ein.</span><span class="sxs-lookup"><span data-stu-id="afbb3-206">Enter the session</span></span>

  ```powershell
  Enter-PSSession $session
  ```

- <span data-ttu-id="afbb3-207">Extrahieren Sie die ZIP-Datei.</span><span class="sxs-lookup"><span data-stu-id="afbb3-207">Extract the ZIP file</span></span>

  ```powershell
  # Insert the appropriate version.
  Expand-Archive -Path C:\powershell-<version>-win-x64.zip -DestinationPath "C:\PowerShell_<version>"
  ```

- <span data-ttu-id="afbb3-208">Befolgen Sie die Anweisungen, wenn Sie auf WSMan basierendes Remoting verwenden möchten, um einen Remoting-Endpunkt mithilfe der [„Andere Instanz-Methode“][] zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="afbb3-208">If you want WSMan-based remoting, follow the instructions to create a remoting endpoint using the ["another instance technique"][].</span></span>

## <a name="install-as-a-net-global-tool"></a><span data-ttu-id="afbb3-209">Installieren als globales .NET-Tool</span><span class="sxs-lookup"><span data-stu-id="afbb3-209">Install as a .NET Global tool</span></span>

<span data-ttu-id="afbb3-210">Wenn Sie das [.NET Core SDK](/dotnet/core/sdk) bereits installiert haben, können Sie PowerShell einfach als [globales .NET-Tool](/dotnet/core/tools/global-tools) installieren.</span><span class="sxs-lookup"><span data-stu-id="afbb3-210">If you already have the [.NET Core SDK](/dotnet/core/sdk) installed, it's easy to install PowerShell as a [.NET Global tool](/dotnet/core/tools/global-tools).</span></span>

```
dotnet tool install --global PowerShell
```

<span data-ttu-id="afbb3-211">Der .NET-Toolinstaller fügt `$env:USERPROFILE\dotnet\tools` Ihrer `$env:PATH`-Umgebungsvariablen hinzu.</span><span class="sxs-lookup"><span data-stu-id="afbb3-211">The dotnet tool installer adds `$env:USERPROFILE\dotnet\tools` to your `$env:PATH` environment variable.</span></span> <span data-ttu-id="afbb3-212">Die aktuell ausgeführte Shell verfügt jedoch nicht über die aktualisierte Umgebungsvariable `$env:PATH`.</span><span class="sxs-lookup"><span data-stu-id="afbb3-212">However, the currently running shell doesn't have the updated `$env:PATH`.</span></span> <span data-ttu-id="afbb3-213">Sie können PowerShell über eine neue Shell starten, indem Sie `pwsh` eingeben.</span><span class="sxs-lookup"><span data-stu-id="afbb3-213">You can start PowerShell from a new shell by typing `pwsh`.</span></span>

## <a name="install-powershell-via-winget"></a><span data-ttu-id="afbb3-214">Installieren von PowerShell über Winget</span><span class="sxs-lookup"><span data-stu-id="afbb3-214">Install PowerShell via Winget</span></span>

<span data-ttu-id="afbb3-215">Mit dem Befehlszeilentool `winget` können Entwickler Anwendungen auf Windows 10-Computern ermitteln, installieren, aktualisieren, entfernen und konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="afbb3-215">The `winget` command-line tool enables developers to discover, install, upgrade, remove, and configure applications on Windows 10 computers.</span></span> <span data-ttu-id="afbb3-216">Dieses Tool ist die Clientschnittstelle für den Windows-Paket-Manager-Dienst.</span><span class="sxs-lookup"><span data-stu-id="afbb3-216">This tool is the client interface to the Windows Package Manager service.</span></span>

> [!NOTE]
> <span data-ttu-id="afbb3-217">Das `winget`-Tool befindet sich zurzeit in der Vorschau.</span><span class="sxs-lookup"><span data-stu-id="afbb3-217">The `winget` tool is currently a preview.</span></span> <span data-ttu-id="afbb3-218">Zurzeit sind nicht alle geplanten Funktionen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="afbb3-218">Not all planned functionality is available at this time.</span></span>
> <span data-ttu-id="afbb3-219">Diese Methode sollten Sie nicht in einem Produktionsbereitstellungsszenario verwenden.</span><span class="sxs-lookup"><span data-stu-id="afbb3-219">You should not use this method in a production deployment scenario.</span></span> <span data-ttu-id="afbb3-220">Eine Liste der Systemanforderungen und Installationsanweisungen finden Sie in der Dokumentation zu [winget].</span><span class="sxs-lookup"><span data-stu-id="afbb3-220">See the [winget] documentation for a list of system requirements and install instructions.</span></span>

<span data-ttu-id="afbb3-221">Die folgenden Befehle können verwendet werden, um PowerShell mithilfe der veröffentlichten `winget`-Pakete zu installieren:</span><span class="sxs-lookup"><span data-stu-id="afbb3-221">The following commands can be used to install PowerShell using the published `winget` packages:</span></span>

1. <span data-ttu-id="afbb3-222">Suchen nach der neuesten Version von PowerShell</span><span class="sxs-lookup"><span data-stu-id="afbb3-222">Search for the latest version of PowerShell</span></span>

   ```powershell
   winget search Microsoft.PowerShell
   ```

   ```Output
   Name                      Id                                Version
   ---------------------------------------------------------------------------
   PowerShell                Microsoft.PowerShell              7.1.3
   PowerShell Preview (MSIX) Microsoft.PowerShell-Preview-MSIX 7.0.2
   PowerShell-Preview        Microsoft.PowerShell-Preview      7.2.0-preview.3
   ```

1. <span data-ttu-id="afbb3-223">Installieren einer PowerShell-Version mithilfe des `--exact`-Parameters</span><span class="sxs-lookup"><span data-stu-id="afbb3-223">Install a version of PowerShell using the `--exact` parameter</span></span>

   ```powershell
   winget install --name PowerShell --exact
   winget install --name PowerShell-Preview --exact
   ```

## <a name="installing-from-the-microsoft-store"></a><span data-ttu-id="afbb3-224"><a id="msix" />Installieren über den Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="afbb3-224"><a id="msix" />Installing from the Microsoft Store</span></span>

<span data-ttu-id="afbb3-225">PowerShell 7.1 wurde im Microsoft Store veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="afbb3-225">PowerShell 7.1 has been published to the Microsoft Store.</span></span> <span data-ttu-id="afbb3-226">Die PowerShell-Version finden Sie auf der Website von [Microsoft Store](https://www.microsoft.com/store/apps/9MZ1SNWT0N5D) oder in der Store-Anwendung unter Windows.</span><span class="sxs-lookup"><span data-stu-id="afbb3-226">You can find the PowerShell release on the [Microsoft Store](https://www.microsoft.com/store/apps/9MZ1SNWT0N5D) website or in the Store application in Windows.</span></span>

<span data-ttu-id="afbb3-227">Vorteile des Microsoft Store-Pakets:</span><span class="sxs-lookup"><span data-stu-id="afbb3-227">Benefits of the Microsoft Store package:</span></span>

- <span data-ttu-id="afbb3-228">Direkt in Windows 10 integrierte automatische Updates</span><span class="sxs-lookup"><span data-stu-id="afbb3-228">Automatic updates built right into Windows 10</span></span>
- <span data-ttu-id="afbb3-229">Integration in andere Softwareverteilungsmechanismen wie Intune und SCCM</span><span class="sxs-lookup"><span data-stu-id="afbb3-229">Integrates with other software distribution mechanisms like Intune and SCCM</span></span>

<span data-ttu-id="afbb3-230">Einschränkungen:</span><span class="sxs-lookup"><span data-stu-id="afbb3-230">Limitations:</span></span>

<span data-ttu-id="afbb3-231">MSIX-Pakete werden in einer Sandbox für Anwendungen ausgeführt, die den Zugriff auf einige Dateisystem- und Registrierungsspeicherorte virtualisiert.</span><span class="sxs-lookup"><span data-stu-id="afbb3-231">MSIX packages run in an application sandbox that virtualizes access to some filesystem and registry locations.</span></span>

- <span data-ttu-id="afbb3-232">Alle Registrierungsänderungen unter HKEY_CURRENT_USER werden beim Schreiben in einen privaten Speicherort benutzer- und App-spezifisch kopiert.</span><span class="sxs-lookup"><span data-stu-id="afbb3-232">All registry changes under HKEY_CURRENT_USER are copied on write to a private, per-user, per-app location.</span></span> <span data-ttu-id="afbb3-233">Diese Werte sind daher für andere Anwendungen nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="afbb3-233">Therefore, those values are not available to other applications.</span></span>
- <span data-ttu-id="afbb3-234">Alle in `$PSHOME` gespeicherten Konfigurationseinstellungen auf Systemebene lassen sich nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="afbb3-234">Any system-level configuration settings stored in `$PSHOME` cannot be modified.</span></span> <span data-ttu-id="afbb3-235">Dies schließt die WSMAN-Konfiguration ein.</span><span class="sxs-lookup"><span data-stu-id="afbb3-235">This includes the WSMAN configuration.</span></span> <span data-ttu-id="afbb3-236">Dadurch wird verhindert, dass Remotesitzungen eine Verbindung mit auf Store basierenden Installationen von PowerShell herstellen.</span><span class="sxs-lookup"><span data-stu-id="afbb3-236">This prevents remote sessions from connecting to Store-based installs of PowerShell.</span></span> <span data-ttu-id="afbb3-237">Konfigurationen auf Benutzerebene und SSH-Remoting werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="afbb3-237">User-level configurations and SSH remoting are supported.</span></span>

<span data-ttu-id="afbb3-238">Weitere Informationen finden Sie unter [Grundlegendes zur Funktionsweise von App-Paketen unter Windows](/windows/msix/desktop/desktop-to-uwp-behind-the-scenes).</span><span class="sxs-lookup"><span data-stu-id="afbb3-238">For more information, see [Understanding how packaged desktop apps run on Windows](/windows/msix/desktop/desktop-to-uwp-behind-the-scenes).</span></span>

### <a name="using-the-msix-package"></a><span data-ttu-id="afbb3-239">Verwenden des MSIX-Pakets</span><span class="sxs-lookup"><span data-stu-id="afbb3-239">Using the MSIX package</span></span>

> [!NOTE]
> <span data-ttu-id="afbb3-240">Die Vorschaubuilds von PowerShell enthalten ein MSIX-Paket.</span><span class="sxs-lookup"><span data-stu-id="afbb3-240">The preview builds of PowerShell include an MSIX package.</span></span> <span data-ttu-id="afbb3-241">Das MSIX-Paket wird nicht offiziell unterstützt.</span><span class="sxs-lookup"><span data-stu-id="afbb3-241">The MSIX package is not officially supported.</span></span> <span data-ttu-id="afbb3-242">Das Paket wird zu Testzwecken in der Vorschauphase erstellt.</span><span class="sxs-lookup"><span data-stu-id="afbb3-242">The package is built for testing purposes during the preview period.</span></span>

<span data-ttu-id="afbb3-243">Für eine manuelle Installation des MSIX-Pakets auf einem Windows 10-Client laden Sie das MSIX-Paket von der GitHub-Seite mit den [Releases][Releases] herunter.</span><span class="sxs-lookup"><span data-stu-id="afbb3-243">To manually install the MSIX package on a Windows 10 client, download the MSIX package from our GitHub [releases][releases] page.</span></span> <span data-ttu-id="afbb3-244">Scrollen Sie nach unten zum Abschnitt **Assets** des Release, das Sie installieren möchten.</span><span class="sxs-lookup"><span data-stu-id="afbb3-244">Scroll down to the **Assets** section of the Release you want to install.</span></span> <span data-ttu-id="afbb3-245">Der Abschnitt „Assets“ ist möglicherweise reduziert, sodass Sie klicken müssen, um ihn zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="afbb3-245">The Assets section may be collapsed, so you may need to click to expand it.</span></span>

<span data-ttu-id="afbb3-246">Die MSIX-Datei sieht so aus: `PowerShell-<version>-win-<os-arch>.msix`</span><span class="sxs-lookup"><span data-stu-id="afbb3-246">The MSIX file looks like this - `PowerShell-<version>-win-<os-arch>.msix`</span></span>

<span data-ttu-id="afbb3-247">Zum Installieren des Pakets müssen Sie das Cmdlet `Add-AppxPackage` verwenden:</span><span class="sxs-lookup"><span data-stu-id="afbb3-247">To install the package, you must use the `Add-AppxPackage` cmdlet.</span></span>

```powershell
Add-AppxPackage PowerShell-<version>-win-<os-arch>.msix
```

## <a name="how-to-create-a-remoting-endpoint"></a><span data-ttu-id="afbb3-248">Vorgehensweise zum Erstellen eines Remoting-Endpunkts</span><span class="sxs-lookup"><span data-stu-id="afbb3-248">How to create a remoting endpoint</span></span>

<span data-ttu-id="afbb3-249">PowerShell unterstützt das PowerShell-Remotingprotokoll (PSRP) über WSMan und SSH.</span><span class="sxs-lookup"><span data-stu-id="afbb3-249">PowerShell supports the PowerShell Remoting Protocol (PSRP) over both WSMan and SSH.</span></span> <span data-ttu-id="afbb3-250">Weitere Informationen finden Sie unter</span><span class="sxs-lookup"><span data-stu-id="afbb3-250">For more information, see:</span></span>

- <span data-ttu-id="afbb3-251">[SSH-Remoting in PowerShell Core][ssh-remoting]</span><span class="sxs-lookup"><span data-stu-id="afbb3-251">[SSH Remoting in PowerShell Core][ssh-remoting]</span></span>
- <span data-ttu-id="afbb3-252">[WSMan-Remoting in PowerShell Core][wsman-remoting]</span><span class="sxs-lookup"><span data-stu-id="afbb3-252">[WSMan Remoting in PowerShell Core][wsman-remoting]</span></span>

## <a name="upgrading-an-existing-installation"></a><span data-ttu-id="afbb3-253">Upgrade einer vorhandenen Installation</span><span class="sxs-lookup"><span data-stu-id="afbb3-253">Upgrading an existing installation</span></span>

<span data-ttu-id="afbb3-254">Für optimale Ergebnisse beim Upgrade sollten Sie dieselbe Installationsmethode verwenden, die Sie bei der ersten Installation von PowerShell verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="afbb3-254">For best results when upgrading, you should use the same install method you used when you first installed PowerShell.</span></span> <span data-ttu-id="afbb3-255">Bei jeder Installationsmethode wird PowerShell an einem anderen Speicherort installiert.</span><span class="sxs-lookup"><span data-stu-id="afbb3-255">Each installation method installs PowerShell in a different location.</span></span> <span data-ttu-id="afbb3-256">Wenn Sie nicht sicher sind, wie PowerShell installiert wurde, können Sie den Speicherort der Installation mit den Paketinformationen in diesem Artikel vergleichen.</span><span class="sxs-lookup"><span data-stu-id="afbb3-256">If you are not sure how PowerShell was installed, you can compare the installed location with the package information in this article.</span></span> <span data-ttu-id="afbb3-257">Wenn die Installation über das MSI-Paket erfolgt ist, finden Sie diese Informationen in der Systemsteuerung unter **Programme und Features**.</span><span class="sxs-lookup"><span data-stu-id="afbb3-257">If you installed via the MSI package, that information appears in the **Programs and Features** Control Panel.</span></span>

## <a name="installation-support"></a><span data-ttu-id="afbb3-258">Installationsunterstützung</span><span class="sxs-lookup"><span data-stu-id="afbb3-258">Installation support</span></span>

<span data-ttu-id="afbb3-259">Microsoft unterstützt die in diesem Dokument beschriebenen Installationsmethoden.</span><span class="sxs-lookup"><span data-stu-id="afbb3-259">Microsoft supports the installation methods in this document.</span></span> <span data-ttu-id="afbb3-260">Möglicherweise stehen andere Installationsmethoden aus anderen Quellen zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="afbb3-260">There may be other methods of installation available from other sources.</span></span> <span data-ttu-id="afbb3-261">Auch wenn diese Tools und Methoden funktionieren, kann Microsoft sie nicht unterstützen.</span><span class="sxs-lookup"><span data-stu-id="afbb3-261">While those tools and methods may work, Microsoft cannot support those methods.</span></span>

<!-- link references -->

[Vorschauversion]: https://aka.ms/powershell-release?tag=preview
[preview]: https://aka.ms/powershell-release?tag=preview
[Neueste]: https://aka.ms/powershell-release?tag=stable
[latest]: https://aka.ms/powershell-release?tag=stable
[ssh-remoting]: ../learn/remoting/SSH-Remoting-in-PowerShell-Core.md
[wsman-remoting]: ../learn/remoting/WSMan-Remoting-in-PowerShell-Core.md
[AppVeyor]: https://ci.appveyor.com/project/PowerShell/powershell
[winget]: /windows/package-manager/winget
[„andere Instanztechnik“]: ../learn/remoting/WSMan-Remoting-in-PowerShell-Core.md#executed-by-another-instance-of-powershell-on-behalf-of-the-instance-that-it-will-register
["another instance technique"]: ../learn/remoting/WSMan-Remoting-in-PowerShell-Core.md#executed-by-another-instance-of-powershell-on-behalf-of-the-instance-that-it-will-register
[Import-PSCoreRelease]: https://github.com/ms-iot/iot-adk-addonkit/blob/master/Tools/IoTCoreImaging/Docs/Import-PSCoreRelease.md#Import-PSCoreRelease
