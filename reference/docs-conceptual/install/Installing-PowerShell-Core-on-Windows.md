---
title: Installieren von PowerShell unter Windows
description: Informationen zur Installation von PowerShell unter Windows
ms.date: 09/14/2020
ms.openlocfilehash: 8f1b60ef6bfef5c2434b0affabb5e0e7af392b96
ms.sourcegitcommit: 30c0c1563f8e840f24b65297e907f3583d90e677
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90574452"
---
# <a name="installing-powershell-on-windows"></a><span data-ttu-id="9f2c8-103">Installieren von PowerShell unter Windows</span><span class="sxs-lookup"><span data-stu-id="9f2c8-103">Installing PowerShell on Windows</span></span>

<span data-ttu-id="9f2c8-104">Es gibt mehrere Möglichkeiten zum Installieren von PowerShell unter Windows.</span><span class="sxs-lookup"><span data-stu-id="9f2c8-104">There are multiple ways to install PowerShell in Windows.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9f2c8-105">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="9f2c8-105">Prerequisites</span></span>

<span data-ttu-id="9f2c8-106">Die neueste Version von PowerShell wird unter Windows 7 SP1, Windows Server 2008 R2 und höheren Versionen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="9f2c8-106">The latest release of PowerShell is supported on Windows 7 SP1, Server 2008 R2, and later versions.</span></span>

<span data-ttu-id="9f2c8-107">Zum Aktivieren des PowerShell-Remoting über WSMan müssen die folgenden Voraussetzungen erfüllt sein:</span><span class="sxs-lookup"><span data-stu-id="9f2c8-107">To enable PowerShell remoting over WSMan, the following prerequisites need to be met:</span></span>

