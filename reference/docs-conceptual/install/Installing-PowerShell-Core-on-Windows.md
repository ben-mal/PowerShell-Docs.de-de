---
title: Installieren von PowerShell unter Windows
description: Informationen zur Installation von PowerShell unter Windows
ms.date: 11/11/2020
ms.openlocfilehash: 039db904a315bd3ad3f4e1358d414c98c3a84be5
ms.sourcegitcommit: 7f712e12ec5b3f3f3e695da804b050ea0ce58b3a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "94661425"
---
# <a name="installing-powershell-on-windows"></a><span data-ttu-id="75fa1-103">Installieren von PowerShell unter Windows</span><span class="sxs-lookup"><span data-stu-id="75fa1-103">Installing PowerShell on Windows</span></span>

<span data-ttu-id="75fa1-104">Es gibt mehrere Möglichkeiten zum Installieren von PowerShell unter Windows.</span><span class="sxs-lookup"><span data-stu-id="75fa1-104">There are multiple ways to install PowerShell in Windows.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="75fa1-105">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="75fa1-105">Prerequisites</span></span>

<span data-ttu-id="75fa1-106">Die neueste Version von PowerShell wird unter Windows 7 SP1, Windows Server 2008 R2 und höheren Versionen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="75fa1-106">The latest release of PowerShell is supported on Windows 7 SP1, Server 2008 R2, and later versions.</span></span>

<span data-ttu-id="75fa1-107">Zum Aktivieren des PowerShell-Remoting über WSMan müssen die folgenden Voraussetzungen erfüllt sein:</span><span class="sxs-lookup"><span data-stu-id="75fa1-107">To enable PowerShell remoting over WSMan, the following prerequisites need to be met:</span></span>

