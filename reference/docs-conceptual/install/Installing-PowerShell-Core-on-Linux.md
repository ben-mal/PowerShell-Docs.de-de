---
title: Installieren von PowerShell unter Linux
description: Informationen zur Installation von PowerShell auf verschiedenen Linux-Distributionen
ms.date: 02/02/2021
ms.openlocfilehash: b093e3ff20772016139999836adc5ec1b7a18197
ms.sourcegitcommit: 080c8b05a1242348c365fe1684457e873325f11e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2021
ms.locfileid: "103483348"
---
# <a name="installing-powershell-on-linux"></a><span data-ttu-id="84b3b-103">Installieren von PowerShell unter Linux</span><span class="sxs-lookup"><span data-stu-id="84b3b-103">Installing PowerShell on Linux</span></span>

<span data-ttu-id="84b3b-104">Sämtliche Pakete sind auf der Seite [Freigaben][] über GitHub verfügbar.</span><span class="sxs-lookup"><span data-stu-id="84b3b-104">All packages are available on our GitHub [releases][] page.</span></span> <span data-ttu-id="84b3b-105">Nachdem Sie das Paket installiert haben, führen Sie `pwsh` über das Terminal aus.</span><span class="sxs-lookup"><span data-stu-id="84b3b-105">After the package is installed, run `pwsh` from a terminal.</span></span> <span data-ttu-id="84b3b-106">Führen Sie `pwsh-preview` aus, wenn Sie eine [Vorschauversion](#installing-preview-releases) installiert haben.</span><span class="sxs-lookup"><span data-stu-id="84b3b-106">Run `pwsh-preview` if you installed a [Preview release](#installing-preview-releases).</span></span>

> [!NOTE]
> <span data-ttu-id="84b3b-107">PowerShell 7 ist ein direktes Upgrade, mit dem PowerShell Core 6.x entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="84b3b-107">PowerShell 7 is an in-place upgrade that removes PowerShell Core 6.x.</span></span>
>
> <span data-ttu-id="84b3b-108">Der Ordner `/usr/local/microsoft/powershell/6` wird durch `/usr/local/microsoft/powershell/7` ersetzt.</span><span class="sxs-lookup"><span data-stu-id="84b3b-108">The `/usr/local/microsoft/powershell/6` folder is replaced by `/usr/local/microsoft/powershell/7`.</span></span>
>
> <span data-ttu-id="84b3b-109">Wenn Sie PowerShell 6 und PowerShell 7 parallel ausführen müssen, installieren Sie PowerShell 6 mithilfe der [binary archive](#binary-archives)-Methode neu.</span><span class="sxs-lookup"><span data-stu-id="84b3b-109">If you need to run PowerShell 6 side-by-side with PowerShell 7, reinstall PowerShell 6 using the [binary archive](#binary-archives) method.</span></span>

<span data-ttu-id="84b3b-110">Für nicht offiziell unterstützte Linux-Distributionen können Sie versuchen, PowerShell über das [Snap-Paket für PowerShell][snap] zu installieren.</span><span class="sxs-lookup"><span data-stu-id="84b3b-110">For Linux distributions that aren't officially supported, you can try to install PowerShell using the [PowerShell Snap Package][snap].</span></span> <span data-ttu-id="84b3b-111">Stattdessen können Sie auch versuchen, PowerShell-Binärdateien über das [`tar.gz`-Archiv][tar] für Linux bereitzustellen. Dafür müssen Sie aber die für Ihr Betriebssystem erforderlichen Abhängigkeiten in zusätzlichen Schritten einrichten.</span><span class="sxs-lookup"><span data-stu-id="84b3b-111">You can also try deploying PowerShell binaries directly using the Linux [`tar.gz` archive][tar], but you would need to set up the necessary dependencies based on the OS in separate steps.</span></span>

[snap]: #snap-package
[tar]: #binary-archives

<!-- TODO: Update for supported releases v7.0 & v7.1 -->

<span data-ttu-id="84b3b-112">Offiziell unterstützte Plattformreleases für PowerShell 7.1</span><span class="sxs-lookup"><span data-stu-id="84b3b-112">Officially supported platform releases for PowerShell 7.1</span></span>

- <span data-ttu-id="84b3b-113">Ubuntu 16.04/18.04/20.04 (einschließlich ARM64)</span><span class="sxs-lookup"><span data-stu-id="84b3b-113">Ubuntu 16.04/18.04/20.04 (including ARM64)</span></span>
- <span data-ttu-id="84b3b-114">Ubuntu 19.10 (über Snap-Pakete)</span><span class="sxs-lookup"><span data-stu-id="84b3b-114">Ubuntu 19.10 (via Snap package)</span></span>
- <span data-ttu-id="84b3b-115">Debian 9/10</span><span class="sxs-lookup"><span data-stu-id="84b3b-115">Debian 9/10</span></span>
- <span data-ttu-id="84b3b-116">CentOS und RHEL 7/8</span><span class="sxs-lookup"><span data-stu-id="84b3b-116">CentOS and RHEL 7/8</span></span>
- <span data-ttu-id="84b3b-117">Fedora 30</span><span class="sxs-lookup"><span data-stu-id="84b3b-117">Fedora 30</span></span>
- <span data-ttu-id="84b3b-118">Alpine ab 3.11 (einschließlich ARM64)</span><span class="sxs-lookup"><span data-stu-id="84b3b-118">Alpine 3.11+ (including ARM64)</span></span>

<span data-ttu-id="84b3b-119">Offiziell unterstützte Plattformreleases für PowerShell 7.0</span><span class="sxs-lookup"><span data-stu-id="84b3b-119">Officially supported platform releases for PowerShell 7.0</span></span>

- <span data-ttu-id="84b3b-120">Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="84b3b-120">Ubuntu 16.04</span></span>
- <span data-ttu-id="84b3b-121">Ubuntu 18.04 und 20.04</span><span class="sxs-lookup"><span data-stu-id="84b3b-121">Ubuntu 18.04 and 20.04</span></span>
- <span data-ttu-id="84b3b-122">Debian 8</span><span class="sxs-lookup"><span data-stu-id="84b3b-122">Debian 8</span></span>
- <span data-ttu-id="84b3b-123">Debian 9</span><span class="sxs-lookup"><span data-stu-id="84b3b-123">Debian 9</span></span>
- <span data-ttu-id="84b3b-124">Debian 10</span><span class="sxs-lookup"><span data-stu-id="84b3b-124">Debian 10</span></span>
- <span data-ttu-id="84b3b-125">Alpine 3.9 und 3.10</span><span class="sxs-lookup"><span data-stu-id="84b3b-125">Alpine 3.9 and 3.10</span></span>
- <span data-ttu-id="84b3b-126">CentOS 7:</span><span class="sxs-lookup"><span data-stu-id="84b3b-126">CentOS 7</span></span>
- <span data-ttu-id="84b3b-127">Red Hat Enterprise Linux 7 (RHEL)</span><span class="sxs-lookup"><span data-stu-id="84b3b-127">Red Hat Enterprise Linux (RHEL) 7</span></span>
- <span data-ttu-id="84b3b-128">Fedora 28</span><span class="sxs-lookup"><span data-stu-id="84b3b-128">Fedora 28</span></span>
- <span data-ttu-id="84b3b-129">Fedora 29</span><span class="sxs-lookup"><span data-stu-id="84b3b-129">Fedora 29</span></span>
- <span data-ttu-id="84b3b-130">Fedora 30</span><span class="sxs-lookup"><span data-stu-id="84b3b-130">Fedora 30</span></span>
- <span data-ttu-id="84b3b-131">openSUSE 42.3</span><span class="sxs-lookup"><span data-stu-id="84b3b-131">openSUSE 42.3</span></span>
- <span data-ttu-id="84b3b-132">openSUSE Leap 15</span><span class="sxs-lookup"><span data-stu-id="84b3b-132">openSUSE Leap 15</span></span>

<span data-ttu-id="84b3b-133">Von der Community unterstützte Releases:</span><span class="sxs-lookup"><span data-stu-id="84b3b-133">Community supported releases</span></span>

- <span data-ttu-id="84b3b-134">Ubuntu 18.10</span><span class="sxs-lookup"><span data-stu-id="84b3b-134">Ubuntu 18.10</span></span>
- <span data-ttu-id="84b3b-135">Ubuntu 19.10 und 20.10</span><span class="sxs-lookup"><span data-stu-id="84b3b-135">Ubuntu 19.10 and 20.10</span></span>
- <span data-ttu-id="84b3b-136">Arch Linux</span><span class="sxs-lookup"><span data-stu-id="84b3b-136">Arch Linux</span></span>
- <span data-ttu-id="84b3b-137">Kali</span><span class="sxs-lookup"><span data-stu-id="84b3b-137">Kali</span></span>
- <span data-ttu-id="84b3b-138">Raspbian (experimentell)</span><span class="sxs-lookup"><span data-stu-id="84b3b-138">Raspbian (experimental)</span></span>

<span data-ttu-id="84b3b-139">Alternative Installationsmethoden</span><span class="sxs-lookup"><span data-stu-id="84b3b-139">Alternate install methods</span></span>

- <span data-ttu-id="84b3b-140">Snap-Paket</span><span class="sxs-lookup"><span data-stu-id="84b3b-140">Snap Package</span></span>
- <span data-ttu-id="84b3b-141">Archive der Binärdateien</span><span class="sxs-lookup"><span data-stu-id="84b3b-141">Binary Archives</span></span>
- <span data-ttu-id="84b3b-142">Globales .NET-Tool</span><span class="sxs-lookup"><span data-stu-id="84b3b-142">.NET Global tool</span></span>

## <a name="ubuntu-1604"></a><span data-ttu-id="84b3b-143">Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="84b3b-143">Ubuntu 16.04</span></span>

### <a name="installation-via-package-repository---ubuntu-1604"></a><span data-ttu-id="84b3b-144">Installation über das Paketrepository: Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="84b3b-144">Installation via Package Repository - Ubuntu 16.04</span></span>

<span data-ttu-id="84b3b-145">PowerShell für Linux wird in Paketrepositorys veröffentlicht, um die Installation und die Updates zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="84b3b-145">PowerShell for Linux is published to package repositories for easy installation and updates.</span></span>

<span data-ttu-id="84b3b-146">Folgende Methode wird bevorzugt:</span><span class="sxs-lookup"><span data-stu-id="84b3b-146">The preferred method is as follows:</span></span>

```sh
# Update the list of packages
sudo apt-get update
# Install pre-requisite packages.
sudo apt-get install -y wget apt-transport-https software-properties-common
# Download the Microsoft repository GPG keys
wget -q https://packages.microsoft.com/config/ubuntu/16.04/packages-microsoft-prod.deb
# Register the Microsoft repository GPG keys
sudo dpkg -i packages-microsoft-prod.deb
# Update the list of packages after we added packages.microsoft.com
sudo apt-get update
# Install PowerShell
sudo apt-get install -y powershell
# Start PowerShell
pwsh
```

<span data-ttu-id="84b3b-147">Registrieren Sie das Microsoft-Repository einmal als Superuser.</span><span class="sxs-lookup"><span data-stu-id="84b3b-147">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="84b3b-148">Nach der Registrierung können Sie PowerShell mit `sudo apt-get install powershell` aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="84b3b-148">After registration, you can update PowerShell with `sudo apt-get install powershell`.</span></span>

### <a name="installation-via-direct-download---ubuntu-1604"></a><span data-ttu-id="84b3b-149">Installation über einen direkten Download: Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="84b3b-149">Installation via Direct Download - Ubuntu 16.04</span></span>

<span data-ttu-id="84b3b-150">Laden Sie das Debian-Paket `powershell_7.1.3-1.ubuntu.16.04_amd64.deb` über die Seite [Freigaben][] auf den Ubuntu-Computer herunter.</span><span class="sxs-lookup"><span data-stu-id="84b3b-150">Download the Debian package `powershell_7.1.3-1.ubuntu.16.04_amd64.deb` from the [releases][] page onto the Ubuntu machine.</span></span>

<span data-ttu-id="84b3b-151">Führen Sie dann im Terminal folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="84b3b-151">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo dpkg -i powershell_7.1.3-1.ubuntu.16.04_amd64.deb
sudo apt-get install -f
```

> [!NOTE]
> <span data-ttu-id="84b3b-152">Der `dpkg -i`-Befehl schlägt mit nicht erfüllten Abhängigkeiten fehl.</span><span class="sxs-lookup"><span data-stu-id="84b3b-152">The `dpkg -i` command fails with unmet dependencies.</span></span> <span data-ttu-id="84b3b-153">Über den Befehl `apt-get install -f` werden diese Probleme behoben und die Konfiguration des PowerShell-Pakets abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="84b3b-153">The next command, `apt-get install -f` resolves these issues then finishes configuring the PowerShell package.</span></span>

### <a name="uninstallation---ubuntu-1604"></a><span data-ttu-id="84b3b-154">Deinstallation: Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="84b3b-154">Uninstallation - Ubuntu 16.04</span></span>

```sh
sudo apt-get remove powershell
```

## <a name="ubuntu-1804"></a><span data-ttu-id="84b3b-155">Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="84b3b-155">Ubuntu 18.04</span></span>

### <a name="installation-via-package-repository---ubuntu-1804"></a><span data-ttu-id="84b3b-156">Installation über das Paketrepository: Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="84b3b-156">Installation via Package Repository - Ubuntu 18.04</span></span>

<span data-ttu-id="84b3b-157">PowerShell für Linux wird in Paketrepositorys veröffentlicht, um die Installation und die Updates zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="84b3b-157">PowerShell for Linux is published to package repositories for easy installation and updates.</span></span>

<span data-ttu-id="84b3b-158">Folgende Methode wird bevorzugt:</span><span class="sxs-lookup"><span data-stu-id="84b3b-158">The preferred method is as follows:</span></span>

```sh
# Update the list of packages
sudo apt-get update
# Install pre-requisite packages.
sudo apt-get install -y wget apt-transport-https software-properties-common
# Download the Microsoft repository GPG keys
wget -q https://packages.microsoft.com/config/ubuntu/18.04/packages-microsoft-prod.deb
# Register the Microsoft repository GPG keys
sudo dpkg -i packages-microsoft-prod.deb
# Update the list of products
sudo apt-get update
# Enable the "universe" repositories
sudo add-apt-repository universe
# Install PowerShell
sudo apt-get install -y powershell
# Start PowerShell
pwsh
```

<span data-ttu-id="84b3b-159">Registrieren Sie das Microsoft-Repository einmal als Superuser.</span><span class="sxs-lookup"><span data-stu-id="84b3b-159">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="84b3b-160">Nach der Registrierung können Sie PowerShell mit `sudo apt-get install powershell` aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="84b3b-160">After registration, you can update PowerShell with `sudo apt-get install powershell`.</span></span>

### <a name="installation-via-direct-download---ubuntu-1804"></a><span data-ttu-id="84b3b-161">Installation über einen direkten Download: Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="84b3b-161">Installation via Direct Download - Ubuntu 18.04</span></span>

<span data-ttu-id="84b3b-162">Laden Sie das Debian-Paket `powershell_7.1.3-1.ubuntu.18.04_amd64.deb` über die Seite [Freigaben][] auf den Ubuntu-Computer herunter.</span><span class="sxs-lookup"><span data-stu-id="84b3b-162">Download the Debian package `powershell_7.1.3-1.ubuntu.18.04_amd64.deb` from the [releases][] page onto the Ubuntu machine.</span></span>

<span data-ttu-id="84b3b-163">Führen Sie dann im Terminal folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="84b3b-163">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo dpkg -i powershell_7.1.3-1.ubuntu.18.04_amd64.deb
sudo apt-get install -f
```

> [!NOTE]
> <span data-ttu-id="84b3b-164">Der `dpkg -i`-Befehl schlägt mit nicht erfüllten Abhängigkeiten fehl.</span><span class="sxs-lookup"><span data-stu-id="84b3b-164">The `dpkg -i` command fails with unmet dependencies.</span></span> <span data-ttu-id="84b3b-165">Über den Befehl `apt-get install -f` werden diese Probleme behoben und die Konfiguration des PowerShell-Pakets abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="84b3b-165">The next command, `apt-get install -f` resolves these issues then finishes configuring the PowerShell package.</span></span>

### <a name="uninstallation---ubuntu-1804"></a><span data-ttu-id="84b3b-166">Deinstallation: Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="84b3b-166">Uninstallation - Ubuntu 18.04</span></span>

```sh
sudo apt-get remove powershell
```

## <a name="ubuntu-2004"></a><span data-ttu-id="84b3b-167">Ubuntu 20.04</span><span class="sxs-lookup"><span data-stu-id="84b3b-167">Ubuntu 20.04</span></span>

### <a name="installation-via-package-repository---ubuntu-2004"></a><span data-ttu-id="84b3b-168">Installation über das Paketrepository: Ubuntu 20.04</span><span class="sxs-lookup"><span data-stu-id="84b3b-168">Installation via Package Repository - Ubuntu 20.04</span></span>

<span data-ttu-id="84b3b-169">PowerShell für Linux wird in Paketrepositorys veröffentlicht, um die Installation und die Updates zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="84b3b-169">PowerShell for Linux is published to package repositories for easy installation and updates.</span></span>

<span data-ttu-id="84b3b-170">Folgende Methode wird bevorzugt:</span><span class="sxs-lookup"><span data-stu-id="84b3b-170">The preferred method is as follows:</span></span>

```sh
# Update the list of packages
sudo apt-get update
# Install pre-requisite packages.
sudo apt-get install -y wget apt-transport-https software-properties-common
# Download the Microsoft repository GPG keys
wget -q https://packages.microsoft.com/config/ubuntu/20.04/packages-microsoft-prod.deb
# Register the Microsoft repository GPG keys
sudo dpkg -i packages-microsoft-prod.deb
# Update the list of products
sudo apt-get update
# Enable the "universe" repositories
sudo add-apt-repository universe
# Install PowerShell
sudo apt-get install -y powershell
# Start PowerShell
pwsh
```

<span data-ttu-id="84b3b-171">Registrieren Sie das Microsoft-Repository einmal als Superuser.</span><span class="sxs-lookup"><span data-stu-id="84b3b-171">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="84b3b-172">Nach der Registrierung können Sie PowerShell mit `sudo apt-get install powershell` aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="84b3b-172">After registration, you can update PowerShell with `sudo apt-get install powershell`.</span></span>

### <a name="installation-via-direct-download---ubuntu-2004"></a><span data-ttu-id="84b3b-173">Installation über direkten Download: Ubuntu 20.04</span><span class="sxs-lookup"><span data-stu-id="84b3b-173">Installation via Direct Download - Ubuntu 20.04</span></span>

<span data-ttu-id="84b3b-174">Laden Sie das Debian-Paket `powershell_7.1.3-1.ubuntu.20.04_amd64.deb` über die Seite [Freigaben][] auf den Ubuntu-Computer herunter.</span><span class="sxs-lookup"><span data-stu-id="84b3b-174">Download the Debian package `powershell_7.1.3-1.ubuntu.20.04_amd64.deb` from the [releases][] page onto the Ubuntu machine.</span></span>

<span data-ttu-id="84b3b-175">Führen Sie dann im Terminal folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="84b3b-175">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo dpkg -i powershell_7.1.3-1.ubuntu.20.04_amd64.deb
sudo apt-get install -f
```

> [!NOTE]
> <span data-ttu-id="84b3b-176">Der `dpkg -i`-Befehl schlägt mit nicht erfüllten Abhängigkeiten fehl.</span><span class="sxs-lookup"><span data-stu-id="84b3b-176">The `dpkg -i` command fails with unmet dependencies.</span></span> <span data-ttu-id="84b3b-177">Über den Befehl `apt-get install -f` werden diese Probleme behoben und die Konfiguration des PowerShell-Pakets abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="84b3b-177">The next command, `apt-get install -f` resolves these issues then finishes configuring the PowerShell package.</span></span>

### <a name="uninstallation---ubuntu-2004"></a><span data-ttu-id="84b3b-178">Deinstallation: Ubuntu 20.04</span><span class="sxs-lookup"><span data-stu-id="84b3b-178">Uninstallation - Ubuntu 20.04</span></span>

```sh
sudo apt-get remove powershell
```

## <a name="ubuntu-1810"></a><span data-ttu-id="84b3b-179">Ubuntu 18.10</span><span class="sxs-lookup"><span data-stu-id="84b3b-179">Ubuntu 18.10</span></span>

<span data-ttu-id="84b3b-180">Die Installation wird über `snapd` unterstützt.</span><span class="sxs-lookup"><span data-stu-id="84b3b-180">Installation is supported via `snapd`.</span></span> <span data-ttu-id="84b3b-181">Anweisungen finden Sie unter [Snap-Paket][snap].</span><span class="sxs-lookup"><span data-stu-id="84b3b-181">For instructions, see [Snap Package][snap].</span></span>

> [!NOTE]
> <span data-ttu-id="84b3b-182">Ubuntu 18.10 ist ein [Zwischenrelease](https://www.ubuntu.com/about/release-cycle), das von der [Community unterstützt](../powershell-support-lifecycle.md) wird.</span><span class="sxs-lookup"><span data-stu-id="84b3b-182">Ubuntu 18.10 is an [interim release](https://www.ubuntu.com/about/release-cycle) that's [community supported](../powershell-support-lifecycle.md).</span></span>

## <a name="ubuntu-1910-and-2010"></a><span data-ttu-id="84b3b-183">Ubuntu 19.10 und 20.10</span><span class="sxs-lookup"><span data-stu-id="84b3b-183">Ubuntu 19.10 and 20.10</span></span>

<span data-ttu-id="84b3b-184">Die Installation wird über `snapd` unterstützt.</span><span class="sxs-lookup"><span data-stu-id="84b3b-184">Installation is supported via `snapd`.</span></span> <span data-ttu-id="84b3b-185">Anweisungen finden Sie unter [Snap-Paket][snap].</span><span class="sxs-lookup"><span data-stu-id="84b3b-185">For instructions, see [Snap Package][snap].</span></span>

> [!NOTE]
> <span data-ttu-id="84b3b-186">Ubuntu 19.10 ist ein [Zwischenrelease](https://www.ubuntu.com/about/release-cycle) mit [Support durch die Community](../powershell-support-lifecycle.md).</span><span class="sxs-lookup"><span data-stu-id="84b3b-186">Ubuntu 19.10 is an [interim release](https://www.ubuntu.com/about/release-cycle) that's [community supported](../powershell-support-lifecycle.md).</span></span>

## <a name="debian-8"></a><span data-ttu-id="84b3b-187">Debian 8</span><span class="sxs-lookup"><span data-stu-id="84b3b-187">Debian 8</span></span>

### <a name="installation-via-package-repository---debian-8"></a><span data-ttu-id="84b3b-188">Installation über das Paketrepository: Debian 8</span><span class="sxs-lookup"><span data-stu-id="84b3b-188">Installation via Package Repository - Debian 8</span></span>

<span data-ttu-id="84b3b-189">PowerShell für Linux wird in Paketrepositorys veröffentlicht, um die Installation und die Updates zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="84b3b-189">PowerShell for Linux is published to package repositories for easy installation and updates.</span></span>

<span data-ttu-id="84b3b-190">Folgende Methode wird bevorzugt:</span><span class="sxs-lookup"><span data-stu-id="84b3b-190">The preferred method is as follows:</span></span>

```sh
# Install system components
sudo apt-get update
sudo apt-get install -y curl apt-transport-https

# Import the public repository GPG keys
curl https://packages.microsoft.com/keys/microsoft.asc | sudo apt-key add -

# Register the Microsoft Product feed
sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-debian-jessie-prod jessie main" > /etc/apt/sources.list.d/microsoft.list'

# Update the list of products
sudo apt-get update

# Install PowerShell
sudo apt-get install -y powershell

# Start PowerShell
pwsh
```

<span data-ttu-id="84b3b-191">Registrieren Sie das Microsoft-Repository einmal als Superuser.</span><span class="sxs-lookup"><span data-stu-id="84b3b-191">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="84b3b-192">Nach der Registrierung können Sie PowerShell mit `sudo apt-get install powershell` aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="84b3b-192">After registration, you can update PowerShell with `sudo apt-get install powershell`.</span></span>

## <a name="debian-9"></a><span data-ttu-id="84b3b-193">Debian 9</span><span class="sxs-lookup"><span data-stu-id="84b3b-193">Debian 9</span></span>

### <a name="installation-via-package-repository---debian-9"></a><span data-ttu-id="84b3b-194">Installation über das Paketrepository: Debian 9</span><span class="sxs-lookup"><span data-stu-id="84b3b-194">Installation via Package Repository - Debian 9</span></span>

<span data-ttu-id="84b3b-195">PowerShell für Linux wird in Paketrepositorys veröffentlicht, um die Installation und die Updates zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="84b3b-195">PowerShell for Linux is published to package repositories for easy installation and updates.</span></span>

<span data-ttu-id="84b3b-196">Folgende Methode wird bevorzugt:</span><span class="sxs-lookup"><span data-stu-id="84b3b-196">The preferred method is as follows:</span></span>

```sh
# Install system components
sudo apt-get update
sudo apt-get install -y curl gnupg apt-transport-https

# Import the public repository GPG keys
curl https://packages.microsoft.com/keys/microsoft.asc | sudo apt-key add -

# Register the Microsoft Product feed
sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-debian-stretch-prod stretch main" > /etc/apt/sources.list.d/microsoft.list'

# Update the list of products
sudo apt-get update

# Install PowerShell
sudo apt-get install -y powershell

# Start PowerShell
pwsh
```

<span data-ttu-id="84b3b-197">Registrieren Sie das Microsoft-Repository einmal als Superuser.</span><span class="sxs-lookup"><span data-stu-id="84b3b-197">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="84b3b-198">Nach der Registrierung können Sie PowerShell mit `sudo apt-get install powershell` aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="84b3b-198">After registration, you can update PowerShell with `sudo apt-get install powershell`.</span></span>

### <a name="installation-via-direct-download---debian-9"></a><span data-ttu-id="84b3b-199">Installation über einen direkten Download: Debian 9</span><span class="sxs-lookup"><span data-stu-id="84b3b-199">Installation via Direct Download - Debian 9</span></span>

<span data-ttu-id="84b3b-200">Laden Sie das Debian-Paket `powershell_7.1.3-1.debian.9_amd64.deb` über die Seite [Freigaben][] auf den Debian-Computer herunter.</span><span class="sxs-lookup"><span data-stu-id="84b3b-200">Download the Debian package `powershell_7.1.3-1.debian.9_amd64.deb` from the [releases][] page onto the Debian machine.</span></span>

<span data-ttu-id="84b3b-201">Führen Sie dann im Terminal folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="84b3b-201">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo dpkg -i powershell_7.1.3-1.debian.9_amd64.deb
sudo apt-get install -f
```

### <a name="uninstallation---debian-9"></a><span data-ttu-id="84b3b-202">Deinstallation: Debian 9</span><span class="sxs-lookup"><span data-stu-id="84b3b-202">Uninstallation - Debian 9</span></span>

```sh
sudo apt-get remove powershell
```

## <a name="debian-10"></a><span data-ttu-id="84b3b-203">Debian 10</span><span class="sxs-lookup"><span data-stu-id="84b3b-203">Debian 10</span></span>

> [!NOTE]
> <span data-ttu-id="84b3b-204">Debian 10 wird nur in PowerShell 7.0 und höher unterstützt.</span><span class="sxs-lookup"><span data-stu-id="84b3b-204">Debian 10 is only supported in PowerShell 7.0 and newer.</span></span>

### <a name="installation-via-package-repository---debian-10"></a><span data-ttu-id="84b3b-205">Installation über das Paketrepository: Debian 10</span><span class="sxs-lookup"><span data-stu-id="84b3b-205">Installation via Package Repository - Debian 10</span></span>

<span data-ttu-id="84b3b-206">PowerShell für Linux wird in Paketrepositorys veröffentlicht, um die Installation und die Updates zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="84b3b-206">PowerShell for Linux is published to package repositories for easy installation and updates.</span></span>

<span data-ttu-id="84b3b-207">Folgende Methode wird bevorzugt:</span><span class="sxs-lookup"><span data-stu-id="84b3b-207">The preferred method is as follows:</span></span>

```sh
# Download the Microsoft repository GPG keys
wget https://packages.microsoft.com/config/debian/10/packages-microsoft-prod.deb

# Register the Microsoft repository GPG keys
sudo dpkg -i packages-microsoft-prod.deb

# Update the list of products
sudo apt-get update

# Install PowerShell
sudo apt-get install -y powershell

# Start PowerShell
pwsh
```

### <a name="installation-via-direct-download---debian-10"></a><span data-ttu-id="84b3b-208">Installation über direkten Download: Debian 10</span><span class="sxs-lookup"><span data-stu-id="84b3b-208">Installation via Direct Download - Debian 10</span></span>

<span data-ttu-id="84b3b-209">Laden Sie das tar.gz-Paket `powershell-7.1.3-linux-x64.tar.gz` über die Seite [Freigaben][] auf den Debian-Computer herunter.</span><span class="sxs-lookup"><span data-stu-id="84b3b-209">Download the tar.gz package `powershell-7.1.3-linux-x64.tar.gz` from the [releases][] page onto the Debian machine.</span></span>

<span data-ttu-id="84b3b-210">Führen Sie dann im Terminal folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="84b3b-210">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo apt-get update
# install the requirements
sudo apt-get install -y \
        less \
        locales \
        ca-certificates \
        libicu63 \
        libssl1.1 \
        libc6 \
        libgcc1 \
        libgssapi-krb5-2 \
        liblttng-ust0 \
        libstdc++6 \
        zlib1g \
        curl

# Download the powershell '.tar.gz' archive
curl -L  https://github.com/PowerShell/PowerShell/releases/download/v7.1.3/powershell-7.1.3-linux-x64.tar.gz -o /tmp/powershell.tar.gz

# Create the target folder where powershell will be placed
sudo mkdir -p /opt/microsoft/powershell/7

# Expand powershell to the target folder
sudo tar zxf /tmp/powershell.tar.gz -C /opt/microsoft/powershell/7

# Set execute permissions
sudo chmod +x /opt/microsoft/powershell/7/pwsh

# Create the symbolic link that points to pwsh
sudo ln -s /opt/microsoft/powershell/7/pwsh /usr/bin/pwsh

# Start PowerShell
pwsh
```

## <a name="alpine-39-and-310"></a><span data-ttu-id="84b3b-211">Alpine 3.9 und 3.10</span><span class="sxs-lookup"><span data-stu-id="84b3b-211">Alpine 3.9 and 3.10</span></span>

> [!NOTE]
> <span data-ttu-id="84b3b-212">Alpine 3.9 und 3.10 werden nur in PowerShell 7.0 und höher unterstützt.</span><span class="sxs-lookup"><span data-stu-id="84b3b-212">Alpine 3.9 and 3.10 are only supported in PowerShell 7.0 and newer.</span></span>

### <a name="installation-via-direct-download---alpine-39-and-310"></a><span data-ttu-id="84b3b-213">Installation über direkten Download: Alpine 3.9 und 3.10</span><span class="sxs-lookup"><span data-stu-id="84b3b-213">Installation via Direct Download - Alpine 3.9 and 3.10</span></span>

<span data-ttu-id="84b3b-214">Laden Sie das tar.gz-Paket `powershell-7.1.3-linux-alpine-x64.tar.gz` über die Seite [Freigaben][] auf den Alpine-Computer herunter.</span><span class="sxs-lookup"><span data-stu-id="84b3b-214">Download the tar.gz package `powershell-7.1.3-linux-alpine-x64.tar.gz` from the [releases][] page onto the Alpine machine.</span></span>

<span data-ttu-id="84b3b-215">Führen Sie dann im Terminal folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="84b3b-215">Then, in the terminal, execute the following commands:</span></span>

```sh
# install the requirements
sudo apk add --no-cache \
    ca-certificates \
    less \
    ncurses-terminfo-base \
    krb5-libs \
    libgcc \
    libintl \
    libssl1.1 \
    libstdc++ \
    tzdata \
    userspace-rcu \
    zlib \
    icu-libs \
    curl

sudo apk -X https://dl-cdn.alpinelinux.org/alpine/edge/main add --no-cache \
    lttng-ust

# Download the powershell '.tar.gz' archive
curl -L https://github.com/PowerShell/PowerShell/releases/download/v7.1.3/powershell-7.1.3-linux-alpine-x64.tar.gz -o /tmp/powershell.tar.gz

# Create the target folder where powershell will be placed
sudo mkdir -p /opt/microsoft/powershell/7

# Expand powershell to the target folder
sudo tar zxf /tmp/powershell.tar.gz -C /opt/microsoft/powershell/7

# Set execute permissions
sudo chmod +x /opt/microsoft/powershell/7/pwsh

# Create the symbolic link that points to pwsh
sudo ln -s /opt/microsoft/powershell/7/pwsh /usr/bin/pwsh

# Start PowerShell
pwsh
```

## <a name="centos-7"></a><span data-ttu-id="84b3b-216">CentOS 7:</span><span class="sxs-lookup"><span data-stu-id="84b3b-216">CentOS 7</span></span>

> [!NOTE]
> <span data-ttu-id="84b3b-217">Dieses Paket funktioniert unter Oracle Linux 7.</span><span class="sxs-lookup"><span data-stu-id="84b3b-217">This package works on Oracle Linux 7.</span></span>

### <a name="installation-via-package-repository-preferred---centos-7"></a><span data-ttu-id="84b3b-218">Installation über das Paketrepository (bevorzugt): CentOS 7</span><span class="sxs-lookup"><span data-stu-id="84b3b-218">Installation via Package Repository (preferred) - CentOS 7</span></span>

<span data-ttu-id="84b3b-219">PowerShell für Linux wird in offiziellen Microsoft-Repositorys veröffentlicht, um die Installation und die Updates zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="84b3b-219">PowerShell for Linux is published to official Microsoft repositories for easy installation and updates.</span></span>

```sh
# Register the Microsoft RedHat repository
curl https://packages.microsoft.com/config/rhel/7/prod.repo | sudo tee /etc/yum.repos.d/microsoft.repo

# Install PowerShell
sudo yum install -y powershell

# Start PowerShell
pwsh
```

<span data-ttu-id="84b3b-220">Registrieren Sie das Microsoft-Repository einmal als Superuser.</span><span class="sxs-lookup"><span data-stu-id="84b3b-220">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="84b3b-221">Nach der Registrierung können Sie PowerShell mit `sudo yum update powershell` aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="84b3b-221">After registration, you can update PowerShell with `sudo yum update powershell`.</span></span>

### <a name="installation-via-direct-download---centos-7"></a><span data-ttu-id="84b3b-222">Installation über einen direkten Download: CentOS 7</span><span class="sxs-lookup"><span data-stu-id="84b3b-222">Installation via Direct Download - CentOS 7</span></span>

<span data-ttu-id="84b3b-223">Für [CentOS 7][]: Laden Sie das RPM-Paket `powershell-7.1.3-1.rhel.7.x86_64.rpm` über die Seite [Freigaben][] auf den CentOS-Computer herunter.</span><span class="sxs-lookup"><span data-stu-id="84b3b-223">Using [CentOS 7][], download the RPM package `powershell-7.1.3-1.rhel.7.x86_64.rpm` from the [releases][] page onto the CentOS machine.</span></span>

<span data-ttu-id="84b3b-224">Führen Sie dann im Terminal folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="84b3b-224">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo yum install powershell-7.1.3-1.rhel.7.x86_64.rpm
```

<span data-ttu-id="84b3b-225">Sie können RPM ohne Download installieren:</span><span class="sxs-lookup"><span data-stu-id="84b3b-225">You can install the RPM without the intermediate step of downloading it:</span></span>

```sh
sudo yum install https://github.com/PowerShell/PowerShell/releases/download/v7.1.3/powershell-7.1.3-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---centos-7"></a><span data-ttu-id="84b3b-226">Deinstallation: CentOS 7</span><span class="sxs-lookup"><span data-stu-id="84b3b-226">Uninstallation - CentOS 7</span></span>

```sh
sudo yum remove powershell
```

[CentOS 7]: https://www.centos.org/download/

## <a name="red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="84b3b-228">Red Hat Enterprise Linux 7 (RHEL)</span><span class="sxs-lookup"><span data-stu-id="84b3b-228">Red Hat Enterprise Linux (RHEL) 7</span></span>

### <a name="installation-via-package-repository-preferred---red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="84b3b-229">Installation über ein Paketrepository (bevorzugt): Red Hat Enterprise Linux 7 (RHEL)</span><span class="sxs-lookup"><span data-stu-id="84b3b-229">Installation via Package Repository (preferred) - Red Hat Enterprise Linux (RHEL) 7</span></span>

<span data-ttu-id="84b3b-230">PowerShell für Linux wird in offiziellen Microsoft-Repositorys veröffentlicht, um die Installation und die Updates zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="84b3b-230">PowerShell for Linux is published to official Microsoft repositories for easy installation and updates.</span></span>

```sh
# Register the Microsoft RedHat repository
curl https://packages.microsoft.com/config/rhel/7/prod.repo | sudo tee /etc/yum.repos.d/microsoft.repo

# Install PowerShell
sudo yum install -y powershell

# Start PowerShell
pwsh
```

<span data-ttu-id="84b3b-231">Registrieren Sie das Microsoft-Repository einmal als Superuser.</span><span class="sxs-lookup"><span data-stu-id="84b3b-231">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="84b3b-232">Nach der Registrierung können Sie PowerShell mit `sudo yum update powershell` aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="84b3b-232">After registration, you can update PowerShell with `sudo yum update powershell`.</span></span>

### <a name="installation-via-direct-download---red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="84b3b-233">Installation über einen direkten Download: Red Hat Enterprise Linux 7 (RHEL)</span><span class="sxs-lookup"><span data-stu-id="84b3b-233">Installation via Direct Download - Red Hat Enterprise Linux (RHEL) 7</span></span>

<span data-ttu-id="84b3b-234">Laden Sie das RPM-Paket `powershell-7.1.3-1.rhel.7.x86_64.rpm` über die Seite [Freigaben][] auf den Red Hat Enterprise Linux-Computer herunter.</span><span class="sxs-lookup"><span data-stu-id="84b3b-234">Download the RPM package `powershell-7.1.3-1.rhel.7.x86_64.rpm` from the [releases][] page onto the Red Hat Enterprise Linux machine.</span></span>

<span data-ttu-id="84b3b-235">Führen Sie dann im Terminal folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="84b3b-235">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo yum install powershell-7.1.3-1.rhel.7.x86_64.rpm
```

<span data-ttu-id="84b3b-236">Sie können RPM ohne Download installieren:</span><span class="sxs-lookup"><span data-stu-id="84b3b-236">You can install the RPM without the intermediate step of downloading it:</span></span>

```sh
sudo yum install https://github.com/PowerShell/PowerShell/releases/download/v7.1.3/powershell-7.1.3-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="84b3b-237">Deinstallation: Red Hat Enterprise Linux 7 (RHEL)</span><span class="sxs-lookup"><span data-stu-id="84b3b-237">Uninstallation - Red Hat Enterprise Linux (RHEL) 7</span></span>

```sh
sudo yum remove powershell
```

## <a name="opensuse"></a><span data-ttu-id="84b3b-238">openSUSE</span><span class="sxs-lookup"><span data-stu-id="84b3b-238">openSUSE</span></span>

### <a name="installation---opensuse-423"></a><span data-ttu-id="84b3b-239">Installation: openSUSE 42.3</span><span class="sxs-lookup"><span data-stu-id="84b3b-239">Installation - openSUSE 42.3</span></span>

```sh
# Install dependencies
zypper update && zypper --non-interactive install curl tar libicu52_1

# Download the powershell '.tar.gz' archive
curl -L https://github.com/PowerShell/PowerShell/releases/download/v7.1.3/powershell-7.1.3-linux-x64.tar.gz -o /tmp/powershell.tar.gz

# Create the target folder where powershell will be placed
mkdir -p /opt/microsoft/powershell/7

# Expand powershell to the target folder
tar zxf /tmp/powershell.tar.gz -C /opt/microsoft/powershell/7

# Set execute permissions
chmod +x /opt/microsoft/powershell/7/pwsh

# Create the symbolic link that points to pwsh
ln -s /opt/microsoft/powershell/7/pwsh /usr/bin/pwsh

# Start PowerShell
pwsh
```

### <a name="installation---opensuse-leap-15"></a><span data-ttu-id="84b3b-240">Installation: openSUSE Leap 15</span><span class="sxs-lookup"><span data-stu-id="84b3b-240">Installation - openSUSE Leap 15</span></span>

```sh
# Install dependencies
zypper update && zypper --non-interactive install curl tar gzip libopenssl1_0_0 libicu60_2

# Download the powershell '.tar.gz' archive
curl -L https://github.com/PowerShell/PowerShell/releases/download/v7.1.3/powershell-7.1.3-linux-x64.tar.gz -o /tmp/powershell.tar.gz

# Create the target folder where powershell will be placed
mkdir -p /opt/microsoft/powershell/7

# Expand powershell to the target folder
tar zxf /tmp/powershell.tar.gz -C /opt/microsoft/powershell/7

# Set execute permissions
chmod +x /opt/microsoft/powershell/7/pwsh

# Create the symbolic link that points to pwsh
ln -s /opt/microsoft/powershell/7/pwsh /usr/bin/pwsh

# Start PowerShell
pwsh
```

### <a name="uninstallation---opensuse-423-opensuse-leap-15"></a><span data-ttu-id="84b3b-241">Deinstallation: openSUSE 42.3, openSUSE Leap 15</span><span class="sxs-lookup"><span data-stu-id="84b3b-241">Uninstallation - openSUSE 42.3, openSUSE Leap 15</span></span>

```sh
rm -rf /usr/bin/pwsh /opt/microsoft/powershell
```

## <a name="fedora"></a><span data-ttu-id="84b3b-242">Fedora</span><span class="sxs-lookup"><span data-stu-id="84b3b-242">Fedora</span></span>

> [!NOTE]
> <span data-ttu-id="84b3b-243">Fedora 28 wird nur in PowerShell 6.1 und höher unterstützt.</span><span class="sxs-lookup"><span data-stu-id="84b3b-243">Fedora 28 is only supported in PowerShell 6.1 and newer.</span></span>

> [!NOTE]
> <span data-ttu-id="84b3b-244">Fedora 29 und 30 werden nur in PowerShell 7.0 und höher unterstützt.</span><span class="sxs-lookup"><span data-stu-id="84b3b-244">Fedora 29 and 30 are only supported in PowerShell 7.0 and newer.</span></span>

### <a name="installation-via-package-repository-preferred---fedora-28-29-and-30"></a><span data-ttu-id="84b3b-245">Installation über das Paketrepository (bevorzugt): Fedora 28, 29 und 30</span><span class="sxs-lookup"><span data-stu-id="84b3b-245">Installation via Package Repository (preferred) - Fedora 28, 29, and 30</span></span>

<span data-ttu-id="84b3b-246">PowerShell für Linux wird in offiziellen Microsoft-Repositorys veröffentlicht, um die Installation und die Updates zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="84b3b-246">PowerShell for Linux is published to official Microsoft repositories for easy installation and updates.</span></span>

```sh
# Register the Microsoft signature key
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc

# Register the Microsoft RedHat repository
curl https://packages.microsoft.com/config/rhel/7/prod.repo | sudo tee /etc/yum.repos.d/microsoft.repo

# Update the list of products
sudo dnf check-update

# Install a system component
sudo dnf install compat-openssl10

# Install PowerShell
sudo dnf install -y powershell

# Start PowerShell
pwsh
```

### <a name="installation-via-direct-download---fedora-28-29-and-30"></a><span data-ttu-id="84b3b-247">Installation über direkten Download: Fedora 28, 29 und 30</span><span class="sxs-lookup"><span data-stu-id="84b3b-247">Installation via Direct Download - Fedora 28, 29, and 30</span></span>

<span data-ttu-id="84b3b-248">Laden Sie das RPM-Paket `powershell-7.1.3-1.rhel.7.x86_64.rpm` über die Seite [Freigaben][] auf den Fedora-Computer herunter.</span><span class="sxs-lookup"><span data-stu-id="84b3b-248">Download the RPM package `powershell-7.1.3-1.rhel.7.x86_64.rpm` from the [releases][] page onto the Fedora machine.</span></span>

<span data-ttu-id="84b3b-249">Führen Sie dann im Terminal folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="84b3b-249">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo dnf install compat-openssl10
sudo dnf install powershell-7.1.3-1.rhel.7.x86_64.rpm
```

<span data-ttu-id="84b3b-250">Sie können RPM ohne Download installieren:</span><span class="sxs-lookup"><span data-stu-id="84b3b-250">You can install the RPM without the intermediate step of downloading it:</span></span>

```sh
sudo dnf install compat-openssl10
sudo dnf install https://github.com/PowerShell/PowerShell/releases/download/v7.1.3/powershell-7.1.3-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---fedora-28-29-and-30"></a><span data-ttu-id="84b3b-251">Deinstallation: Fedora 28, 29 und 30</span><span class="sxs-lookup"><span data-stu-id="84b3b-251">Uninstallation - Fedora 28, 29, and 30</span></span>

```sh
sudo dnf remove powershell
```

## <a name="arch-linux"></a><span data-ttu-id="84b3b-252">Arch Linux</span><span class="sxs-lookup"><span data-stu-id="84b3b-252">Arch Linux</span></span>

> [!NOTE]
> <span data-ttu-id="84b3b-253">Arch Linux wird offiziell nicht von Microsoft unterstützt und daher von der Community verwaltet.</span><span class="sxs-lookup"><span data-stu-id="84b3b-253">Arch support is not officially supported by Microsoft and is maintained by the community.</span></span>

<span data-ttu-id="84b3b-254">PowerShell ist über das Benutzerrepository [Arch Linux][] verfügbar.</span><span class="sxs-lookup"><span data-stu-id="84b3b-254">PowerShell is available from the [Arch Linux][] User Repository (AUR).</span></span>

- <span data-ttu-id="84b3b-255">Es kann gemeinsam mit dem [zuletzt markierten Release][arch-release] kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="84b3b-255">It can be compiled with the [latest tagged release][arch-release]</span></span>
- <span data-ttu-id="84b3b-256">Es kann gemeinsam vom [letzten Commit für den Master][arch-git] aus kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="84b3b-256">It can be compiled from the [latest commit to master][arch-git]</span></span>
- <span data-ttu-id="84b3b-257">Es kann mithilfe der [zuletzt zur Veröffentlichung bestimmten Binärdatei][arch-bin] installiert werden.</span><span class="sxs-lookup"><span data-stu-id="84b3b-257">It can be installed using the [latest release binary][arch-bin]</span></span>

<span data-ttu-id="84b3b-258">Pakete im Benutzerrepository „Arch Linux“ werden von der Community verwaltet. Es gibt keinen offiziellen Support.</span><span class="sxs-lookup"><span data-stu-id="84b3b-258">Packages in the AUR are community maintained; there's no official support.</span></span>

<span data-ttu-id="84b3b-259">Weitere Informationen zum Installieren von Paketen aus dem Benutzerrepository „Arch Linux“ finden Sie im [Arch Linux-Wiki](https://wiki.archlinux.org/index.php/Arch_User_Repository#Installing_packages) oder unter [Verwenden von PowerShell in Docker](powershell-in-docker.md).</span><span class="sxs-lookup"><span data-stu-id="84b3b-259">For more information on installing packages from the AUR, see the [Arch Linux wiki](https://wiki.archlinux.org/index.php/Arch_User_Repository#Installing_packages) or [Using PowerShell in Docker](powershell-in-docker.md).</span></span>

[Arch Linux]: https://www.archlinux.org/download/
[arch-release]: https://aur.archlinux.org/packages/powershell/
[arch-git]: https://aur.archlinux.org/packages/powershell-git/
[arch-bin]: https://aur.archlinux.org/packages/powershell-bin/

## <a name="snap-package"></a><span data-ttu-id="84b3b-261">Snap-Paket</span><span class="sxs-lookup"><span data-stu-id="84b3b-261">Snap Package</span></span>

### <a name="getting-snapd"></a><span data-ttu-id="84b3b-262">Abrufen von snapd</span><span class="sxs-lookup"><span data-stu-id="84b3b-262">Getting snapd</span></span>

<span data-ttu-id="84b3b-263">`snapd` ist für das Ausführen von Snap-Paketen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="84b3b-263">`snapd` is required to run snaps.</span></span> <span data-ttu-id="84b3b-264">Halten Sie sich an [diese Anweisungen](https://docs.snapcraft.io/core/install), um sicherzustellen, dass `snapd` installiert ist.</span><span class="sxs-lookup"><span data-stu-id="84b3b-264">Use [these instructions](https://docs.snapcraft.io/core/install) to make sure you have `snapd` installed.</span></span>

### <a name="installation-via-snap"></a><span data-ttu-id="84b3b-265">Installation über Snap</span><span class="sxs-lookup"><span data-stu-id="84b3b-265">Installation via Snap</span></span>

<span data-ttu-id="84b3b-266">PowerShell für Linux wird im [Snap-Store](https://snapcraft.io/store) veröffentlicht, um die Installation und die Updates zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="84b3b-266">PowerShell for Linux is published to the [Snap store](https://snapcraft.io/store) for easy installation and updates.</span></span>

<span data-ttu-id="84b3b-267">Folgende Methode wird bevorzugt:</span><span class="sxs-lookup"><span data-stu-id="84b3b-267">The preferred method is as follows:</span></span>

```sh
# Install PowerShell
sudo snap install powershell --classic

# Start PowerShell
pwsh
```

<span data-ttu-id="84b3b-268">Gehen Sie folgendermaßen vor, wenn Sie eine Vorschauversion installieren möchten:</span><span class="sxs-lookup"><span data-stu-id="84b3b-268">To install a preview version, use the following method:</span></span>

```sh
# Install PowerShell
sudo snap install powershell-preview --classic

# Start PowerShell
pwsh-preview
```

<span data-ttu-id="84b3b-269">Nach der Installation wird für Snap automatisch ein Upgrade durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="84b3b-269">After installation, Snap will automatically upgrade.</span></span> <span data-ttu-id="84b3b-270">Sie können ein Upgrade mit `sudo snap refresh powershell` oder `sudo snap refresh powershell-preview` auslösen.</span><span class="sxs-lookup"><span data-stu-id="84b3b-270">You can trigger an upgrade using `sudo snap refresh powershell` or `sudo snap refresh powershell-preview`.</span></span>

### <a name="uninstallation"></a><span data-ttu-id="84b3b-271">Deinstallation</span><span class="sxs-lookup"><span data-stu-id="84b3b-271">Uninstallation</span></span>

```sh
sudo snap remove powershell
```

<span data-ttu-id="84b3b-272">oder</span><span class="sxs-lookup"><span data-stu-id="84b3b-272">or</span></span>

```sh
sudo snap remove powershell-preview
```

## <a name="kali"></a><span data-ttu-id="84b3b-273">Kali</span><span class="sxs-lookup"><span data-stu-id="84b3b-273">Kali</span></span>

> [!NOTE]
> <span data-ttu-id="84b3b-274">Kali wird offiziell nicht von Microsoft unterstützt und daher von der Community verwaltet.</span><span class="sxs-lookup"><span data-stu-id="84b3b-274">Kali support is not officially supported by Microsoft and is maintained by the community.</span></span>

### <a name="installation---kali"></a><span data-ttu-id="84b3b-275">Installation: Kali</span><span class="sxs-lookup"><span data-stu-id="84b3b-275">Installation - Kali</span></span>

```sh
# Install PowerShell package
apt update && apt -y install powershell

# Start PowerShell
pwsh
```

### <a name="uninstallation---kali"></a><span data-ttu-id="84b3b-276">Deinstallation: Kali</span><span class="sxs-lookup"><span data-stu-id="84b3b-276">Uninstallation - Kali</span></span>

```sh
# Uninstall PowerShell package
apt -y remove powershell
```

## <a name="support-for-arm-processors"></a><span data-ttu-id="84b3b-277">Unterstützung für ARM-Prozessoren</span><span class="sxs-lookup"><span data-stu-id="84b3b-277">Support for Arm processors</span></span>

<span data-ttu-id="84b3b-278">PowerShell kann unter einigen Linux-Distributionen installiert werden.</span><span class="sxs-lookup"><span data-stu-id="84b3b-278">PowerShell can be installed on some Linux distributions.</span></span> <span data-ttu-id="84b3b-279">PowerShell benötigt die .NET-Unterstützung von ARM.</span><span class="sxs-lookup"><span data-stu-id="84b3b-279">PowerShell is dependent on .NET support of Arm.</span></span> <span data-ttu-id="84b3b-280">PowerShell wird unter den folgenden Distributionen unterstützt:</span><span class="sxs-lookup"><span data-stu-id="84b3b-280">PowerShell is supported on the following distributions:</span></span>

- <span data-ttu-id="84b3b-281">Alpine Linux v3.11+: .NET unterstützt Arm64, aber zurzeit gibt es noch kein installierbares Paket für PowerShell.</span><span class="sxs-lookup"><span data-stu-id="84b3b-281">Alpine Linux v3.11+ - .NET supports Arm64 but there is no installable package for PowerShell at this time</span></span>
- <span data-ttu-id="84b3b-282">Raspbian: Die Installationsanweisungen finden Sie weiter unten.</span><span class="sxs-lookup"><span data-stu-id="84b3b-282">Raspbian - see the installation instructions below</span></span>
- <span data-ttu-id="84b3b-283">Debian v9+: Unterstützt Arm32 und Arm64 über die Installationsmethode [Archive der Binärdateien](#binary-archives).</span><span class="sxs-lookup"><span data-stu-id="84b3b-283">Debian v9+ - supports Arm32 and Arm64 using the [Binary Archive](#binary-archives) installation method</span></span>
- <span data-ttu-id="84b3b-284">Ubuntu 20.10, 20.04, 18.04, 16.04: Unterstützt Arm32 und Arm64 über die Installationsmethode [Archive der Binärdateien](#binary-archives).</span><span class="sxs-lookup"><span data-stu-id="84b3b-284">Ubuntu 20.10, 20.04, 18.04, 16.04 - supports Arm32 and Arm64 using the [Binary Archive](#binary-archives) installation method</span></span>

## <a name="raspbian"></a><span data-ttu-id="84b3b-285">Raspbian</span><span class="sxs-lookup"><span data-stu-id="84b3b-285">Raspbian</span></span>

> [!NOTE]
> <span data-ttu-id="84b3b-286">Die Unterstützung von Raspbian wird noch getestet.</span><span class="sxs-lookup"><span data-stu-id="84b3b-286">Raspbian support is experimental.</span></span>

<span data-ttu-id="84b3b-287">Derzeit wird PowerShell nur unter Raspbian Stretch unterstützt.</span><span class="sxs-lookup"><span data-stu-id="84b3b-287">Currently, PowerShell is only supported on Raspbian Stretch.</span></span>

<span data-ttu-id="84b3b-288">Außerdem funktionieren CoreCLR und PowerShell nur auf Geräten mit Pi 2 und Pi 3, da andere Geräte, wie z. B. [Pi Zero](https://github.com/dotnet/coreclr/issues/10605), einen nicht unterstützten Prozessor haben.</span><span class="sxs-lookup"><span data-stu-id="84b3b-288">CoreCLR and PowerShell will only work on Pi 2 and Pi 3 devices as other devices, like [Pi Zero](https://github.com/dotnet/coreclr/issues/10605), have an unsupported processor.</span></span>

<span data-ttu-id="84b3b-289">Laden Sie [Raspbian Stretch](https://www.raspberrypi.org/downloads/raspbian/) herunter, und folgen Sie den [Installationsanweisungen](https://www.raspberrypi.org/documentation/installation/installing-images/README.md), um es zu installieren.</span><span class="sxs-lookup"><span data-stu-id="84b3b-289">Download [Raspbian Stretch](https://www.raspberrypi.org/downloads/raspbian/) and follow the [installation instructions](https://www.raspberrypi.org/documentation/installation/installing-images/README.md) to get it onto your Pi.</span></span>

### <a name="installation---raspbian"></a><span data-ttu-id="84b3b-290">Installation: Raspbian</span><span class="sxs-lookup"><span data-stu-id="84b3b-290">Installation - Raspbian</span></span>

```sh
###################################
# Prerequisites

# Update package lists
sudo apt-get update

# Install libunwind8 and libssl1.0
# Regex is used to ensure that we do not install libssl1.0-dev, as it is a variant that is not required
sudo apt-get install '^libssl1.0.[0-9]$' libunwind8 -y

###################################
# Download and extract PowerShell

# Grab the latest tar.gz
wget https://github.com/PowerShell/PowerShell/releases/download/v7.1.3/powershell-7.1.3-linux-arm32.tar.gz

# Make folder to put powershell
mkdir ~/powershell

# Unpack the tar.gz file
tar -xvf ./powershell-7.1.3-linux-arm32.tar.gz -C ~/powershell

# Start PowerShell
~/powershell/pwsh
```

<span data-ttu-id="84b3b-291">Optional können Sie eine symbolische Verknüpfung erstellen, damit Sie PowerShell ohne Angabe des Pfads zur Binärdatei `pwsh` starten können.</span><span class="sxs-lookup"><span data-stu-id="84b3b-291">Optionally, you can create a symbolic link to start PowerShell without specifying the path to the `pwsh` binary.</span></span>

```sh
# Start PowerShell from bash with sudo to create a symbolic link
sudo ~/powershell/pwsh -c New-Item -ItemType SymbolicLink -Path "/usr/bin/pwsh" -Target "$PSHOME/pwsh" -Force

# alternatively you can run following to create a symbolic link
# sudo ln -s ~/powershell/pwsh /usr/bin/pwsh

# Now to start PowerShell you can just run "pwsh"
```

### <a name="uninstallation---raspbian"></a><span data-ttu-id="84b3b-292">Deinstallation: Raspbian</span><span class="sxs-lookup"><span data-stu-id="84b3b-292">Uninstallation - Raspbian</span></span>

```sh
rm -rf ~/powershell
```

## <a name="installing-preview-releases"></a><span data-ttu-id="84b3b-293">Installieren von Vorschauversionen</span><span class="sxs-lookup"><span data-stu-id="84b3b-293">Installing Preview Releases</span></span>

<span data-ttu-id="84b3b-294">Wenn eine Vorschauversion von PowerShell für Linux über ein Paketrepository installiert wird, ändert sich der Paketname von `powershell` in `powershell-preview`.</span><span class="sxs-lookup"><span data-stu-id="84b3b-294">When installing a PowerShell Preview release for Linux via a Package Repository, the package name changes from `powershell` to `powershell-preview`.</span></span>

<span data-ttu-id="84b3b-295">Bei einer Installation über einen direkten Download wird nur der Dateiname geändert.</span><span class="sxs-lookup"><span data-stu-id="84b3b-295">Installing via direct download doesn't change, other than the file name.</span></span>

<span data-ttu-id="84b3b-296">In der nachfolgenden Tabelle werden die Befehle aufgeführt, über die Sie Pakete stabiler Versionen und von Vorschauversionen mithilfe der verschiedenen Paket-Manager installieren können:</span><span class="sxs-lookup"><span data-stu-id="84b3b-296">The following table contains the commands to install the stable and preview packages using the various package managers:</span></span>

| <span data-ttu-id="84b3b-297">Distribution(en)</span><span class="sxs-lookup"><span data-stu-id="84b3b-297">Distribution(s)</span></span> |            <span data-ttu-id="84b3b-298">Befehl für die stabile Version</span><span class="sxs-lookup"><span data-stu-id="84b3b-298">Stable Command</span></span>            |               <span data-ttu-id="84b3b-299">Befehl für die Vorschauversion</span><span class="sxs-lookup"><span data-stu-id="84b3b-299">Preview Command</span></span>                |
| --------------- | ------------------------------------ | -------------------------------------------- |
| <span data-ttu-id="84b3b-300">Ubuntu, Debian</span><span class="sxs-lookup"><span data-stu-id="84b3b-300">Ubuntu, Debian</span></span>  | `sudo apt-get install -y powershell` | `sudo apt-get install -y powershell-preview` |
| <span data-ttu-id="84b3b-301">CentOS, RedHat</span><span class="sxs-lookup"><span data-stu-id="84b3b-301">CentOS, RedHat</span></span>  | `sudo yum install -y powershell`     | `sudo yum install -y powershell-preview`     |
| <span data-ttu-id="84b3b-302">Fedora</span><span class="sxs-lookup"><span data-stu-id="84b3b-302">Fedora</span></span>          | `sudo dnf install -y powershell`     | `sudo dnf install -y powershell-preview`     |

## <a name="install-as-a-net-global-tool"></a><span data-ttu-id="84b3b-303">Installieren als globales .NET-Tool</span><span class="sxs-lookup"><span data-stu-id="84b3b-303">Install as a .NET Global tool</span></span>

<span data-ttu-id="84b3b-304">Wenn Sie das [.NET Core SDK](/dotnet/core/sdk) bereits installiert haben, können Sie PowerShell einfach als [globales .NET-Tool](/dotnet/core/tools/global-tools) installieren.</span><span class="sxs-lookup"><span data-stu-id="84b3b-304">If you already have the [.NET Core SDK](/dotnet/core/sdk) installed, it's easy to install PowerShell as a [.NET Global tool](/dotnet/core/tools/global-tools).</span></span>

```
dotnet tool install --global PowerShell
```

<span data-ttu-id="84b3b-305">Der .NET-Toolinstaller fügt `~/.dotnet/tools` Ihrer `PATH`-Umgebungsvariablen hinzu.</span><span class="sxs-lookup"><span data-stu-id="84b3b-305">The dotnet tool installer adds `~/.dotnet/tools` to your `PATH` environment variable.</span></span> <span data-ttu-id="84b3b-306">Die aktuell ausgeführte Shell verfügt jedoch nicht über den aktualisierten `PATH`.</span><span class="sxs-lookup"><span data-stu-id="84b3b-306">However, the currently running shell does not have the updated `PATH`.</span></span> <span data-ttu-id="84b3b-307">Sie sollten PowerShell über eine neue Shell starten können, indem Sie `pwsh` eingeben.</span><span class="sxs-lookup"><span data-stu-id="84b3b-307">You should be able to start PowerShell from a new shell by typing `pwsh`.</span></span>

## <a name="binary-archives"></a><span data-ttu-id="84b3b-308">Archive der Binärdateien</span><span class="sxs-lookup"><span data-stu-id="84b3b-308">Binary Archives</span></span>

<span data-ttu-id="84b3b-309">`tar.gz`-Archive der PowerShell-Binärdateien werden für Linux-Plattformen zur Verfügung gestellt, um erweiterte Bereitstellungsszenarios zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="84b3b-309">PowerShell binary `tar.gz` archives are provided for Linux platforms to enable advanced deployment scenarios.</span></span>

> [!NOTE]
> <span data-ttu-id="84b3b-310">Sie können diese Methode verwenden, um eine beliebige Version von PowerShell zu installieren, einschließlich der neuesten:</span><span class="sxs-lookup"><span data-stu-id="84b3b-310">You can use this method to install any version of PowerShell including the latest:</span></span>
> - <span data-ttu-id="84b3b-311">Stabiles Release: [https://aka.ms/powershell-release?tag=stable](https://aka.ms/powershell-release?tag=stable)</span><span class="sxs-lookup"><span data-stu-id="84b3b-311">Stable release: [https://aka.ms/powershell-release?tag=stable](https://aka.ms/powershell-release?tag=stable)</span></span>
> - <span data-ttu-id="84b3b-312">Vorschaurelease: [https://aka.ms/powershell-release?tag=preview](https://aka.ms/powershell-release?tag=preview)</span><span class="sxs-lookup"><span data-stu-id="84b3b-312">Preview release: [https://aka.ms/powershell-release?tag=preview](https://aka.ms/powershell-release?tag=preview)</span></span>
> - <span data-ttu-id="84b3b-313">LTS-Release: [https://aka.ms/powershell-release?tag=lts](https://aka.ms/powershell-release?tag=lts)</span><span class="sxs-lookup"><span data-stu-id="84b3b-313">LTS release: [https://aka.ms/powershell-release?tag=lts](https://aka.ms/powershell-release?tag=lts)</span></span>

### <a name="dependencies"></a><span data-ttu-id="84b3b-314">Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="84b3b-314">Dependencies</span></span>

<span data-ttu-id="84b3b-315">PowerShell erstellt portierbare Binärdateien für alle Linux-Distributionen.</span><span class="sxs-lookup"><span data-stu-id="84b3b-315">PowerShell builds portable binaries for all Linux distributions.</span></span> <span data-ttu-id="84b3b-316">Allerdings erfordern die .NET Core-Runtime und PowerShell verschiedene Abhängigkeiten für die verschiedenen Distributionen.</span><span class="sxs-lookup"><span data-stu-id="84b3b-316">But, .NET Core runtime requires different dependencies on different distributions, and PowerShell does too.</span></span>

<span data-ttu-id="84b3b-317">Im folgenden Diagramm werden die Abhängigkeiten von .NET Core 2.0 für die verschiedenen Linux-Distributionen dargestellt, die offiziell unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="84b3b-317">The following chart shows the .NET Core 2.0 dependencies that are officially supported on different Linux distributions.</span></span>

| <span data-ttu-id="84b3b-318">OS</span><span class="sxs-lookup"><span data-stu-id="84b3b-318">OS</span></span>                 | <span data-ttu-id="84b3b-319">Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="84b3b-319">Dependencies</span></span> |
| ------------------ | ------------ |
| <span data-ttu-id="84b3b-320">Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="84b3b-320">Ubuntu 16.04</span></span>       | <span data-ttu-id="84b3b-321">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span><span class="sxs-lookup"><span data-stu-id="84b3b-321">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="84b3b-322">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu55</span><span class="sxs-lookup"><span data-stu-id="84b3b-322">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu55</span></span> |
| <span data-ttu-id="84b3b-323">Ubuntu 17.10</span><span class="sxs-lookup"><span data-stu-id="84b3b-323">Ubuntu 17.10</span></span>       | <span data-ttu-id="84b3b-324">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span><span class="sxs-lookup"><span data-stu-id="84b3b-324">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="84b3b-325">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu57</span><span class="sxs-lookup"><span data-stu-id="84b3b-325">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu57</span></span> |
| <span data-ttu-id="84b3b-326">Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="84b3b-326">Ubuntu 18.04</span></span>       | <span data-ttu-id="84b3b-327">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span><span class="sxs-lookup"><span data-stu-id="84b3b-327">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="84b3b-328">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu60</span><span class="sxs-lookup"><span data-stu-id="84b3b-328">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu60</span></span> |
| <span data-ttu-id="84b3b-329">Debian 8 (Jessie)</span><span class="sxs-lookup"><span data-stu-id="84b3b-329">Debian 8 (Jessie)</span></span>  | <span data-ttu-id="84b3b-330">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span><span class="sxs-lookup"><span data-stu-id="84b3b-330">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="84b3b-331">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu52</span><span class="sxs-lookup"><span data-stu-id="84b3b-331">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu52</span></span> |
| <span data-ttu-id="84b3b-332">Debian 9 (Stretch)</span><span class="sxs-lookup"><span data-stu-id="84b3b-332">Debian 9 (Stretch)</span></span> | <span data-ttu-id="84b3b-333">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span><span class="sxs-lookup"><span data-stu-id="84b3b-333">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="84b3b-334">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.2, libicu57</span><span class="sxs-lookup"><span data-stu-id="84b3b-334">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.2, libicu57</span></span> |
| <span data-ttu-id="84b3b-335">CentOS 7:</span><span class="sxs-lookup"><span data-stu-id="84b3b-335">CentOS 7</span></span> <br> <span data-ttu-id="84b3b-336">Oracle Linux 7</span><span class="sxs-lookup"><span data-stu-id="84b3b-336">Oracle Linux 7</span></span> <br> <span data-ttu-id="84b3b-337">RHEL 7</span><span class="sxs-lookup"><span data-stu-id="84b3b-337">RHEL 7</span></span> | <span data-ttu-id="84b3b-338">libunwind, libcurl, openssl-libs, libicu</span><span class="sxs-lookup"><span data-stu-id="84b3b-338">libunwind, libcurl, openssl-libs, libicu</span></span> |
| <span data-ttu-id="84b3b-339">openSUSE 42.3</span><span class="sxs-lookup"><span data-stu-id="84b3b-339">openSUSE 42.3</span></span> | <span data-ttu-id="84b3b-340">libcurl4, libopenssl1_0_0, libicu52_1</span><span class="sxs-lookup"><span data-stu-id="84b3b-340">libcurl4, libopenssl1_0_0, libicu52_1</span></span> |
| <span data-ttu-id="84b3b-341">openSUSE Leap 15</span><span class="sxs-lookup"><span data-stu-id="84b3b-341">openSUSE Leap 15</span></span> | <span data-ttu-id="84b3b-342">libcurl4, libopenssl1_0_0, libicu60_2</span><span class="sxs-lookup"><span data-stu-id="84b3b-342">libcurl4, libopenssl1_0_0, libicu60_2</span></span> |
| <span data-ttu-id="84b3b-343">Fedora 27</span><span class="sxs-lookup"><span data-stu-id="84b3b-343">Fedora 27</span></span> <br> <span data-ttu-id="84b3b-344">Fedora 28</span><span class="sxs-lookup"><span data-stu-id="84b3b-344">Fedora 28</span></span> | <span data-ttu-id="84b3b-345">libunwind, libcurl, openssl-libs, libicu, compat-openssl10</span><span class="sxs-lookup"><span data-stu-id="84b3b-345">libunwind, libcurl, openssl-libs, libicu, compat-openssl10</span></span> |

<span data-ttu-id="84b3b-346">Sie müssen zur Bereitstellung von PowerShell-Binärdateien für nicht offiziell unterstützte Linux-Distributionen die notwendigen Abhängigkeiten für das Zielbetriebssystem über zusätzliche Schritte installieren.</span><span class="sxs-lookup"><span data-stu-id="84b3b-346">To deploy PowerShell binaries on Linux distributions that aren't officially supported, you need to install the necessary dependencies for the target OS in separate steps.</span></span> <span data-ttu-id="84b3b-347">Beispielsweise installiert die [Amazon Linux-Dockerfile][amazon-dockerfile] zuerst die Abhängigkeiten und extrahiert anschließend das `tar.gz`-Archiv für Linux.</span><span class="sxs-lookup"><span data-stu-id="84b3b-347">For example, our [Amazon Linux dockerfile][amazon-dockerfile] installs dependencies first, and then extracts the Linux `tar.gz` archive.</span></span>

[amazon-dockerfile]: https://github.com/PowerShell/PowerShell-Docker/blob/master/release/community-stable/amazonlinux/docker/Dockerfile

### <a name="installation---binary-archives"></a><span data-ttu-id="84b3b-348">Installation: Archive von Binärdateien</span><span class="sxs-lookup"><span data-stu-id="84b3b-348">Installation - Binary Archives</span></span>

<span data-ttu-id="84b3b-349">Das folgende Beispiel zeigt die Schritte zur Installation des Archivs der x64-Binärdateien.</span><span class="sxs-lookup"><span data-stu-id="84b3b-349">The following example shows the steps for installing the x64 binary archive.</span></span> <span data-ttu-id="84b3b-350">Sie müssen das richtige Binärdateienarchiv auswählen, das dem Prozessortyp Ihrer Plattform entspricht.</span><span class="sxs-lookup"><span data-stu-id="84b3b-350">You must choose the correct binary archive that matches the processor type for your platform.</span></span>

- <span data-ttu-id="84b3b-351">powershell-7.1.3-linux-arm32.tar.gz</span><span class="sxs-lookup"><span data-stu-id="84b3b-351">powershell-7.1.3-linux-arm32.tar.gz</span></span>
- <span data-ttu-id="84b3b-352">powershell-7.1.3-linux-arm64.tar.gz</span><span class="sxs-lookup"><span data-stu-id="84b3b-352">powershell-7.1.3-linux-arm64.tar.gz</span></span>
- <span data-ttu-id="84b3b-353">powershell-7.1.3-linux-x64.tar.gz</span><span class="sxs-lookup"><span data-stu-id="84b3b-353">powershell-7.1.3-linux-x64.tar.gz</span></span>

#### <a name="linux"></a><span data-ttu-id="84b3b-354">Linux</span><span class="sxs-lookup"><span data-stu-id="84b3b-354">Linux</span></span>

```sh
# Download the powershell '.tar.gz' archive
curl -L -o /tmp/powershell.tar.gz https://github.com/PowerShell/PowerShell/releases/download/v7.1.3/powershell-7.1.3-linux-x64.tar.gz

# Create the target folder where powershell will be placed
sudo mkdir -p /opt/microsoft/powershell/7

# Expand powershell to the target folder
sudo tar zxf /tmp/powershell.tar.gz -C /opt/microsoft/powershell/7

# Set execute permissions
sudo chmod +x /opt/microsoft/powershell/7/pwsh

# Create the symbolic link that points to pwsh
sudo ln -s /opt/microsoft/powershell/7/pwsh /usr/bin/pwsh
```

### <a name="uninstalling-binary-archives"></a><span data-ttu-id="84b3b-355">Deinstallation: Archive von Binärdateien</span><span class="sxs-lookup"><span data-stu-id="84b3b-355">Uninstalling binary archives</span></span>

```sh
sudo rm -rf /usr/bin/pwsh /opt/microsoft/powershell
```

## <a name="paths"></a><span data-ttu-id="84b3b-356">Paths</span><span class="sxs-lookup"><span data-stu-id="84b3b-356">Paths</span></span>

- <span data-ttu-id="84b3b-357">`$PSHOME` ist `/opt/microsoft/powershell/7/`.</span><span class="sxs-lookup"><span data-stu-id="84b3b-357">`$PSHOME` is `/opt/microsoft/powershell/7/`</span></span>
- <span data-ttu-id="84b3b-358">Benutzerprofile werden aus `~/.config/powershell/profile.ps1` gelesen.</span><span class="sxs-lookup"><span data-stu-id="84b3b-358">User profiles are read from `~/.config/powershell/profile.ps1`</span></span>
- <span data-ttu-id="84b3b-359">Standardprofile werden aus `$PSHOME/profile.ps1` gelesen.</span><span class="sxs-lookup"><span data-stu-id="84b3b-359">Default profiles are read from `$PSHOME/profile.ps1`</span></span>
- <span data-ttu-id="84b3b-360">Benutzermodule werden aus `~/.local/share/powershell/Modules` gelesen.</span><span class="sxs-lookup"><span data-stu-id="84b3b-360">User modules are read from `~/.local/share/powershell/Modules`</span></span>
- <span data-ttu-id="84b3b-361">Freigegebene Module werden aus `/usr/local/share/powershell/Modules` gelesen.</span><span class="sxs-lookup"><span data-stu-id="84b3b-361">Shared modules are read from `/usr/local/share/powershell/Modules`</span></span>
- <span data-ttu-id="84b3b-362">Standardmodule werden aus `$PSHOME/Modules` gelesen.</span><span class="sxs-lookup"><span data-stu-id="84b3b-362">Default modules are read from `$PSHOME/Modules`</span></span>
- <span data-ttu-id="84b3b-363">Der PSReadLine-Verlauf wird in `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt` protokolliert.</span><span class="sxs-lookup"><span data-stu-id="84b3b-363">PSReadLine history is recorded to `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt`</span></span>

<span data-ttu-id="84b3b-364">Die Profile beachten die Konfigurationen von PowerShell pro Host. Das bedeutet, die hostspezifischen Standardprofile sind an denselben Orten unter `Microsoft.PowerShell_profile.ps1` gespeichert.</span><span class="sxs-lookup"><span data-stu-id="84b3b-364">The profiles respect PowerShell's per-host configuration, so the default host-specific profiles exists at `Microsoft.PowerShell_profile.ps1` in the same locations.</span></span>

<span data-ttu-id="84b3b-365">PowerShell hält die [XDG Base Directory Specification (XDG Base Directory-Spezifikation)][xdg-bds] unter Linux ein.</span><span class="sxs-lookup"><span data-stu-id="84b3b-365">PowerShell respects the [XDG Base Directory Specification][xdg-bds] on Linux.</span></span>

## <a name="installation-support"></a><span data-ttu-id="84b3b-366">Installationsunterstützung</span><span class="sxs-lookup"><span data-stu-id="84b3b-366">Installation support</span></span>

<span data-ttu-id="84b3b-367">Microsoft unterstützt die in diesem Dokument beschriebenen Installationsmethoden.</span><span class="sxs-lookup"><span data-stu-id="84b3b-367">Microsoft supports the installation methods in this document.</span></span> <span data-ttu-id="84b3b-368">Möglicherweise stehen andere Installationsmethoden aus anderen Quellen zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="84b3b-368">There may be other methods of installation available from other sources.</span></span> <span data-ttu-id="84b3b-369">Auch wenn diese Tools und Methoden funktionieren, kann Microsoft sie nicht unterstützen.</span><span class="sxs-lookup"><span data-stu-id="84b3b-369">While those tools and methods may work, Microsoft cannot support those methods.</span></span>

<!-- link references -->
[Freigaben]: https://aka.ms/PowerShell-Release?tag=stable
[releases]: https://aka.ms/PowerShell-Release?tag=stable
[xdg-bds]: https://specifications.freedesktop.org/basedir-spec/basedir-spec-latest.html
[distros]: https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md#linux
[Distribution Support Request]: https://github.com/PowerShell/PowerShell/issues/new?assignees=&labels=Distribution-Request&template=Distribution_Request.md&title=Distribution+Support+Request