- <span data-ttu-id="9f2c8-108">[Universal C-Runtime](https://www.microsoft.com/download/details.aspx?id=50410) muss unter Windows-Versionen vor Windows 10 installiert sein.</span><span class="sxs-lookup"><span data-stu-id="9f2c8-108">Install the [Universal C Runtime](https://www.microsoft.com/download/details.aspx?id=50410) on Windows versions predating Windows 10.</span></span> <span data-ttu-id="9f2c8-109">Die Runtime ist über einen direkten Download oder Windows-Update verfügbar.</span><span class="sxs-lookup"><span data-stu-id="9f2c8-109">It's available via direct download or Windows Update.</span></span> <span data-ttu-id="9f2c8-110">Auf vollständig gepatchten Systemen ist dieses Paket bereits installiert.</span><span class="sxs-lookup"><span data-stu-id="9f2c8-110">Fully patched systems already have this package installed.</span></span>
- <span data-ttu-id="9f2c8-111">Installieren Sie Windows Management Framework (WMF) 4.0 oder höher auf Windows 7 und Windows Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="9f2c8-111">Install the Windows Management Framework (WMF) 4.0 or newer on Windows 7 and Windows Server 2008 R2.</span></span> <span data-ttu-id="9f2c8-112">Weitere Informationen zu WMF erhalten Sie in der [WMF-Übersicht](/powershell/scripting/wmf/overview).</span><span class="sxs-lookup"><span data-stu-id="9f2c8-112">For more information about WMF, see [WMF Overview](/powershell/scripting/wmf/overview).</span></span>

## <a name="download-the-installer-package"></a><span data-ttu-id="9f2c8-113">Herunterladen des Installationspakets</span><span class="sxs-lookup"><span data-stu-id="9f2c8-113">Download the installer package</span></span>

<span data-ttu-id="9f2c8-114">Um PowerShell unter Windows zu installieren, laden Sie das Installationspaket von unserer GitHub-Seite [Releases][releases] herunter.</span><span class="sxs-lookup"><span data-stu-id="9f2c8-114">To install PowerShell on Windows, download the install package from our GitHub [releases][releases] page.</span></span> <span data-ttu-id="9f2c8-115">Scrollen Sie auf der Seite „Release“ nach unten zum Abschnitt **Assets**.</span><span class="sxs-lookup"><span data-stu-id="9f2c8-115">Scroll down to the **Assets** section of the Release page.</span></span> <span data-ttu-id="9f2c8-116">Der Abschnitt **Assets** ist möglicherweise zugeklappt, sodass Sie darauf klicken müssen, um ihn aufzuklappen.</span><span class="sxs-lookup"><span data-stu-id="9f2c8-116">The **Assets** section may be collapsed, so you may need to click to expand it.</span></span>

## <a name="installing-the-msi-package"></a><span data-ttu-id="9f2c8-117"><a id="msi" />Installieren des MSI-Pakets</span><span class="sxs-lookup"><span data-stu-id="9f2c8-117"><a id="msi" />Installing the MSI package</span></span>

<span data-ttu-id="9f2c8-118">Die MSI-Datei sieht so aus: `PowerShell-<version>-win-<os-arch>.msi`.</span><span class="sxs-lookup"><span data-stu-id="9f2c8-118">The MSI file looks like `PowerShell-<version>-win-<os-arch>.msi`.</span></span> <span data-ttu-id="9f2c8-119">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="9f2c8-119">For example:</span></span>

- `PowerShell-7.0.3-win-x64.msi`
- `PowerShell-7.0.3-win-x86.msi`

<span data-ttu-id="9f2c8-120">Sobald sie heruntergeladen wurde, führen Sie den Installer mit einem Doppelklick aus und befolgen die Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="9f2c8-120">Once downloaded, double-click the installer and follow the prompts.</span></span>

<span data-ttu-id="9f2c8-121">Das Installationsprogramm erstellt eine Verknüpfung im Windows-Startmenü.</span><span class="sxs-lookup"><span data-stu-id="9f2c8-121">The installer creates a shortcut in the Windows Start Menu.</span></span>

- <span data-ttu-id="9f2c8-122">Das Paket wird standardmäßig unter `$env:ProgramFiles\PowerShell\<version>` installiert</span><span class="sxs-lookup"><span data-stu-id="9f2c8-122">By default the package is installed to `$env:ProgramFiles\PowerShell\<version>`</span></span>
- <span data-ttu-id="9f2c8-123">Sie können PowerShell über das Startmenü oder über `$env:ProgramFiles\PowerShell\<version>\pwsh.exe` starten</span><span class="sxs-lookup"><span data-stu-id="9f2c8-123">You can launch PowerShell via the Start Menu or `$env:ProgramFiles\PowerShell\<version>\pwsh.exe`</span></span>

> [!NOTE]
> <span data-ttu-id="9f2c8-124">PowerShell 7 wird in ein neues Verzeichnis installiert und parallel mit Windows PowerShell 5.1 ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="9f2c8-124">PowerShell 7 installs to a new directory and runs side-by-side with Windows PowerShell 5.1.</span></span> <span data-ttu-id="9f2c8-125">Für PowerShell Core 6.x ist PowerShell 7 ein direktes Upgrade, durch das PowerShell Core 6.x entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="9f2c8-125">For PowerShell Core 6.x, PowerShell 7 is an in-place upgrade that removes PowerShell Core 6.x.</span></span>
>
> - <span data-ttu-id="9f2c8-126">PowerShell 7 wird in `$env:ProgramFiles\PowerShell\7` installiert.</span><span class="sxs-lookup"><span data-stu-id="9f2c8-126">PowerShell 7 is installed to `$env:ProgramFiles\PowerShell\7`</span></span>
> - <span data-ttu-id="9f2c8-127">Der Ordner `$env:ProgramFiles\PowerShell\7` wird `$env:PATH` hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="9f2c8-127">The `$env:ProgramFiles\PowerShell\7` folder is added to `$env:PATH`</span></span>
> - <span data-ttu-id="9f2c8-128">Der Ordner `$env:ProgramFiles\PowerShell\6` wird gelöscht.</span><span class="sxs-lookup"><span data-stu-id="9f2c8-128">The `$env:ProgramFiles\PowerShell\6` folder is deleted</span></span>
>
> <span data-ttu-id="9f2c8-129">Wenn Sie PowerShell 6 und PowerShell 7 parallel ausführen müssen, installieren Sie PowerShell 6 mithilfe der [ZIP-Installationsmethode](#zip) neu.</span><span class="sxs-lookup"><span data-stu-id="9f2c8-129">If you need to run PowerShell 6 side-by-side with PowerShell 7, reinstall PowerShell 6 using the [ZIP install](#zip) method.</span></span>

### <a name="administrative-install-from-the-command-line"></a><span data-ttu-id="9f2c8-130">Administrative Installation über die Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="9f2c8-130">Administrative install from the command line</span></span>

<span data-ttu-id="9f2c8-131">MSI-Pakete können über die Befehlszeile installiert werden, sodass Administratoren Pakete ohne Benutzerinteraktion bereitstellen können.</span><span class="sxs-lookup"><span data-stu-id="9f2c8-131">MSI packages can be installed from the command line allowing administrators to deploy packages without user interaction.</span></span> <span data-ttu-id="9f2c8-132">Das MSI-Paket enthält die folgenden Eigenschaften zum Steuern der Installationsoptionen:</span><span class="sxs-lookup"><span data-stu-id="9f2c8-132">The MSI package includes the following properties to control the installation options:</span></span>

- <span data-ttu-id="9f2c8-133">**ADD_EXPLORER_CONTEXT_MENU_OPENPOWERSHELL** – Diese Eigenschaft steuert die Option zum Hinzufügen des Elements **PowerShell öffnen** zum Kontextmenü im Windows-Explorer.</span><span class="sxs-lookup"><span data-stu-id="9f2c8-133">**ADD_EXPLORER_CONTEXT_MENU_OPENPOWERSHELL** - This property controls the option for adding the **Open PowerShell** item to the context menu in Windows Explorer.</span></span>
- <span data-ttu-id="9f2c8-134">**ENABLE_PSREMOTING** – Diese Eigenschaft steuert die Option zum Aktivieren von PowerShell-Remoting während der Installation.</span><span class="sxs-lookup"><span data-stu-id="9f2c8-134">**ENABLE_PSREMOTING** - This property controls the option for enabling PowerShell remoting during installation.</span></span>
- <span data-ttu-id="9f2c8-135">**REGISTER_MANIFEST** – Diese Eigenschaft steuert die Option zum Registrieren des Manifests für Windows-Ereignisprotokollierung.</span><span class="sxs-lookup"><span data-stu-id="9f2c8-135">**REGISTER_MANIFEST** - This property controls the option for registering the Windows Event Logging manifest.</span></span>

<span data-ttu-id="9f2c8-136">Das folgenden Beispiel zeigt, wie PowerShell mit allen aktivierten Installationsoptionen im Hintergrund installiert wird.</span><span class="sxs-lookup"><span data-stu-id="9f2c8-136">The following example shows how to silently install PowerShell with all the install options enabled.</span></span>

```powershell
msiexec.exe /package PowerShell-7.0.3-win-x64.msi /quiet ADD_EXPLORER_CONTEXT_MENU_OPENPOWERSHELL=1 ENABLE_PSREMOTING=1 REGISTER_MANIFEST=1
```

<span data-ttu-id="9f2c8-137">Eine vollständige Liste der Befehlszeilenoptionen für `Msiexec.exe` finden Sie unter [Befehlszeilenoptionen](/windows/desktop/Msi/command-line-options).</span><span class="sxs-lookup"><span data-stu-id="9f2c8-137">For a full list of command-line options for `Msiexec.exe`, see [Command line options](/windows/desktop/Msi/command-line-options).</span></span>

### <a name="registry-keys-created-during-installation"></a><span data-ttu-id="9f2c8-138">Während der Installation erstellte Registrierungsschlüssel</span><span class="sxs-lookup"><span data-stu-id="9f2c8-138">Registry keys created during installation</span></span>

<span data-ttu-id="9f2c8-139">Ab PowerShell 7.1 erstellt das MSI-Paket Registrierungsschlüssel, die den Installationsort und die PowerShell-Version speichern.</span><span class="sxs-lookup"><span data-stu-id="9f2c8-139">Beginning in PowerShell 7.1, the MSI package creates registry keys that store the installation location and version of PowerShell.</span></span> <span data-ttu-id="9f2c8-140">Diese Werte befinden sich in `HKLM\Software\Microsoft\PowerShellCore\InstalledVersions\<GUID>`.</span><span class="sxs-lookup"><span data-stu-id="9f2c8-140">These values are located in `HKLM\Software\Microsoft\PowerShellCore\InstalledVersions\<GUID>`.</span></span> <span data-ttu-id="9f2c8-141">Der Wert von `<GUID>` ist für jeden Buildtyp (Release oder Vorschau), Hauptversion und Architektur eindeutig.</span><span class="sxs-lookup"><span data-stu-id="9f2c8-141">The value of `<GUID>` is unique for each build type (release or preview), major version, and architecture.</span></span>

|    <span data-ttu-id="9f2c8-142">Release</span><span class="sxs-lookup"><span data-stu-id="9f2c8-142">Release</span></span>    | <span data-ttu-id="9f2c8-143">Aufbau</span><span class="sxs-lookup"><span data-stu-id="9f2c8-143">Architecture</span></span> |                                          <span data-ttu-id="9f2c8-144">Registrierungsschlüssel</span><span class="sxs-lookup"><span data-stu-id="9f2c8-144">Registry Key</span></span>                                           |
| ------------- | :----------: | ----------------------------------------------------------------------------------------------- |
| <span data-ttu-id="9f2c8-145">Release 7.1.x</span><span class="sxs-lookup"><span data-stu-id="9f2c8-145">7.1.x Release</span></span> |     <span data-ttu-id="9f2c8-146">x86</span><span class="sxs-lookup"><span data-stu-id="9f2c8-146">x86</span></span>      | `HKLM\Software\Microsoft\PowerShellCore\InstalledVersions\1d00683b-0f84-4db8-a64f-2f98ad42fe06` |
| <span data-ttu-id="9f2c8-147">Release 7.1.x</span><span class="sxs-lookup"><span data-stu-id="9f2c8-147">7.1.x Release</span></span> |     <span data-ttu-id="9f2c8-148">x64</span><span class="sxs-lookup"><span data-stu-id="9f2c8-148">x64</span></span>      | `HKLM\Software\Microsoft\PowerShellCore\InstalledVersions\31ab5147-9a97-4452-8443-d9709f0516e1` |
| <span data-ttu-id="9f2c8-149">Vorschau 7.1.x</span><span class="sxs-lookup"><span data-stu-id="9f2c8-149">7.1.x Preview</span></span> |     <span data-ttu-id="9f2c8-150">x86</span><span class="sxs-lookup"><span data-stu-id="9f2c8-150">x86</span></span>      | `HKLM\Software\Microsoft\PowerShellCore\InstalledVersions\86abcfbd-1ccc-4a88-b8b2-0facfde29094` |
| <span data-ttu-id="9f2c8-151">Vorschau 7.1.x</span><span class="sxs-lookup"><span data-stu-id="9f2c8-151">7.1.x Preview</span></span> |     <span data-ttu-id="9f2c8-152">x64</span><span class="sxs-lookup"><span data-stu-id="9f2c8-152">x64</span></span>      | `HKLM\Software\Microsoft\PowerShellCore\InstalledVersions\39243d76-adaf-42b1-94fb-16ecf83237c8` |

<span data-ttu-id="9f2c8-153">Dies kann von Administratoren und Entwicklern verwendet werden, um den Pfad zu PowerShell zu finden.</span><span class="sxs-lookup"><span data-stu-id="9f2c8-153">This can be used by administrators and developers to find the path to PowerShell.</span></span> <span data-ttu-id="9f2c8-154">Die `<GUID>`-Werte sind für alle Vorschau- und Nebenversionen identisch.</span><span class="sxs-lookup"><span data-stu-id="9f2c8-154">The `<GUID>` values will be the same for all preview and minor version releases.</span></span> <span data-ttu-id="9f2c8-155">Die `<GUID>`-Werte werden für jede Hauptversion geändert.</span><span class="sxs-lookup"><span data-stu-id="9f2c8-155">The `<GUID>` values are changed for each major release.</span></span>

## <a name="installing-the-msix-package"></a><span data-ttu-id="9f2c8-156"><a id="msix" />Installieren des MSIX-Pakets</span><span class="sxs-lookup"><span data-stu-id="9f2c8-156"><a id="msix" />Installing the MSIX package</span></span>

> [!NOTE]
> <span data-ttu-id="9f2c8-157">Das MSIX-Paket wird zurzeit nicht offiziell unterstützt.</span><span class="sxs-lookup"><span data-stu-id="9f2c8-157">The MSIX package is not officially supported at this time.</span></span> <span data-ttu-id="9f2c8-158">Wir erstellen das Paket weiterhin nur zu internen Testzwecken.</span><span class="sxs-lookup"><span data-stu-id="9f2c8-158">We continue to build the package for internal testing purposes only.</span></span>

<span data-ttu-id="9f2c8-159">Um das MSIX-Paket manuell auf einem Windows 10-Client zu installieren, laden Sie das MSIX-Paket von der GitHub-Seite mit [Releases][releases] herunter.</span><span class="sxs-lookup"><span data-stu-id="9f2c8-159">To manually install the MSIX package on a Windows 10 client, download the MSIX package from our GitHub [releases][releases] page.</span></span> <span data-ttu-id="9f2c8-160">Scrollen Sie nach unten zum Abschnitt **Assets** des Release, das Sie installieren möchten.</span><span class="sxs-lookup"><span data-stu-id="9f2c8-160">Scroll down to the **Assets** section of the Release you want to install.</span></span> <span data-ttu-id="9f2c8-161">Der Abschnitt „Assets“ ist möglicherweise reduziert, sodass Sie klicken müssen, um ihn zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="9f2c8-161">The Assets section may be collapsed, so you may need to click to expand it.</span></span>

<span data-ttu-id="9f2c8-162">Die MSIX-Datei sieht so aus: `PowerShell-<version>-win-<os-arch>.msix`</span><span class="sxs-lookup"><span data-stu-id="9f2c8-162">The MSIX file looks like this - `PowerShell-<version>-win-<os-arch>.msix`</span></span>

<span data-ttu-id="9f2c8-163">Zum Installieren des Pakets müssen Sie das Cmdlet `Add-AppxPackage` verwenden:</span><span class="sxs-lookup"><span data-stu-id="9f2c8-163">To install the package, you must use the `Add-AppxPackage` cmdlet.</span></span>

```powershell
Add-AppxPackage PowerShell-<version>-win-<os-arch>.msix
```

## <a name="installing-the-zip-package"></a><span data-ttu-id="9f2c8-164"><a id="zip" />Installieren des ZIP-Pakets</span><span class="sxs-lookup"><span data-stu-id="9f2c8-164"><a id="zip" />Installing the ZIP package</span></span>

<span data-ttu-id="9f2c8-165">Binäre PowerShell ZIP-Archive werden zur Verfügung gestellt, um erweiterte Bereitstellungsszenarios zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="9f2c8-165">PowerShell binary ZIP archives are provided to enable advanced deployment scenarios.</span></span> <span data-ttu-id="9f2c8-166">Bei der Installation des ZIP-Archivs werden die Voraussetzungen nicht wie bei den MSI-Paketen überprüft.</span><span class="sxs-lookup"><span data-stu-id="9f2c8-166">Installing the ZIP archive doesn't check the prerequisites like the MSI packages do.</span></span> <span data-ttu-id="9f2c8-167">Laden Sie das ZIP-Archiv von der Seite [Releases][releases] herunter.</span><span class="sxs-lookup"><span data-stu-id="9f2c8-167">Download the ZIP archive from the [releases][releases] page.</span></span> <span data-ttu-id="9f2c8-168">Je nachdem, wie Sie die Datei herunterladen, müssen Sie die Blockierung der Datei mit dem Cmdlet `Unblock-File` aufheben.</span><span class="sxs-lookup"><span data-stu-id="9f2c8-168">Depending on how you download the file you may need to unblock the file using the `Unblock-File` cmdlet.</span></span> <span data-ttu-id="9f2c8-169">Entpacken Sie den Inhalt an den Speicherort Ihrer Wahl, und führen Sie `pwsh.exe` von dort aus.</span><span class="sxs-lookup"><span data-stu-id="9f2c8-169">Unzip the contents to the location of your choice and run `pwsh.exe` from there.</span></span> <span data-ttu-id="9f2c8-170">Damit Remoting über WSMan einwandfrei funktioniert, müssen die [Voraussetzungen](#prerequisites) unbedingt erfüllt sein.</span><span class="sxs-lookup"><span data-stu-id="9f2c8-170">For remoting over WSMan to work properly, ensure that you've met the [prerequisites](#prerequisites).</span></span>

## <a name="deploying-on-windows-10-iot-enterprise"></a><span data-ttu-id="9f2c8-171">Bereitstellung unter Windows 10 IoT Enterprise</span><span class="sxs-lookup"><span data-stu-id="9f2c8-171">Deploying on Windows 10 IoT Enterprise</span></span>

<span data-ttu-id="9f2c8-172">Bei Windows 10 IoT Enterprise ist Windows PowerShell bereits im Funktionsumfang enthalten, sodass PowerShell 7 bereitgestellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="9f2c8-172">Windows 10 IoT Enterprise comes with Windows PowerShell, which we can use to deploy PowerShell 7.</span></span>

1. <span data-ttu-id="9f2c8-173">Erstellen Sie `PSSession` auf dem Zielgerät.</span><span class="sxs-lookup"><span data-stu-id="9f2c8-173">Create `PSSession` to target device</span></span>

   ```powershell
   Set-Item -Path WSMan:\localhost\Client\TrustedHosts <deviceip>
   $S = New-PSSession -ComputerName <deviceIp> -Credential Administrator
   ```

1. <span data-ttu-id="9f2c8-174">Kopieren Sie das ZIP-Paket auf das Gerät.</span><span class="sxs-lookup"><span data-stu-id="9f2c8-174">Copy the ZIP package to the device</span></span>

   ```powershell
   # change the destination to however you had partitioned it with sufficient
   # space for the zip and the unzipped contents
   # the path should be local to the device
   Copy-Item .\PowerShell-<version>-win-<os-arch>.zip -Destination u:\users\administrator\Downloads -ToSession $s
   ```

1. <span data-ttu-id="9f2c8-175">Stellen Sie eine Verbindung mit dem Gerät her, und erweitern Sie das Archiv.</span><span class="sxs-lookup"><span data-stu-id="9f2c8-175">Connect to the device and expand the archive</span></span>

   ```powershell
   Enter-PSSession $s
   Set-Location u:\users\administrator\downloads
   Expand-Archive .\PowerShell-<version>-win-<os-arch>.zip
   ```

1. <span data-ttu-id="9f2c8-176">Richten Sie Remoting für PowerShell 7 ein.</span><span class="sxs-lookup"><span data-stu-id="9f2c8-176">Set up remoting to PowerShell 7</span></span>

   ```powershell
   Set-Location .\PowerShell-<version>-win-<os-arch>
   # Be sure to use the -PowerShellHome parameter otherwise it'll try to create a new
   # endpoint with Windows PowerShell 5.1
   .\Install-PowerShellRemoting.ps1 -PowerShellHome .
   # You'll get an error message and will be disconnected from the device because it has to restart WinRM
   ```

1. <span data-ttu-id="9f2c8-177">Stellen Sie eine Verbindung mit dem PowerShell 7-Endpunkt auf dem Gerät her.</span><span class="sxs-lookup"><span data-stu-id="9f2c8-177">Connect to PowerShell 7 endpoint on device</span></span>

   ```powershell
   # Be sure to use the -Configuration parameter.  If you omit it, you will connect to Windows PowerShell 5.1
   Enter-PSSession -ComputerName <deviceIp> -Credential Administrator -Configuration powershell.<version>
   ```

## <a name="deploying-on-windows-10-iot-core"></a><span data-ttu-id="9f2c8-178">Bereitstellung unter Windows 10 IoT Core</span><span class="sxs-lookup"><span data-stu-id="9f2c8-178">Deploying on Windows 10 IoT Core</span></span>

<span data-ttu-id="9f2c8-179">Bei Windows 10 IoT Core wird Windows PowerShell hinzugefügt, wenn Sie das Feature *IOT_POWERSHELL* aufnehmen. Über dieses Feature kann PowerShell 7 bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="9f2c8-179">Windows 10 IoT Core adds Windows PowerShell when you include *IOT_POWERSHELL* feature, which we can use to deploy PowerShell 7.</span></span>
<span data-ttu-id="9f2c8-180">Die oben beschriebenen Schritte für Windows 10 IoT Enterprise können auch für IoT Core ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="9f2c8-180">The steps defined above for Windows 10 IoT Enterprise can be followed for IoT Core as well.</span></span>

<span data-ttu-id="9f2c8-181">Verwenden Sie zum Hinzufügen der aktuellen PowerShell-Version im Image den Befehl [Import-PSCoreRelease](https://github.com/ms-iot/iot-adk-addonkit/blob/master/Tools/IoTCoreImaging/Docs/Import-PSCoreRelease.md#Import-PSCoreRelease). Mit diesem Befehl wird das Paket im Arbeitsbereich eingefügt und das Feature *OPENSRC_POWERSHELL* zu Ihrem Image hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="9f2c8-181">For adding the latest powershell in the shipping image, use [Import-PSCoreRelease](https://github.com/ms-iot/iot-adk-addonkit/blob/master/Tools/IoTCoreImaging/Docs/Import-PSCoreRelease.md#Import-PSCoreRelease) command to include the package in the workarea and add *OPENSRC_POWERSHELL* feature to your image.</span></span>

> [!NOTE]
> <span data-ttu-id="9f2c8-182">Bei der ARM64-Architektur wird Windows PowerShell nicht hinzugefügt, wenn Sie *IOT_POWERSHELL* einfügen.</span><span class="sxs-lookup"><span data-stu-id="9f2c8-182">For ARM64 architecture, Windows Powershell is not added when you include *IOT_POWERSHELL*.</span></span> <span data-ttu-id="9f2c8-183">Daher funktioniert die ZIP-basierte Installation nicht.</span><span class="sxs-lookup"><span data-stu-id="9f2c8-183">So the zip based install will not work.</span></span>
> <span data-ttu-id="9f2c8-184">Sie müssen den Befehl „Import-PSCoreRelease“ verwenden, um PowerShell im Image hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="9f2c8-184">You will need to use Import-PSCoreRelease command to add it in the image.</span></span>

## <a name="deploying-on-nano-server"></a><span data-ttu-id="9f2c8-185">Bereitstellen auf Nano Server</span><span class="sxs-lookup"><span data-stu-id="9f2c8-185">Deploying on Nano Server</span></span>

<span data-ttu-id="9f2c8-186">Diese Anweisungen gehen davon aus, dass der Nano Server ein „monitorloses“ Betriebssystem ist, unter dem bereits eine Version von PowerShell ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="9f2c8-186">These instructions assume that the Nano Server is a "headless" OS that has a version of PowerShell is already running on it.</span></span> <span data-ttu-id="9f2c8-187">Weitere Informationen finden Sie in der [Dokumentation zu Nano Server Image Builder](/windows-server/get-started/deploy-nano-server).</span><span class="sxs-lookup"><span data-stu-id="9f2c8-187">For more information, see the [Nano Server Image Builder](/windows-server/get-started/deploy-nano-server) documentation.</span></span>

<span data-ttu-id="9f2c8-188">PowerShell-Binärdateien können auf zwei verschiedene Arten bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="9f2c8-188">PowerShell binaries can be deployed using two different methods.</span></span>

1. <span data-ttu-id="9f2c8-189">Offline: Binden Sie die Nano Server-VHD ein, und entpacken Sie den Inhalt der ZIP-Datei an dem von Ihnen gewünschten Speicherort in dem eingebundenen Image.</span><span class="sxs-lookup"><span data-stu-id="9f2c8-189">Offline - Mount the Nano Server VHD and unzip the contents of the zip file to your chosen location within the mounted image.</span></span>
1. <span data-ttu-id="9f2c8-190">Online: Übertragen Sie die ZIP-Datei über eine PowerShell-Sitzung, und entpacken Sie sie an dem von Ihnen gewünschten Speicherort.</span><span class="sxs-lookup"><span data-stu-id="9f2c8-190">Online - Transfer the zip file over a PowerShell Session and unzip it in your chosen location.</span></span>

<span data-ttu-id="9f2c8-191">In beiden Fällen benötigen Sie das ZIP-Releasepaket für Windows 10 x64.</span><span class="sxs-lookup"><span data-stu-id="9f2c8-191">In both cases, you need the Windows 10 x64 ZIP release package.</span></span> <span data-ttu-id="9f2c8-192">Führen Sie die Befehle in einer „Administrator“-Instanz von PowerShell aus.</span><span class="sxs-lookup"><span data-stu-id="9f2c8-192">Run the commands within an "Administrator" instance of PowerShell.</span></span>

### <a name="offline-deployment-of-powershell"></a><span data-ttu-id="9f2c8-193">Offlinebereitstellung von PowerShell</span><span class="sxs-lookup"><span data-stu-id="9f2c8-193">Offline Deployment of PowerShell</span></span>

1. <span data-ttu-id="9f2c8-194">Verwenden Sie Ihr bevorzugtes ZIP-Hilfsprogramm, um das Paket in ein Verzeichnis im eingebundenen Nano Server-Image zu entpacken.</span><span class="sxs-lookup"><span data-stu-id="9f2c8-194">Use your favorite zip utility to unzip the package to a directory within the mounted Nano Server image.</span></span>
1. <span data-ttu-id="9f2c8-195">Heben Sie die Bereitstellung des Images auf, und starten Sie es.</span><span class="sxs-lookup"><span data-stu-id="9f2c8-195">Unmount the image and boot it.</span></span>
1. <span data-ttu-id="9f2c8-196">Stellen Sie eine Verbindung mit der integrierten Instanz von Windows PowerShell her.</span><span class="sxs-lookup"><span data-stu-id="9f2c8-196">Connect to the built-in instance of Windows PowerShell.</span></span>
1. <span data-ttu-id="9f2c8-197">Befolgen Sie die Anweisungen, um einen Remoting-Endpunkt mithilfe der [„Andere Instanz-Methode“](../learn/remoting/wsman-remoting-in-powershell-core.md#executed-by-another-instance-of-powershell-on-behalf-of-the-instance-that-it-will-register) zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="9f2c8-197">Follow the instructions to create a remoting endpoint using the ["another instance technique"](../learn/remoting/wsman-remoting-in-powershell-core.md#executed-by-another-instance-of-powershell-on-behalf-of-the-instance-that-it-will-register).</span></span>

### <a name="online-deployment-of-powershell"></a><span data-ttu-id="9f2c8-198">Onlinebereitstellung von PowerShell</span><span class="sxs-lookup"><span data-stu-id="9f2c8-198">Online Deployment of PowerShell</span></span>

<span data-ttu-id="9f2c8-199">Stellen Sie PowerShell mithilfe der folgenden Schritte für Nano Server bereit.</span><span class="sxs-lookup"><span data-stu-id="9f2c8-199">Deploy PowerShell to Nano Server using the following steps.</span></span>

- <span data-ttu-id="9f2c8-200">Herstellen einer Verbindung mit der integrierten Instanz von Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9f2c8-200">Connect to the built-in instance of Windows PowerShell</span></span>

  ```powershell
  $session = New-PSSession -ComputerName <Nano Server IP address> -Credential <An Administrator account on the system>
  ```

- <span data-ttu-id="9f2c8-201">Kopieren Sie die Datei in die Nano Server-Instanz.</span><span class="sxs-lookup"><span data-stu-id="9f2c8-201">Copy the file to the Nano Server instance</span></span>

  ```powershell
  Copy-Item <local PS Core download location>\powershell-<version>-win-x64.zip c:\ -ToSession $session
  ```

- <span data-ttu-id="9f2c8-202">Geben Sie die Sitzung ein.</span><span class="sxs-lookup"><span data-stu-id="9f2c8-202">Enter the session</span></span>

  ```powershell
  Enter-PSSession $session
  ```

- <span data-ttu-id="9f2c8-203">Extrahieren Sie die ZIP-Datei.</span><span class="sxs-lookup"><span data-stu-id="9f2c8-203">Extract the ZIP file</span></span>

  ```powershell
  # Insert the appropriate version.
  Expand-Archive -Path C:\powershell-<version>-win-x64.zip -DestinationPath "C:\PowerShell_<version>"
  ```

- <span data-ttu-id="9f2c8-204">Befolgen Sie die Anweisungen, wenn Sie auf WSMan basierendes Remoting verwenden möchten, um einen Remoting-Endpunkt mithilfe der [„Andere Instanz-Methode“](../learn/remoting/WSMan-Remoting-in-PowerShell-Core.md#executed-by-another-instance-of-powershell-on-behalf-of-the-instance-that-it-will-register) zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="9f2c8-204">If you want WSMan-based remoting, follow the instructions to create a remoting endpoint using the ["another instance technique"](../learn/remoting/WSMan-Remoting-in-PowerShell-Core.md#executed-by-another-instance-of-powershell-on-behalf-of-the-instance-that-it-will-register).</span></span>

## <a name="install-as-a-net-global-tool"></a><span data-ttu-id="9f2c8-205">Installieren als globales .NET-Tool</span><span class="sxs-lookup"><span data-stu-id="9f2c8-205">Install as a .NET Global tool</span></span>

<span data-ttu-id="9f2c8-206">Wenn Sie das [.NET Core SDK](/dotnet/core/sdk) bereits installiert haben, können Sie PowerShell einfach als [globales .NET-Tool](/dotnet/core/tools/global-tools) installieren.</span><span class="sxs-lookup"><span data-stu-id="9f2c8-206">If you already have the [.NET Core SDK](/dotnet/core/sdk) installed, it's easy to install PowerShell as a [.NET Global tool](/dotnet/core/tools/global-tools).</span></span>

```
dotnet tool install --global PowerShell
```

<span data-ttu-id="9f2c8-207">Der .NET-Toolinstaller fügt `$env:USERPROFILE\dotnet\tools` Ihrer `$env:PATH`-Umgebungsvariablen hinzu.</span><span class="sxs-lookup"><span data-stu-id="9f2c8-207">The dotnet tool installer adds `$env:USERPROFILE\dotnet\tools` to your `$env:PATH` environment variable.</span></span> <span data-ttu-id="9f2c8-208">Die aktuell ausgeführte Shell verfügt jedoch nicht über die aktualisierte Umgebungsvariable `$env:PATH`.</span><span class="sxs-lookup"><span data-stu-id="9f2c8-208">However, the currently running shell doesn't have the updated `$env:PATH`.</span></span> <span data-ttu-id="9f2c8-209">Sie können PowerShell über eine neue Shell starten, indem Sie `pwsh` eingeben.</span><span class="sxs-lookup"><span data-stu-id="9f2c8-209">You can start PowerShell from a new shell by typing `pwsh`.</span></span>

## <a name="install-powershell-via-winget"></a><span data-ttu-id="9f2c8-210">Installieren von PowerShell über Winget</span><span class="sxs-lookup"><span data-stu-id="9f2c8-210">Install PowerShell via Winget</span></span>

<span data-ttu-id="9f2c8-211">Mit dem Befehlszeilentool `winget` können Entwickler Anwendungen auf Windows 10-Computern ermitteln, installieren, aktualisieren, entfernen und konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="9f2c8-211">The `winget` command-line tool enables developers to discover, install, upgrade, remove and configure applications on Windows 10 computers.</span></span> <span data-ttu-id="9f2c8-212">Dieses Tool ist die Clientschnittstelle für den Windows-Paket-Manager-Dienst.</span><span class="sxs-lookup"><span data-stu-id="9f2c8-212">This tool is the client interface to the Windows Package Manager service.</span></span>

> [!NOTE]
> <span data-ttu-id="9f2c8-213">Das `winget`-Tool befindet sich zurzeit in der Vorschau.</span><span class="sxs-lookup"><span data-stu-id="9f2c8-213">The `winget` tool is currently a preview.</span></span> <span data-ttu-id="9f2c8-214">Zurzeit sind nicht alle geplanten Funktionen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="9f2c8-214">Not all planned functionality is available at this time.</span></span>
> <span data-ttu-id="9f2c8-215">Die Optionen und Features des Tools unterliegen Änderungen.</span><span class="sxs-lookup"><span data-stu-id="9f2c8-215">The tool's options and features are subject to change.</span></span> <span data-ttu-id="9f2c8-216">Diese Methode sollten Sie nicht in einem Produktionsbereitstellungsszenario verwenden.</span><span class="sxs-lookup"><span data-stu-id="9f2c8-216">You should not use this method in a production deployment scenario.</span></span> <span data-ttu-id="9f2c8-217">Eine Liste der Systemanforderungen und Installationsanweisungen finden Sie in der Dokumentation zu [winget].</span><span class="sxs-lookup"><span data-stu-id="9f2c8-217">See the [winget] documentation for a list of system requirements and install instructions.</span></span>

<span data-ttu-id="9f2c8-218">Die folgenden Befehle können verwendet werden, um PowerShell mithilfe der veröffentlichten `winget`-Pakete zu installieren:</span><span class="sxs-lookup"><span data-stu-id="9f2c8-218">The following commands can be used to install PowerShell using the published `winget` packages:</span></span>

1. <span data-ttu-id="9f2c8-219">Suchen nach der neuesten Version von PowerShell</span><span class="sxs-lookup"><span data-stu-id="9f2c8-219">Search for the latest version of PowerShell</span></span>

   ```powershell
   winget search Microsoft.PowerShell
   ```

   ```Output
   Name               Id                           Version
   ---------------------------------------------------------------
   PowerShell         Microsoft.PowerShell         7.0.3
   PowerShell-Preview Microsoft.PowerShell-Preview 7.1.0-preview.5
   ```

1. <span data-ttu-id="9f2c8-220">Installieren einer PowerShell-Version mithilfe des `--exact`-Parameters</span><span class="sxs-lookup"><span data-stu-id="9f2c8-220">Install a version of PowerShell using the `--exact` parameter</span></span>

   ```powershell
   winget install --name PowerShell --exact
   winget install --name PowerShell-Preview --exact
   ```

## <a name="how-to-create-a-remoting-endpoint"></a><span data-ttu-id="9f2c8-221">Vorgehensweise zum Erstellen eines Remoting-Endpunkts</span><span class="sxs-lookup"><span data-stu-id="9f2c8-221">How to create a remoting endpoint</span></span>

<span data-ttu-id="9f2c8-222">PowerShell unterstützt das PowerShell-Remotingprotokoll (PSRP) über WSMan und SSH.</span><span class="sxs-lookup"><span data-stu-id="9f2c8-222">PowerShell supports the PowerShell Remoting Protocol (PSRP) over both WSMan and SSH.</span></span> <span data-ttu-id="9f2c8-223">Weitere Informationen finden Sie unter</span><span class="sxs-lookup"><span data-stu-id="9f2c8-223">For more information, see:</span></span>

- <span data-ttu-id="9f2c8-224">[SSH-Remoting in PowerShell Core][ssh-remoting]</span><span class="sxs-lookup"><span data-stu-id="9f2c8-224">[SSH Remoting in PowerShell Core][ssh-remoting]</span></span>
- <span data-ttu-id="9f2c8-225">[WSMan-Remoting in PowerShell Core][wsman-remoting]</span><span class="sxs-lookup"><span data-stu-id="9f2c8-225">[WSMan Remoting in PowerShell Core][wsman-remoting]</span></span>

## <a name="installation-support"></a><span data-ttu-id="9f2c8-226">Installationsunterstützung</span><span class="sxs-lookup"><span data-stu-id="9f2c8-226">Installation support</span></span>

<span data-ttu-id="9f2c8-227">Microsoft unterstützt die in diesem Dokument beschriebenen Installationsmethoden.</span><span class="sxs-lookup"><span data-stu-id="9f2c8-227">Microsoft supports the installation methods in this document.</span></span> <span data-ttu-id="9f2c8-228">Möglicherweise stehen andere Installationsmethoden aus anderen Quellen zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="9f2c8-228">There may be other methods of installation available from other sources.</span></span> <span data-ttu-id="9f2c8-229">Auch wenn diese Tools und Methoden funktionieren, kann Microsoft sie nicht unterstützen.</span><span class="sxs-lookup"><span data-stu-id="9f2c8-229">While those tools and methods may work, Microsoft cannot support those methods.</span></span>

<!-- link references -->

[releases]: https://github.com/PowerShell/PowerShell/releases
[ssh-remoting]: ../learn/remoting/SSH-Remoting-in-PowerShell-Core.md
[wsman-remoting]: ../learn/remoting/WSMan-Remoting-in-PowerShell-Core.md
[AppVeyor]: https://ci.appveyor.com/project/PowerShell/powershell
[winget]: /windows/package-manager/winget