- <span data-ttu-id="75fa1-108">[Universal C-Runtime](https://www.microsoft.com/download/details.aspx?id=50410) muss unter Windows-Versionen vor Windows 10 installiert sein.</span><span class="sxs-lookup"><span data-stu-id="75fa1-108">Install the [Universal C Runtime](https://www.microsoft.com/download/details.aspx?id=50410) on Windows versions predating Windows 10.</span></span> <span data-ttu-id="75fa1-109">Die Runtime ist über einen direkten Download oder Windows-Update verfügbar.</span><span class="sxs-lookup"><span data-stu-id="75fa1-109">It's available via direct download or Windows Update.</span></span> <span data-ttu-id="75fa1-110">Auf vollständig gepatchten Systemen ist dieses Paket bereits installiert.</span><span class="sxs-lookup"><span data-stu-id="75fa1-110">Fully patched systems already have this package installed.</span></span>
- <span data-ttu-id="75fa1-111">Installieren Sie Windows Management Framework (WMF) 4.0 oder höher auf Windows 7 und Windows Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="75fa1-111">Install the Windows Management Framework (WMF) 4.0 or newer on Windows 7 and Windows Server 2008 R2.</span></span> <span data-ttu-id="75fa1-112">Weitere Informationen zu WMF erhalten Sie in der [WMF-Übersicht](/powershell/scripting/wmf/overview).</span><span class="sxs-lookup"><span data-stu-id="75fa1-112">For more information about WMF, see [WMF Overview](/powershell/scripting/wmf/overview).</span></span>

## <a name="download-the-installer-package"></a><span data-ttu-id="75fa1-113">Herunterladen des Installationspakets</span><span class="sxs-lookup"><span data-stu-id="75fa1-113">Download the installer package</span></span>

<span data-ttu-id="75fa1-114">Laden Sie zum Installieren von PowerShell unter Windows das [neueste][] Installationspaket von GitHub herunter.</span><span class="sxs-lookup"><span data-stu-id="75fa1-114">To install PowerShell on Windows, download the [latest][] install package from GitHub.</span></span> <span data-ttu-id="75fa1-115">Die neueste Vorschauversion finden Sie auch auf der Seite [Releases][].</span><span class="sxs-lookup"><span data-stu-id="75fa1-115">You can also find the latest preview version on the [releases][] page.</span></span> <span data-ttu-id="75fa1-116">Scrollen Sie auf der Seite „Release“ nach unten zum Abschnitt **Assets**.</span><span class="sxs-lookup"><span data-stu-id="75fa1-116">Scroll down to the **Assets** section of the Release page.</span></span> <span data-ttu-id="75fa1-117">Der Abschnitt **Assets** ist möglicherweise zugeklappt, sodass Sie darauf klicken müssen, um ihn aufzuklappen.</span><span class="sxs-lookup"><span data-stu-id="75fa1-117">The **Assets** section may be collapsed, so you may need to click to expand it.</span></span>

## <a name="installing-the-msi-package"></a><span data-ttu-id="75fa1-118"><a id="msi" />Installieren des MSI-Pakets</span><span class="sxs-lookup"><span data-stu-id="75fa1-118"><a id="msi" />Installing the MSI package</span></span>

<span data-ttu-id="75fa1-119">Die MSI-Datei sieht so aus: `PowerShell-<version>-win-<os-arch>.msi`.</span><span class="sxs-lookup"><span data-stu-id="75fa1-119">The MSI file looks like `PowerShell-<version>-win-<os-arch>.msi`.</span></span> <span data-ttu-id="75fa1-120">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="75fa1-120">For example:</span></span>

- `PowerShell-7.1.0-win-x64.msi`
- `PowerShell-7.1.0-win-x86.msi`

<span data-ttu-id="75fa1-121">Sobald sie heruntergeladen wurde, führen Sie den Installer mit einem Doppelklick aus und befolgen die Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="75fa1-121">Once downloaded, double-click the installer and follow the prompts.</span></span>

<span data-ttu-id="75fa1-122">Das Installationsprogramm erstellt eine Verknüpfung im Windows-Startmenü.</span><span class="sxs-lookup"><span data-stu-id="75fa1-122">The installer creates a shortcut in the Windows Start Menu.</span></span>

- <span data-ttu-id="75fa1-123">Das Paket wird standardmäßig unter `$env:ProgramFiles\PowerShell\<version>` installiert</span><span class="sxs-lookup"><span data-stu-id="75fa1-123">By default the package is installed to `$env:ProgramFiles\PowerShell\<version>`</span></span>
- <span data-ttu-id="75fa1-124">Sie können PowerShell über das Startmenü oder über `$env:ProgramFiles\PowerShell\<version>\pwsh.exe` starten</span><span class="sxs-lookup"><span data-stu-id="75fa1-124">You can launch PowerShell via the Start Menu or `$env:ProgramFiles\PowerShell\<version>\pwsh.exe`</span></span>

> [!NOTE]
> <span data-ttu-id="75fa1-125">PowerShell 7.1 wird in ein neues Verzeichnis installiert und parallel mit Windows PowerShell 5.1 ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="75fa1-125">PowerShell 7.1 installs to a new directory and runs side-by-side with Windows PowerShell 5.1.</span></span>
> <span data-ttu-id="75fa1-126">PowerShell 7.1 ist ein direktes Upgrade, das PowerShell 6.x.</span><span class="sxs-lookup"><span data-stu-id="75fa1-126">PowerShell 7.1 is an in-place upgrade that replaces PowerShell 6.x.</span></span> <span data-ttu-id="75fa1-127">oder PowerShell 7.0 ersetzt.</span><span class="sxs-lookup"><span data-stu-id="75fa1-127">or PowerShell 7.0.</span></span>
>
> - <span data-ttu-id="75fa1-128">PowerShell 7.1 wird in `$env:ProgramFiles\PowerShell\7` installiert.</span><span class="sxs-lookup"><span data-stu-id="75fa1-128">PowerShell 7.1 is installed to `$env:ProgramFiles\PowerShell\7`</span></span>
> - <span data-ttu-id="75fa1-129">Der Ordner `$env:ProgramFiles\PowerShell\7` wird `$env:PATH` hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="75fa1-129">The `$env:ProgramFiles\PowerShell\7` folder is added to `$env:PATH`</span></span>
> - <span data-ttu-id="75fa1-130">Der Ordner `$env:ProgramFiles\PowerShell\6` wird gelöscht.</span><span class="sxs-lookup"><span data-stu-id="75fa1-130">The `$env:ProgramFiles\PowerShell\6` folder is deleted</span></span>
>
> <span data-ttu-id="75fa1-131">Wenn PowerShell 7.1 parallel mit anderen Versionen ausgeführt werden muss, installieren Sie die andere Version mit der Methode unter [Installieren des ZIP-Pakets](#zip) in einem anderen Ordner.</span><span class="sxs-lookup"><span data-stu-id="75fa1-131">If you need to run PowerShell 7.1 side-by-side with other versions, use the [ZIP install](#zip) method to install the other version to a different folder.</span></span>

### <a name="administrative-install-from-the-command-line"></a><span data-ttu-id="75fa1-132">Administrative Installation über die Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="75fa1-132">Administrative install from the command line</span></span>

<span data-ttu-id="75fa1-133">MSI-Pakete können über die Befehlszeile installiert werden, sodass Administratoren Pakete ohne Benutzerinteraktion bereitstellen können.</span><span class="sxs-lookup"><span data-stu-id="75fa1-133">MSI packages can be installed from the command line allowing administrators to deploy packages without user interaction.</span></span> <span data-ttu-id="75fa1-134">Das MSI-Paket enthält die folgenden Eigenschaften zum Steuern der Installationsoptionen:</span><span class="sxs-lookup"><span data-stu-id="75fa1-134">The MSI package includes the following properties to control the installation options:</span></span>

- <span data-ttu-id="75fa1-135">**ADD_EXPLORER_CONTEXT_MENU_OPENPOWERSHELL** – Diese Eigenschaft steuert die Option zum Hinzufügen des Elements **PowerShell öffnen** zum Kontextmenü im Windows-Explorer.</span><span class="sxs-lookup"><span data-stu-id="75fa1-135">**ADD_EXPLORER_CONTEXT_MENU_OPENPOWERSHELL** - This property controls the option for adding the **Open PowerShell** item to the context menu in Windows Explorer.</span></span>
- <span data-ttu-id="75fa1-136">**ENABLE_PSREMOTING** – Diese Eigenschaft steuert die Option zum Aktivieren von PowerShell-Remoting während der Installation.</span><span class="sxs-lookup"><span data-stu-id="75fa1-136">**ENABLE_PSREMOTING** - This property controls the option for enabling PowerShell remoting during installation.</span></span>
- <span data-ttu-id="75fa1-137">**REGISTER_MANIFEST** – Diese Eigenschaft steuert die Option zum Registrieren des Manifests für Windows-Ereignisprotokollierung.</span><span class="sxs-lookup"><span data-stu-id="75fa1-137">**REGISTER_MANIFEST** - This property controls the option for registering the Windows Event Logging manifest.</span></span>

<span data-ttu-id="75fa1-138">Das folgenden Beispiel zeigt, wie PowerShell mit allen aktivierten Installationsoptionen im Hintergrund installiert wird.</span><span class="sxs-lookup"><span data-stu-id="75fa1-138">The following example shows how to silently install PowerShell with all the install options enabled.</span></span>

```powershell
msiexec.exe /package PowerShell-7.1.0-win-x64.msi /quiet ADD_EXPLORER_CONTEXT_MENU_OPENPOWERSHELL=1 ENABLE_PSREMOTING=1 REGISTER_MANIFEST=1
```

<span data-ttu-id="75fa1-139">Eine vollständige Liste der Befehlszeilenoptionen für `Msiexec.exe` finden Sie unter [Befehlszeilenoptionen](/windows/desktop/Msi/command-line-options).</span><span class="sxs-lookup"><span data-stu-id="75fa1-139">For a full list of command-line options for `Msiexec.exe`, see [Command line options](/windows/desktop/Msi/command-line-options).</span></span>

### <a name="registry-keys-created-during-installation"></a><span data-ttu-id="75fa1-140">Während der Installation erstellte Registrierungsschlüssel</span><span class="sxs-lookup"><span data-stu-id="75fa1-140">Registry keys created during installation</span></span>

<span data-ttu-id="75fa1-141">Ab PowerShell 7.1 erstellt das MSI-Paket Registrierungsschlüssel, die den Installationsort und die PowerShell-Version speichern.</span><span class="sxs-lookup"><span data-stu-id="75fa1-141">Beginning in PowerShell 7.1, the MSI package creates registry keys that store the installation location and version of PowerShell.</span></span> <span data-ttu-id="75fa1-142">Diese Werte befinden sich in `HKLM\Software\Microsoft\PowerShellCore\InstalledVersions\<GUID>`.</span><span class="sxs-lookup"><span data-stu-id="75fa1-142">These values are located in `HKLM\Software\Microsoft\PowerShellCore\InstalledVersions\<GUID>`.</span></span> <span data-ttu-id="75fa1-143">Der Wert von `<GUID>` ist für jeden Buildtyp (Release oder Vorschau), Hauptversion und Architektur eindeutig.</span><span class="sxs-lookup"><span data-stu-id="75fa1-143">The value of `<GUID>` is unique for each build type (release or preview), major version, and architecture.</span></span>

|    <span data-ttu-id="75fa1-144">Release</span><span class="sxs-lookup"><span data-stu-id="75fa1-144">Release</span></span>    | <span data-ttu-id="75fa1-145">Aufbau</span><span class="sxs-lookup"><span data-stu-id="75fa1-145">Architecture</span></span> |                                          <span data-ttu-id="75fa1-146">Registrierungsschlüssel</span><span class="sxs-lookup"><span data-stu-id="75fa1-146">Registry Key</span></span>                                           |
| ------------- | :----------: | ----------------------------------------------------------------------------------------------- |
| <span data-ttu-id="75fa1-147">Release 7.1.x</span><span class="sxs-lookup"><span data-stu-id="75fa1-147">7.1.x Release</span></span> |     <span data-ttu-id="75fa1-148">x86</span><span class="sxs-lookup"><span data-stu-id="75fa1-148">x86</span></span>      | `HKLM\Software\Microsoft\PowerShellCore\InstalledVersions\1d00683b-0f84-4db8-a64f-2f98ad42fe06` |
| <span data-ttu-id="75fa1-149">Release 7.1.x</span><span class="sxs-lookup"><span data-stu-id="75fa1-149">7.1.x Release</span></span> |     <span data-ttu-id="75fa1-150">x64</span><span class="sxs-lookup"><span data-stu-id="75fa1-150">x64</span></span>      | `HKLM\Software\Microsoft\PowerShellCore\InstalledVersions\31ab5147-9a97-4452-8443-d9709f0516e1` |
| <span data-ttu-id="75fa1-151">Vorschau 7.1.x</span><span class="sxs-lookup"><span data-stu-id="75fa1-151">7.1.x Preview</span></span> |     <span data-ttu-id="75fa1-152">x86</span><span class="sxs-lookup"><span data-stu-id="75fa1-152">x86</span></span>      | `HKLM\Software\Microsoft\PowerShellCore\InstalledVersions\86abcfbd-1ccc-4a88-b8b2-0facfde29094` |
| <span data-ttu-id="75fa1-153">Vorschau 7.1.x</span><span class="sxs-lookup"><span data-stu-id="75fa1-153">7.1.x Preview</span></span> |     <span data-ttu-id="75fa1-154">x64</span><span class="sxs-lookup"><span data-stu-id="75fa1-154">x64</span></span>      | `HKLM\Software\Microsoft\PowerShellCore\InstalledVersions\39243d76-adaf-42b1-94fb-16ecf83237c8` |

<span data-ttu-id="75fa1-155">Dies kann von Administratoren und Entwicklern verwendet werden, um den Pfad zu PowerShell zu finden.</span><span class="sxs-lookup"><span data-stu-id="75fa1-155">This can be used by administrators and developers to find the path to PowerShell.</span></span> <span data-ttu-id="75fa1-156">Die `<GUID>`-Werte sind für alle Vorschau- und Nebenversionen identisch.</span><span class="sxs-lookup"><span data-stu-id="75fa1-156">The `<GUID>` values will be the same for all preview and minor version releases.</span></span> <span data-ttu-id="75fa1-157">Die `<GUID>`-Werte werden für jede Hauptversion geändert.</span><span class="sxs-lookup"><span data-stu-id="75fa1-157">The `<GUID>` values are changed for each major release.</span></span>

## <a name="installing-the-zip-package"></a><span data-ttu-id="75fa1-158"><a id="zip" />Installieren des ZIP-Pakets</span><span class="sxs-lookup"><span data-stu-id="75fa1-158"><a id="zip" />Installing the ZIP package</span></span>

<span data-ttu-id="75fa1-159">Binäre PowerShell ZIP-Archive werden zur Verfügung gestellt, um erweiterte Bereitstellungsszenarios zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="75fa1-159">PowerShell binary ZIP archives are provided to enable advanced deployment scenarios.</span></span> <span data-ttu-id="75fa1-160">Laden Sie eines der folgenden ZIP-Archive von der Seite [Releases][Releases] herunter.</span><span class="sxs-lookup"><span data-stu-id="75fa1-160">Download one of the following ZIP archives from the [releases][releases] page.</span></span>

- <span data-ttu-id="75fa1-161">PowerShell-7.1.0-win-x64.zip</span><span class="sxs-lookup"><span data-stu-id="75fa1-161">PowerShell-7.1.0-win-x64.zip</span></span>
- <span data-ttu-id="75fa1-162">PowerShell-7.1.0-win-x86.zip</span><span class="sxs-lookup"><span data-stu-id="75fa1-162">PowerShell-7.1.0-win-x86.zip</span></span>
- <span data-ttu-id="75fa1-163">PowerShell-7.1.0-win-arm64.zip</span><span class="sxs-lookup"><span data-stu-id="75fa1-163">PowerShell-7.1.0-win-arm64.zip</span></span>
- <span data-ttu-id="75fa1-164">PowerShell-7.1.0-win-arm32.zip</span><span class="sxs-lookup"><span data-stu-id="75fa1-164">PowerShell-7.1.0-win-arm32.zip</span></span>

<span data-ttu-id="75fa1-165">Je nachdem, wie Sie die Datei herunterladen, müssen Sie die Blockierung der Datei mit dem Cmdlet `Unblock-File` aufheben.</span><span class="sxs-lookup"><span data-stu-id="75fa1-165">Depending on how you download the file you may need to unblock the file using the `Unblock-File` cmdlet.</span></span> <span data-ttu-id="75fa1-166">Entpacken Sie den Inhalt an den Speicherort Ihrer Wahl, und führen Sie `pwsh.exe` von dort aus.</span><span class="sxs-lookup"><span data-stu-id="75fa1-166">Unzip the contents to the location of your choice and run `pwsh.exe` from there.</span></span> <span data-ttu-id="75fa1-167">Anders als bei der Installation der MSI-Pakete erfolgt bei der Installation des ZIP-Archivs keine Prüfung auf Voraussetzungen.</span><span class="sxs-lookup"><span data-stu-id="75fa1-167">Unlike installing the MSI packages, installing the ZIP archive doesn't check for prerequisites.</span></span> <span data-ttu-id="75fa1-168">Damit Remoting über WSMan einwandfrei funktioniert, müssen die [Voraussetzungen](#prerequisites) unbedingt erfüllt sein.</span><span class="sxs-lookup"><span data-stu-id="75fa1-168">For remoting over WSMan to work properly, ensure that you've met the [prerequisites](#prerequisites).</span></span>

<span data-ttu-id="75fa1-169">Installieren Sie mit dieser Methode die ARM-basierte Version von PowerShell auf Computern wie Microsoft Surface Pro X. Die besten Ergebnisse erzielen Sie, wenn Sie PowerShell im Ordner `$env:ProgramFiles\PowerShell\7` installieren.</span><span class="sxs-lookup"><span data-stu-id="75fa1-169">Use this method to install the ARM-based version of PowerShell on computers like the Microsoft Surface Pro X. For best results, install PowerShell to the to `$env:ProgramFiles\PowerShell\7` folder.</span></span>

## <a name="deploying-on-windows-10-iot-enterprise"></a><span data-ttu-id="75fa1-170">Bereitstellung unter Windows 10 IoT Enterprise</span><span class="sxs-lookup"><span data-stu-id="75fa1-170">Deploying on Windows 10 IoT Enterprise</span></span>

<span data-ttu-id="75fa1-171">Bei Windows 10 IoT Enterprise ist Windows PowerShell bereits im Funktionsumfang enthalten, sodass PowerShell 7 bereitgestellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="75fa1-171">Windows 10 IoT Enterprise comes with Windows PowerShell, which we can use to deploy PowerShell 7.</span></span>

1. <span data-ttu-id="75fa1-172">Erstellen Sie `PSSession` auf dem Zielgerät.</span><span class="sxs-lookup"><span data-stu-id="75fa1-172">Create `PSSession` to target device</span></span>

   ```powershell
   Set-Item -Path WSMan:\localhost\Client\TrustedHosts <deviceip>
   $S = New-PSSession -ComputerName <deviceIp> -Credential Administrator
   ```

1. <span data-ttu-id="75fa1-173">Kopieren Sie das ZIP-Paket auf das Gerät.</span><span class="sxs-lookup"><span data-stu-id="75fa1-173">Copy the ZIP package to the device</span></span>

   ```powershell
   # change the destination to however you had partitioned it with sufficient
   # space for the zip and the unzipped contents
   # the path should be local to the device
   Copy-Item .\PowerShell-<version>-win-<os-arch>.zip -Destination u:\users\administrator\Downloads -ToSession $s
   ```

1. <span data-ttu-id="75fa1-174">Stellen Sie eine Verbindung mit dem Gerät her, und erweitern Sie das Archiv.</span><span class="sxs-lookup"><span data-stu-id="75fa1-174">Connect to the device and expand the archive</span></span>

   ```powershell
   Enter-PSSession $s
   Set-Location u:\users\administrator\downloads
   Expand-Archive .\PowerShell-<version>-win-<os-arch>.zip
   ```

1. <span data-ttu-id="75fa1-175">Richten Sie Remoting für PowerShell 7 ein.</span><span class="sxs-lookup"><span data-stu-id="75fa1-175">Set up remoting to PowerShell 7</span></span>

   ```powershell
   Set-Location .\PowerShell-<version>-win-<os-arch>
   # Be sure to use the -PowerShellHome parameter otherwise it'll try to create a new
   # endpoint with Windows PowerShell 5.1
   .\Install-PowerShellRemoting.ps1 -PowerShellHome .
   # You'll get an error message and will be disconnected from the device because
   # it has to restart WinRM
   ```

1. <span data-ttu-id="75fa1-176">Stellen Sie eine Verbindung mit dem PowerShell 7-Endpunkt auf dem Gerät her.</span><span class="sxs-lookup"><span data-stu-id="75fa1-176">Connect to PowerShell 7 endpoint on device</span></span>

   ```powershell
   # Be sure to use the -Configuration parameter. If you omit it, you will connect to Windows PowerShell 5.1
   Enter-PSSession -ComputerName <deviceIp> -Credential Administrator -Configuration powershell.<version>
   ```

## <a name="deploying-on-windows-10-iot-core"></a><span data-ttu-id="75fa1-177">Bereitstellung unter Windows 10 IoT Core</span><span class="sxs-lookup"><span data-stu-id="75fa1-177">Deploying on Windows 10 IoT Core</span></span>

<span data-ttu-id="75fa1-178">Bei Windows 10 IoT Core wird Windows PowerShell hinzugefügt, wenn Sie das Feature _IOT_POWERSHELL_ aufnehmen. Über dieses Feature kann PowerShell 7 bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="75fa1-178">Windows 10 IoT Core adds Windows PowerShell when you include _IOT_POWERSHELL_ feature, which we can use to deploy PowerShell 7.</span></span> <span data-ttu-id="75fa1-179">Die oben beschriebenen Schritte für Windows 10 IoT Enterprise können auch für IoT Core ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="75fa1-179">The steps defined above for Windows 10 IoT Enterprise can be followed for IoT Core as well.</span></span>

<span data-ttu-id="75fa1-180">Verwenden Sie zum Hinzufügen der aktuellen PowerShell-Version im Image den Befehl [Import-PSCoreRelease][]. Mit diesem Befehl wird das Paket im Arbeitsbereich eingefügt und das Feature _OPENSRC_POWERSHELL_ zu Ihrem Image hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="75fa1-180">For adding the latest PowerShell in the shipping image, use [Import-PSCoreRelease][] command to include the package in the workarea and add _OPENSRC_POWERSHELL_ feature to your image.</span></span>

> [!NOTE]
> <span data-ttu-id="75fa1-181">Bei der ARM64-Architektur wird Windows PowerShell nicht hinzugefügt, wenn Sie _IOT_POWERSHELL_ einfügen.</span><span class="sxs-lookup"><span data-stu-id="75fa1-181">For ARM64 architecture, Windows PowerShell is not added when you include _IOT_POWERSHELL_.</span></span> <span data-ttu-id="75fa1-182">Daher funktioniert die ZIP-basierte Installation nicht.</span><span class="sxs-lookup"><span data-stu-id="75fa1-182">So the zip based install will not work.</span></span> <span data-ttu-id="75fa1-183">Sie müssen den Befehl `Import-PSCoreRelease` verwenden, um ihn im Image hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="75fa1-183">You will need to use `Import-PSCoreRelease` command to add it in the image.</span></span>

## <a name="deploying-on-nano-server"></a><span data-ttu-id="75fa1-184">Bereitstellen auf Nano Server</span><span class="sxs-lookup"><span data-stu-id="75fa1-184">Deploying on Nano Server</span></span>

<span data-ttu-id="75fa1-185">Diese Anweisungen gehen davon aus, dass der Nano Server ein „monitorloses“ Betriebssystem ist, unter dem bereits eine Version von PowerShell ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="75fa1-185">These instructions assume that the Nano Server is a "headless" OS that has a version of PowerShell is already running on it.</span></span> <span data-ttu-id="75fa1-186">Weitere Informationen finden Sie in der [Dokumentation zu Nano Server Image Builder](/windows-server/get-started/deploy-nano-server).</span><span class="sxs-lookup"><span data-stu-id="75fa1-186">For more information, see the [Nano Server Image Builder](/windows-server/get-started/deploy-nano-server) documentation.</span></span>

<span data-ttu-id="75fa1-187">PowerShell-Binärdateien können auf zwei verschiedene Arten bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="75fa1-187">PowerShell binaries can be deployed using two different methods.</span></span>

1. <span data-ttu-id="75fa1-188">Offline: Binden Sie die Nano Server-VHD ein, und entpacken Sie den Inhalt der ZIP-Datei an dem von Ihnen gewünschten Speicherort in dem eingebundenen Image.</span><span class="sxs-lookup"><span data-stu-id="75fa1-188">Offline - Mount the Nano Server VHD and unzip the contents of the zip file to your chosen location within the mounted image.</span></span>
1. <span data-ttu-id="75fa1-189">Online: Übertragen Sie die ZIP-Datei über eine PowerShell-Sitzung, und entpacken Sie sie an dem von Ihnen gewünschten Speicherort.</span><span class="sxs-lookup"><span data-stu-id="75fa1-189">Online - Transfer the zip file over a PowerShell Session and unzip it in your chosen location.</span></span>

<span data-ttu-id="75fa1-190">In beiden Fällen benötigen Sie das ZIP-Releasepaket für Windows 10 x64.</span><span class="sxs-lookup"><span data-stu-id="75fa1-190">In both cases, you need the Windows 10 x64 ZIP release package.</span></span> <span data-ttu-id="75fa1-191">Führen Sie die Befehle in einer „Administrator“-Instanz von PowerShell aus.</span><span class="sxs-lookup"><span data-stu-id="75fa1-191">Run the commands within an "Administrator" instance of PowerShell.</span></span>

### <a name="offline-deployment-of-powershell"></a><span data-ttu-id="75fa1-192">Offlinebereitstellung von PowerShell</span><span class="sxs-lookup"><span data-stu-id="75fa1-192">Offline Deployment of PowerShell</span></span>

1. <span data-ttu-id="75fa1-193">Verwenden Sie Ihr bevorzugtes ZIP-Hilfsprogramm, um das Paket in ein Verzeichnis im eingebundenen Nano Server-Image zu entpacken.</span><span class="sxs-lookup"><span data-stu-id="75fa1-193">Use your favorite zip utility to unzip the package to a directory within the mounted Nano Server image.</span></span>
1. <span data-ttu-id="75fa1-194">Heben Sie die Bereitstellung des Images auf, und starten Sie es.</span><span class="sxs-lookup"><span data-stu-id="75fa1-194">Unmount the image and boot it.</span></span>
1. <span data-ttu-id="75fa1-195">Stellen Sie eine Verbindung mit der integrierten Instanz von Windows PowerShell her.</span><span class="sxs-lookup"><span data-stu-id="75fa1-195">Connect to the built-in instance of Windows PowerShell.</span></span>
1. <span data-ttu-id="75fa1-196">Befolgen Sie die Anweisungen, um einen Remoting-Endpunkt mithilfe der [„Andere Instanz-Methode“][] zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="75fa1-196">Follow the instructions to create a remoting endpoint using the ["another instance technique"][].</span></span>

### <a name="online-deployment-of-powershell"></a><span data-ttu-id="75fa1-197">Onlinebereitstellung von PowerShell</span><span class="sxs-lookup"><span data-stu-id="75fa1-197">Online Deployment of PowerShell</span></span>

<span data-ttu-id="75fa1-198">Stellen Sie PowerShell mithilfe der folgenden Schritte für Nano Server bereit.</span><span class="sxs-lookup"><span data-stu-id="75fa1-198">Deploy PowerShell to Nano Server using the following steps.</span></span>

- <span data-ttu-id="75fa1-199">Herstellen einer Verbindung mit der integrierten Instanz von Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="75fa1-199">Connect to the built-in instance of Windows PowerShell</span></span>

  ```powershell
  $session = New-PSSession -ComputerName <Nano Server IP address> -Credential <An Administrator account on the system>
  ```

- <span data-ttu-id="75fa1-200">Kopieren Sie die Datei in die Nano Server-Instanz.</span><span class="sxs-lookup"><span data-stu-id="75fa1-200">Copy the file to the Nano Server instance</span></span>

  ```powershell
  Copy-Item <local PS Core download location>\powershell-<version>-win-x64.zip c:\ -ToSession $session
  ```

- <span data-ttu-id="75fa1-201">Geben Sie die Sitzung ein.</span><span class="sxs-lookup"><span data-stu-id="75fa1-201">Enter the session</span></span>

  ```powershell
  Enter-PSSession $session
  ```

- <span data-ttu-id="75fa1-202">Extrahieren Sie die ZIP-Datei.</span><span class="sxs-lookup"><span data-stu-id="75fa1-202">Extract the ZIP file</span></span>

  ```powershell
  # Insert the appropriate version.
  Expand-Archive -Path C:\powershell-<version>-win-x64.zip -DestinationPath "C:\PowerShell_<version>"
  ```

- <span data-ttu-id="75fa1-203">Befolgen Sie die Anweisungen, wenn Sie auf WSMan basierendes Remoting verwenden möchten, um einen Remoting-Endpunkt mithilfe der [„Andere Instanz-Methode“][] zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="75fa1-203">If you want WSMan-based remoting, follow the instructions to create a remoting endpoint using the ["another instance technique"][].</span></span>

## <a name="install-as-a-net-global-tool"></a><span data-ttu-id="75fa1-204">Installieren als globales .NET-Tool</span><span class="sxs-lookup"><span data-stu-id="75fa1-204">Install as a .NET Global tool</span></span>

<span data-ttu-id="75fa1-205">Wenn Sie das [.NET Core SDK](/dotnet/core/sdk) bereits installiert haben, können Sie PowerShell einfach als [globales .NET-Tool](/dotnet/core/tools/global-tools) installieren.</span><span class="sxs-lookup"><span data-stu-id="75fa1-205">If you already have the [.NET Core SDK](/dotnet/core/sdk) installed, it's easy to install PowerShell as a [.NET Global tool](/dotnet/core/tools/global-tools).</span></span>

```
dotnet tool install --global PowerShell
```

<span data-ttu-id="75fa1-206">Der .NET-Toolinstaller fügt `$env:USERPROFILE\dotnet\tools` Ihrer `$env:PATH`-Umgebungsvariablen hinzu.</span><span class="sxs-lookup"><span data-stu-id="75fa1-206">The dotnet tool installer adds `$env:USERPROFILE\dotnet\tools` to your `$env:PATH` environment variable.</span></span> <span data-ttu-id="75fa1-207">Die aktuell ausgeführte Shell verfügt jedoch nicht über die aktualisierte Umgebungsvariable `$env:PATH`.</span><span class="sxs-lookup"><span data-stu-id="75fa1-207">However, the currently running shell doesn't have the updated `$env:PATH`.</span></span> <span data-ttu-id="75fa1-208">Sie können PowerShell über eine neue Shell starten, indem Sie `pwsh` eingeben.</span><span class="sxs-lookup"><span data-stu-id="75fa1-208">You can start PowerShell from a new shell by typing `pwsh`.</span></span>

## <a name="install-powershell-via-winget"></a><span data-ttu-id="75fa1-209">Installieren von PowerShell über Winget</span><span class="sxs-lookup"><span data-stu-id="75fa1-209">Install PowerShell via Winget</span></span>

<span data-ttu-id="75fa1-210">Mit dem Befehlszeilentool `winget` können Entwickler Anwendungen auf Windows 10-Computern ermitteln, installieren, aktualisieren, entfernen und konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="75fa1-210">The `winget` command-line tool enables developers to discover, install, upgrade, remove, and configure applications on Windows 10 computers.</span></span> <span data-ttu-id="75fa1-211">Dieses Tool ist die Clientschnittstelle für den Windows-Paket-Manager-Dienst.</span><span class="sxs-lookup"><span data-stu-id="75fa1-211">This tool is the client interface to the Windows Package Manager service.</span></span>

> [!NOTE]
> <span data-ttu-id="75fa1-212">Das `winget`-Tool befindet sich zurzeit in der Vorschau.</span><span class="sxs-lookup"><span data-stu-id="75fa1-212">The `winget` tool is currently a preview.</span></span> <span data-ttu-id="75fa1-213">Zurzeit sind nicht alle geplanten Funktionen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="75fa1-213">Not all planned functionality is available at this time.</span></span>
> <span data-ttu-id="75fa1-214">Diese Methode sollten Sie nicht in einem Produktionsbereitstellungsszenario verwenden.</span><span class="sxs-lookup"><span data-stu-id="75fa1-214">You should not use this method in a production deployment scenario.</span></span> <span data-ttu-id="75fa1-215">Eine Liste der Systemanforderungen und Installationsanweisungen finden Sie in der Dokumentation zu [winget].</span><span class="sxs-lookup"><span data-stu-id="75fa1-215">See the [winget] documentation for a list of system requirements and install instructions.</span></span>

<span data-ttu-id="75fa1-216">Die folgenden Befehle können verwendet werden, um PowerShell mithilfe der veröffentlichten `winget`-Pakete zu installieren:</span><span class="sxs-lookup"><span data-stu-id="75fa1-216">The following commands can be used to install PowerShell using the published `winget` packages:</span></span>

1. <span data-ttu-id="75fa1-217">Suchen nach der neuesten Version von PowerShell</span><span class="sxs-lookup"><span data-stu-id="75fa1-217">Search for the latest version of PowerShell</span></span>

   ```powershell
   winget search Microsoft.PowerShell
   ```

   ```Output
   Name               Id                           Version
   ---------------------------------------------------------------
   PowerShell         Microsoft.PowerShell         7.1.0
   PowerShell-Preview Microsoft.PowerShell-Preview 7.1.0-preview.5
   ```

1. <span data-ttu-id="75fa1-218">Installieren einer PowerShell-Version mithilfe des `--exact`-Parameters</span><span class="sxs-lookup"><span data-stu-id="75fa1-218">Install a version of PowerShell using the `--exact` parameter</span></span>

   ```powershell
   winget install --name PowerShell --exact
   winget install --name PowerShell-Preview --exact
   ```

## <a name="installing-from-the-microsoft-store"></a><span data-ttu-id="75fa1-219"><a id="msix" />Installieren über den Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="75fa1-219"><a id="msix" />Installing from the Microsoft Store</span></span>

<span data-ttu-id="75fa1-220">PowerShell 7.1 wurde im Microsoft Store veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="75fa1-220">PowerShell 7.1 has been published to the Microsoft Store.</span></span> <span data-ttu-id="75fa1-221">Die PowerShell-Version finden Sie auf der Website von [Microsoft Store](https://www.microsoft.com/store/apps/9MZ1SNWT0N5D) oder in der Store-Anwendung unter Windows.</span><span class="sxs-lookup"><span data-stu-id="75fa1-221">You can find the PowerShell release on the [Microsoft Store](https://www.microsoft.com/store/apps/9MZ1SNWT0N5D) website or in the Store application in Windows.</span></span>

<span data-ttu-id="75fa1-222">Vorteile des Microsoft Store-Pakets:</span><span class="sxs-lookup"><span data-stu-id="75fa1-222">Benefits of the Microsoft Store package:</span></span>

- <span data-ttu-id="75fa1-223">Direkt in Windows 10 integrierte automatische Updates</span><span class="sxs-lookup"><span data-stu-id="75fa1-223">Automatic updates built right into Windows 10</span></span>
- <span data-ttu-id="75fa1-224">Integration in andere Softwareverteilungsmechanismen wie Intune und SCCM</span><span class="sxs-lookup"><span data-stu-id="75fa1-224">Integrates with other software distribution mechanisms like Intune and SCCM</span></span>

<span data-ttu-id="75fa1-225">Einschränkungen:</span><span class="sxs-lookup"><span data-stu-id="75fa1-225">Limitations:</span></span>

<span data-ttu-id="75fa1-226">MSIX-Pakete werden in einer Sandbox für Anwendungen ausgeführt, die den Zugriff auf einige Dateisystem- und Registrierungsspeicherorte virtualisiert.</span><span class="sxs-lookup"><span data-stu-id="75fa1-226">MSIX packages run in an application sandbox that virtualizes access to some filesystem and registry locations.</span></span>

- <span data-ttu-id="75fa1-227">Alle Registrierungsänderungen unter HKEY_CURRENT_USER werden beim Schreiben in einen privaten Speicherort benutzer- und App-spezifisch kopiert.</span><span class="sxs-lookup"><span data-stu-id="75fa1-227">All registry changes under HKEY_CURRENT_USER are copied on write to a private, per-user, per-app location.</span></span> <span data-ttu-id="75fa1-228">Diese Werte sind daher für andere Anwendungen nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="75fa1-228">Therefore, those values are not available to other applications.</span></span>
- <span data-ttu-id="75fa1-229">Alle in `$PSHOME` gespeicherten Konfigurationseinstellungen auf Systemebene lassen sich nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="75fa1-229">Any system-level configuration settings stored in `$PSHOME` cannot be modified.</span></span> <span data-ttu-id="75fa1-230">Dies schließt die WSMAN-Konfiguration ein.</span><span class="sxs-lookup"><span data-stu-id="75fa1-230">This includes the WSMAN configuration.</span></span> <span data-ttu-id="75fa1-231">Dadurch wird verhindert, dass Remotesitzungen eine Verbindung mit auf Store basierenden Installationen von PowerShell herstellen.</span><span class="sxs-lookup"><span data-stu-id="75fa1-231">This prevents remote sessions from connecting to Store-based installs of PowerShell.</span></span> <span data-ttu-id="75fa1-232">Konfigurationen auf Benutzerebene und SSH-Remoting werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="75fa1-232">User-level configurations and SSH remoting are supported.</span></span>

<span data-ttu-id="75fa1-233">Weitere Informationen finden Sie unter [Grundlegendes zur Funktionsweise von App-Paketen unter Windows](/windows/msix/desktop/desktop-to-uwp-behind-the-scenes).</span><span class="sxs-lookup"><span data-stu-id="75fa1-233">For more information, see [Understanding how packaged desktop apps run on Windows](/windows/msix/desktop/desktop-to-uwp-behind-the-scenes).</span></span>

### <a name="using-the-msix-package"></a><span data-ttu-id="75fa1-234">Verwenden des MSIX-Pakets</span><span class="sxs-lookup"><span data-stu-id="75fa1-234">Using the MSIX package</span></span>

> [!NOTE]
> <span data-ttu-id="75fa1-235">Die Vorschaubuilds von PowerShell enthalten ein MSIX-Paket.</span><span class="sxs-lookup"><span data-stu-id="75fa1-235">The preview builds of PowerShell include an MSIX package.</span></span> <span data-ttu-id="75fa1-236">Das MSIX-Paket wird nicht offiziell unterstützt.</span><span class="sxs-lookup"><span data-stu-id="75fa1-236">The MSIX package is not officially supported.</span></span> <span data-ttu-id="75fa1-237">Das Paket wird zu Testzwecken in der Vorschauphase erstellt.</span><span class="sxs-lookup"><span data-stu-id="75fa1-237">The package is built for testing purposes during the preview period.</span></span>

<span data-ttu-id="75fa1-238">Um das MSIX-Paket manuell auf einem Windows 10-Client zu installieren, laden Sie das MSIX-Paket von der GitHub-Seite mit [Releases][Releases] herunter.</span><span class="sxs-lookup"><span data-stu-id="75fa1-238">To manually install the MSIX package on a Windows 10 client, download the MSIX package from our GitHub [releases][releases] page.</span></span> <span data-ttu-id="75fa1-239">Scrollen Sie nach unten zum Abschnitt **Assets** des Release, das Sie installieren möchten.</span><span class="sxs-lookup"><span data-stu-id="75fa1-239">Scroll down to the **Assets** section of the Release you want to install.</span></span> <span data-ttu-id="75fa1-240">Der Abschnitt „Assets“ ist möglicherweise reduziert, sodass Sie klicken müssen, um ihn zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="75fa1-240">The Assets section may be collapsed, so you may need to click to expand it.</span></span>

<span data-ttu-id="75fa1-241">Die MSIX-Datei sieht so aus: `PowerShell-<version>-win-<os-arch>.msix`</span><span class="sxs-lookup"><span data-stu-id="75fa1-241">The MSIX file looks like this - `PowerShell-<version>-win-<os-arch>.msix`</span></span>

<span data-ttu-id="75fa1-242">Zum Installieren des Pakets müssen Sie das Cmdlet `Add-AppxPackage` verwenden:</span><span class="sxs-lookup"><span data-stu-id="75fa1-242">To install the package, you must use the `Add-AppxPackage` cmdlet.</span></span>

```powershell
Add-AppxPackage PowerShell-<version>-win-<os-arch>.msix
```

## <a name="how-to-create-a-remoting-endpoint"></a><span data-ttu-id="75fa1-243">Vorgehensweise zum Erstellen eines Remoting-Endpunkts</span><span class="sxs-lookup"><span data-stu-id="75fa1-243">How to create a remoting endpoint</span></span>

<span data-ttu-id="75fa1-244">PowerShell unterstützt das PowerShell-Remotingprotokoll (PSRP) über WSMan und SSH.</span><span class="sxs-lookup"><span data-stu-id="75fa1-244">PowerShell supports the PowerShell Remoting Protocol (PSRP) over both WSMan and SSH.</span></span> <span data-ttu-id="75fa1-245">Weitere Informationen finden Sie unter</span><span class="sxs-lookup"><span data-stu-id="75fa1-245">For more information, see:</span></span>

- <span data-ttu-id="75fa1-246">[SSH-Remoting in PowerShell Core][ssh-remoting]</span><span class="sxs-lookup"><span data-stu-id="75fa1-246">[SSH Remoting in PowerShell Core][ssh-remoting]</span></span>
- <span data-ttu-id="75fa1-247">[WSMan-Remoting in PowerShell Core][wsman-remoting]</span><span class="sxs-lookup"><span data-stu-id="75fa1-247">[WSMan Remoting in PowerShell Core][wsman-remoting]</span></span>

## <a name="upgrading-an-existing-installation"></a><span data-ttu-id="75fa1-248">Upgrade einer vorhandenen Installation</span><span class="sxs-lookup"><span data-stu-id="75fa1-248">Upgrading an existing installation</span></span>

<span data-ttu-id="75fa1-249">Für optimale Ergebnisse beim Upgrade sollten Sie dieselbe Installationsmethode verwenden, die Sie bei der ersten Installation von PowerShell verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="75fa1-249">For best results when upgrading, you should use the same install method you used when you first installed PowerShell.</span></span> <span data-ttu-id="75fa1-250">Bei jeder Installationsmethode wird PowerShell an einem anderen Speicherort installiert.</span><span class="sxs-lookup"><span data-stu-id="75fa1-250">Each installation method installs PowerShell in a different location.</span></span> <span data-ttu-id="75fa1-251">Wenn Sie nicht sicher sind, wie PowerShell installiert wurde, können Sie den Speicherort der Installation mit den Paketinformationen in diesem Artikel vergleichen.</span><span class="sxs-lookup"><span data-stu-id="75fa1-251">If you are not sure how PowerShell was installed, you can compare the installed location with the package information in this article.</span></span> <span data-ttu-id="75fa1-252">Wenn die Installation über das MSI-Paket erfolgt ist, finden Sie diese Informationen in der Systemsteuerung unter **Programme und Features**.</span><span class="sxs-lookup"><span data-stu-id="75fa1-252">If you installed via the MSI package, that information appears in the **Programs and Features** Control Panel.</span></span>

## <a name="installation-support"></a><span data-ttu-id="75fa1-253">Installationsunterstützung</span><span class="sxs-lookup"><span data-stu-id="75fa1-253">Installation support</span></span>

<span data-ttu-id="75fa1-254">Microsoft unterstützt die in diesem Dokument beschriebenen Installationsmethoden.</span><span class="sxs-lookup"><span data-stu-id="75fa1-254">Microsoft supports the installation methods in this document.</span></span> <span data-ttu-id="75fa1-255">Möglicherweise stehen andere Installationsmethoden aus anderen Quellen zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="75fa1-255">There may be other methods of installation available from other sources.</span></span> <span data-ttu-id="75fa1-256">Auch wenn diese Tools und Methoden funktionieren, kann Microsoft sie nicht unterstützen.</span><span class="sxs-lookup"><span data-stu-id="75fa1-256">While those tools and methods may work, Microsoft cannot support those methods.</span></span>

<!-- link references -->

[Freigaben]: https://github.com/PowerShell/PowerShell/releases
[releases]: https://github.com/PowerShell/PowerShell/releases
[Neueste]: https://github.com/PowerShell/PowerShell/releases/latest
[latest]: https://github.com/PowerShell/PowerShell/releases/latest
[ssh-remoting]: ../learn/remoting/SSH-Remoting-in-PowerShell-Core.md
[wsman-remoting]: ../learn/remoting/WSMan-Remoting-in-PowerShell-Core.md
[AppVeyor]: https://ci.appveyor.com/project/PowerShell/powershell
[winget]: /windows/package-manager/winget
[„andere Instanztechnik“]: ../learn/remoting/WSMan-Remoting-in-PowerShell-Core.md#executed-by-another-instance-of-powershell-on-behalf-of-the-instance-that-it-will-register
["another instance technique"]: ../learn/remoting/WSMan-Remoting-in-PowerShell-Core.md#executed-by-another-instance-of-powershell-on-behalf-of-the-instance-that-it-will-register
[Import-PSCoreRelease]: https://github.com/ms-iot/iot-adk-addonkit/blob/master/Tools/IoTCoreImaging/Docs/Import-PSCoreRelease.md#Import-PSCoreRelease
