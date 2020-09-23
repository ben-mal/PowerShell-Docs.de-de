---
title: Installieren von PowerShell unter Linux
description: Informationen zur Installation von PowerShell auf verschiedenen Linux-Distributionen
ms.date: 07/30/2020
ms.openlocfilehash: ce69f75416eb326e38d42991a4ae85a3a7298c5d
ms.sourcegitcommit: 79d430fe48ad77a058f42b6bc9955d21b657987e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2020
ms.locfileid: "87441762"
---
# <a name="installing-powershell-on-linux"></a><span data-ttu-id="7d474-103">Installieren von PowerShell unter Linux</span><span class="sxs-lookup"><span data-stu-id="7d474-103">Installing PowerShell on Linux</span></span>

<span data-ttu-id="7d474-104">Sämtliche Pakete sind auf der Seite [Freigaben][] über GitHub verfügbar.</span><span class="sxs-lookup"><span data-stu-id="7d474-104">All packages are available on our GitHub [releases][] page.</span></span> <span data-ttu-id="7d474-105">Nachdem Sie das Paket installiert haben, führen Sie `pwsh` über das Terminal aus.</span><span class="sxs-lookup"><span data-stu-id="7d474-105">After the package is installed, run `pwsh` from a terminal.</span></span> <span data-ttu-id="7d474-106">Führen Sie `pwsh-preview` aus, wenn Sie eine [Vorschauversion](#installing-preview-releases) installiert haben.</span><span class="sxs-lookup"><span data-stu-id="7d474-106">Run `pwsh-preview` if you installed a [Preview release](#installing-preview-releases).</span></span>

> [!NOTE]
> <span data-ttu-id="7d474-107">PowerShell 7 ist ein direktes Upgrade, mit dem PowerShell Core 6.x entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="7d474-107">PowerShell 7 is an in-place upgrade that removes PowerShell Core 6.x.</span></span>
>
> <span data-ttu-id="7d474-108">Der Ordner `/usr/local/microsoft/powershell/6` wird durch `/usr/local/microsoft/powershell/7` ersetzt.</span><span class="sxs-lookup"><span data-stu-id="7d474-108">The `/usr/local/microsoft/powershell/6` folder is replaced by `/usr/local/microsoft/powershell/7`.</span></span>
>
> <span data-ttu-id="7d474-109">Wenn Sie PowerShell 6 und PowerShell 7 parallel ausführen müssen, installieren Sie PowerShell 6 mithilfe der [binary archive](#binary-archives)-Methode neu.</span><span class="sxs-lookup"><span data-stu-id="7d474-109">If you need to run PowerShell 6 side-by-side with PowerShell 7, reinstall PowerShell 6 using the [binary archive](#binary-archives) method.</span></span>

<span data-ttu-id="7d474-110">Für nicht offiziell unterstützte Linux-Distributionen können Sie versuchen, PowerShell über das [Snap-Paket für PowerShell][snap] zu installieren.</span><span class="sxs-lookup"><span data-stu-id="7d474-110">For Linux distributions that aren't officially supported, you can try to install PowerShell using the [PowerShell Snap Package][snap].</span></span> <span data-ttu-id="7d474-111">Stattdessen können Sie auch versuchen, PowerShell-Binärdateien über das [`tar.gz`-Archiv][tar] für Linux bereitzustellen. Dafür müssen Sie aber die für Ihr Betriebssystem erforderlichen Abhängigkeiten in zusätzlichen Schritten einrichten.</span><span class="sxs-lookup"><span data-stu-id="7d474-111">You can also try deploying PowerShell binaries directly using the Linux [`tar.gz` archive][tar], but you would need to set up the necessary dependencies based on the OS in separate steps.</span></span>

[snap]: #snap-package
[tar]: #binary-archives

<span data-ttu-id="7d474-112">Offiziell unterstützte Releases:</span><span class="sxs-lookup"><span data-stu-id="7d474-112">Officially supported releases</span></span>

- <span data-ttu-id="7d474-113">Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="7d474-113">Ubuntu 16.04</span></span>
- <span data-ttu-id="7d474-114">Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="7d474-114">Ubuntu 18.04</span></span>
- <span data-ttu-id="7d474-115">Debian 8</span><span class="sxs-lookup"><span data-stu-id="7d474-115">Debian 8</span></span>
- <span data-ttu-id="7d474-116">Debian 9</span><span class="sxs-lookup"><span data-stu-id="7d474-116">Debian 9</span></span>
- <span data-ttu-id="7d474-117">Debian 10</span><span class="sxs-lookup"><span data-stu-id="7d474-117">Debian 10</span></span>
- <span data-ttu-id="7d474-118">Alpine 3.9 und 3.10</span><span class="sxs-lookup"><span data-stu-id="7d474-118">Alpine 3.9 and 3.10</span></span>
- <span data-ttu-id="7d474-119">CentOS 7:</span><span class="sxs-lookup"><span data-stu-id="7d474-119">CentOS 7</span></span>
- <span data-ttu-id="7d474-120">Red Hat Enterprise Linux 7 (RHEL)</span><span class="sxs-lookup"><span data-stu-id="7d474-120">Red Hat Enterprise Linux (RHEL) 7</span></span>
- <span data-ttu-id="7d474-121">Fedora 28</span><span class="sxs-lookup"><span data-stu-id="7d474-121">Fedora 28</span></span>
- <span data-ttu-id="7d474-122">Fedora 29</span><span class="sxs-lookup"><span data-stu-id="7d474-122">Fedora 29</span></span>
- <span data-ttu-id="7d474-123">Fedora 30</span><span class="sxs-lookup"><span data-stu-id="7d474-123">Fedora 30</span></span>
- <span data-ttu-id="7d474-124">openSUSE 42.3</span><span class="sxs-lookup"><span data-stu-id="7d474-124">openSUSE 42.3</span></span>
- <span data-ttu-id="7d474-125">openSUSE Leap 15</span><span class="sxs-lookup"><span data-stu-id="7d474-125">openSUSE Leap 15</span></span>

<span data-ttu-id="7d474-126">Von der Community unterstützte Releases:</span><span class="sxs-lookup"><span data-stu-id="7d474-126">Community supported releases</span></span>

- <span data-ttu-id="7d474-127">Ubuntu 18.10</span><span class="sxs-lookup"><span data-stu-id="7d474-127">Ubuntu 18.10</span></span>
- <span data-ttu-id="7d474-128">Ubuntu 19.04</span><span class="sxs-lookup"><span data-stu-id="7d474-128">Ubuntu 19.04</span></span>
- <span data-ttu-id="7d474-129">Arch Linux</span><span class="sxs-lookup"><span data-stu-id="7d474-129">Arch Linux</span></span>
- <span data-ttu-id="7d474-130">Kali</span><span class="sxs-lookup"><span data-stu-id="7d474-130">Kali</span></span>
- <span data-ttu-id="7d474-131">Raspbian (experimentell)</span><span class="sxs-lookup"><span data-stu-id="7d474-131">Raspbian (experimental)</span></span>

<span data-ttu-id="7d474-132">Alternative Installationsmethoden</span><span class="sxs-lookup"><span data-stu-id="7d474-132">Alternate install methods</span></span>

- <span data-ttu-id="7d474-133">Snap-Paket</span><span class="sxs-lookup"><span data-stu-id="7d474-133">Snap Package</span></span>
- <span data-ttu-id="7d474-134">Archive der Binärdateien</span><span class="sxs-lookup"><span data-stu-id="7d474-134">Binary Archives</span></span>
- <span data-ttu-id="7d474-135">Globales .NET-Tool</span><span class="sxs-lookup"><span data-stu-id="7d474-135">.NET Global tool</span></span>

<span data-ttu-id="7d474-136">Derzeit nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="7d474-136">Not currently supported</span></span>

- <span data-ttu-id="7d474-137">Ubuntu 20.04</span><span class="sxs-lookup"><span data-stu-id="7d474-137">Ubuntu 20.04</span></span>

> [!NOTE]
> <span data-ttu-id="7d474-138">PowerShell unterstützt nur die von .NET unterstützten Verteilungen.</span><span class="sxs-lookup"><span data-stu-id="7d474-138">PowerShell can only support the distributions that are supported by .NET.</span></span> <span data-ttu-id="7d474-139">Eine Liste der unterstützten Verteilungen finden Sie in den [Versionshinweisen zu .NET Core][distros].</span><span class="sxs-lookup"><span data-stu-id="7d474-139">See the [.NET Core release notes][distros] for a list of supported distributions.</span></span> <span data-ttu-id="7d474-140">Wird eine von .NET unterstützte Distribution hier nicht aufgeführt, können Sie anfordern, dass für diese Verteilung Unterstützung hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="7d474-140">If there is a distrbution supported by .NET that is not listed here, you can request that support for the distribution be added.</span></span> <span data-ttu-id="7d474-141">Verwenden Sie hierzu die Vorlage für die [Anforderung von Verteilungsunterstützung][].</span><span class="sxs-lookup"><span data-stu-id="7d474-141">Please file a request using the [Distribution Support Request][] template.</span></span>

## <a name="ubuntu-1604"></a><span data-ttu-id="7d474-142">Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="7d474-142">Ubuntu 16.04</span></span>

### <a name="installation-via-package-repository---ubuntu-1604"></a><span data-ttu-id="7d474-143">Installation über das Paketrepository: Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="7d474-143">Installation via Package Repository - Ubuntu 16.04</span></span>

<span data-ttu-id="7d474-144">PowerShell für Linux wird in Paketrepositorys veröffentlicht, um die Installation und die Updates zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="7d474-144">PowerShell for Linux is published to package repositories for easy installation and updates.</span></span>

<span data-ttu-id="7d474-145">Folgende Methode wird bevorzugt:</span><span class="sxs-lookup"><span data-stu-id="7d474-145">The preferred method is as follows:</span></span>

```sh
# Download the Microsoft repository GPG keys
wget -q https://packages.microsoft.com/config/ubuntu/16.04/packages-microsoft-prod.deb

# Register the Microsoft repository GPG keys
sudo dpkg -i packages-microsoft-prod.deb

# Update the list of products
sudo apt-get update

# Install PowerShell
sudo apt-get install -y powershell

# Start PowerShell
pwsh
```

<span data-ttu-id="7d474-146">Registrieren Sie das Microsoft-Repository einmal als Superuser.</span><span class="sxs-lookup"><span data-stu-id="7d474-146">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="7d474-147">Nach der Registrierung können Sie PowerShell mit `sudo apt-get install powershell` aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="7d474-147">After registration, you can update PowerShell with `sudo apt-get install powershell`.</span></span>

### <a name="installation-via-direct-download---ubuntu-1604"></a><span data-ttu-id="7d474-148">Installation über einen direkten Download: Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="7d474-148">Installation via Direct Download - Ubuntu 16.04</span></span>

<span data-ttu-id="7d474-149">Laden Sie das Debian-Paket `powershell-lts_7.0.3-1.ubuntu.16.04_amd64.deb` über die Seite [Freigaben][] auf den Ubuntu-Computer herunter.</span><span class="sxs-lookup"><span data-stu-id="7d474-149">Download the Debian package `powershell-lts_7.0.3-1.ubuntu.16.04_amd64.deb` from the [releases][] page onto the Ubuntu machine.</span></span>

<span data-ttu-id="7d474-150">Führen Sie dann im Terminal folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="7d474-150">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo dpkg -i powershell-lts_7.0.3-1.ubuntu.16.04_amd64.deb
sudo apt-get install -f
```

> [!NOTE]
> <span data-ttu-id="7d474-151">Der `dpkg -i`-Befehl schlägt mit nicht erfüllten Abhängigkeiten fehl.</span><span class="sxs-lookup"><span data-stu-id="7d474-151">The `dpkg -i` command fails with unmet dependencies.</span></span> <span data-ttu-id="7d474-152">Über den Befehl `apt-get install -f` werden diese Probleme behoben und die Konfiguration des PowerShell-Pakets abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="7d474-152">The next command, `apt-get install -f` resolves these issues then finishes configuring the PowerShell package.</span></span>

### <a name="uninstallation---ubuntu-1604"></a><span data-ttu-id="7d474-153">Deinstallation: Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="7d474-153">Uninstallation - Ubuntu 16.04</span></span>

```sh
sudo apt-get remove powershell
```

## <a name="ubuntu-1804"></a><span data-ttu-id="7d474-154">Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="7d474-154">Ubuntu 18.04</span></span>

### <a name="installation-via-package-repository---ubuntu-1804"></a><span data-ttu-id="7d474-155">Installation über das Paketrepository: Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="7d474-155">Installation via Package Repository - Ubuntu 18.04</span></span>

<span data-ttu-id="7d474-156">PowerShell für Linux wird in Paketrepositorys veröffentlicht, um die Installation und die Updates zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="7d474-156">PowerShell for Linux is published to package repositories for easy installation and updates.</span></span>

<span data-ttu-id="7d474-157">Folgende Methode wird bevorzugt:</span><span class="sxs-lookup"><span data-stu-id="7d474-157">The preferred method is as follows:</span></span>

```sh
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

<span data-ttu-id="7d474-158">Registrieren Sie das Microsoft-Repository einmal als Superuser.</span><span class="sxs-lookup"><span data-stu-id="7d474-158">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="7d474-159">Nach der Registrierung können Sie PowerShell mit `sudo apt-get install powershell` aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="7d474-159">After registration, you can update PowerShell with `sudo apt-get install powershell`.</span></span>

### <a name="installation-via-direct-download---ubuntu-1804"></a><span data-ttu-id="7d474-160">Installation über einen direkten Download: Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="7d474-160">Installation via Direct Download - Ubuntu 18.04</span></span>

<span data-ttu-id="7d474-161">Laden Sie das Debian-Paket `powershell-lts_7.0.3-1.ubuntu.18.04_amd64.deb` über die Seite [Freigaben][] auf den Ubuntu-Computer herunter.</span><span class="sxs-lookup"><span data-stu-id="7d474-161">Download the Debian package `powershell-lts_7.0.3-1.ubuntu.18.04_amd64.deb` from the [releases][] page onto the Ubuntu machine.</span></span>

<span data-ttu-id="7d474-162">Führen Sie dann im Terminal folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="7d474-162">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo dpkg -i powershell-lts_7.0.3-1.ubuntu.18.04_amd64.deb
sudo apt-get install -f
```

> [!NOTE]
> <span data-ttu-id="7d474-163">Der `dpkg -i`-Befehl schlägt mit nicht erfüllten Abhängigkeiten fehl.</span><span class="sxs-lookup"><span data-stu-id="7d474-163">The `dpkg -i` command fails with unmet dependencies.</span></span> <span data-ttu-id="7d474-164">Über den Befehl `apt-get install -f` werden diese Probleme behoben und die Konfiguration des PowerShell-Pakets abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="7d474-164">The next command, `apt-get install -f` resolves these issues then finishes configuring the PowerShell package.</span></span>

### <a name="uninstallation---ubuntu-1804"></a><span data-ttu-id="7d474-165">Deinstallation: Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="7d474-165">Uninstallation - Ubuntu 18.04</span></span>

```sh
sudo apt-get remove powershell
```

## <a name="ubuntu-1810"></a><span data-ttu-id="7d474-166">Ubuntu 18.10</span><span class="sxs-lookup"><span data-stu-id="7d474-166">Ubuntu 18.10</span></span>

<span data-ttu-id="7d474-167">Die Installation wird über `snapd` unterstützt.</span><span class="sxs-lookup"><span data-stu-id="7d474-167">Installation is supported via `snapd`.</span></span> <span data-ttu-id="7d474-168">Anweisungen finden Sie unter [Snap-Paket][snap].</span><span class="sxs-lookup"><span data-stu-id="7d474-168">For instructions, see [Snap Package][snap].</span></span>

> [!NOTE]
> <span data-ttu-id="7d474-169">Ubuntu 18.10 ist ein [Zwischenrelease](https://www.ubuntu.com/about/release-cycle), das von der [Community unterstützt](../powershell-support-lifecycle.md) wird.</span><span class="sxs-lookup"><span data-stu-id="7d474-169">Ubuntu 18.10 is an [interim release](https://www.ubuntu.com/about/release-cycle) that's [community supported](../powershell-support-lifecycle.md).</span></span>

## <a name="ubuntu-1904"></a><span data-ttu-id="7d474-170">Ubuntu 19.04</span><span class="sxs-lookup"><span data-stu-id="7d474-170">Ubuntu 19.04</span></span>

<span data-ttu-id="7d474-171">Die Installation wird über `snapd` unterstützt.</span><span class="sxs-lookup"><span data-stu-id="7d474-171">Installation is supported via `snapd`.</span></span> <span data-ttu-id="7d474-172">Anweisungen finden Sie unter [Snap-Paket][snap].</span><span class="sxs-lookup"><span data-stu-id="7d474-172">For instructions, see [Snap Package][snap].</span></span>

> [!NOTE]
> <span data-ttu-id="7d474-173">Ubuntu 19.04 ist ein [Zwischenrelease](https://www.ubuntu.com/about/release-cycle), das von der [Community unterstützt](../powershell-support-lifecycle.md) wird.</span><span class="sxs-lookup"><span data-stu-id="7d474-173">Ubuntu 19.04 is an [interim release](https://www.ubuntu.com/about/release-cycle) that's [community supported](../powershell-support-lifecycle.md).</span></span>

## <a name="ubuntu-2004"></a><span data-ttu-id="7d474-174">Ubuntu 20.04</span><span class="sxs-lookup"><span data-stu-id="7d474-174">Ubuntu 20.04</span></span>

<span data-ttu-id="7d474-175">PowerShell 20.04 ist ein LTS-Release.</span><span class="sxs-lookup"><span data-stu-id="7d474-175">Ubuntu 20.04 is an LTS release.</span></span> <span data-ttu-id="7d474-176">Diese Version wird von PowerShell derzeit nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="7d474-176">PowerShell does not currently support this version.</span></span> <span data-ttu-id="7d474-177">Die Unterstützung für diese Version wird für die PowerShell-Version 7.1 in Erwägung gezogen.</span><span class="sxs-lookup"><span data-stu-id="7d474-177">Support for this version is being considered for the PowerShell 7.1 release.</span></span> <span data-ttu-id="7d474-178">Bitte stimmen Sie für diese [Anforderung](https://github.com/PowerShell/PowerShell/issues/12626) zu, wenn Sie Unterstützung für Ubuntu 20.04 wünschen.</span><span class="sxs-lookup"><span data-stu-id="7d474-178">Please upvote this [request](https://github.com/PowerShell/PowerShell/issues/12626) if you would like support for Ubuntu 20.04.</span></span>

## <a name="debian-8"></a><span data-ttu-id="7d474-179">Debian 8</span><span class="sxs-lookup"><span data-stu-id="7d474-179">Debian 8</span></span>

### <a name="installation-via-package-repository---debian-8"></a><span data-ttu-id="7d474-180">Installation über das Paketrepository: Debian 8</span><span class="sxs-lookup"><span data-stu-id="7d474-180">Installation via Package Repository - Debian 8</span></span>

<span data-ttu-id="7d474-181">PowerShell für Linux wird in Paketrepositorys veröffentlicht, um die Installation und die Updates zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="7d474-181">PowerShell for Linux is published to package repositories for easy installation and updates.</span></span>

<span data-ttu-id="7d474-182">Folgende Methode wird bevorzugt:</span><span class="sxs-lookup"><span data-stu-id="7d474-182">The preferred method is as follows:</span></span>

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

<span data-ttu-id="7d474-183">Registrieren Sie das Microsoft-Repository einmal als Superuser.</span><span class="sxs-lookup"><span data-stu-id="7d474-183">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="7d474-184">Nach der Registrierung können Sie PowerShell mit `sudo apt-get install powershell` aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="7d474-184">After registration, you can update PowerShell with `sudo apt-get install powershell`.</span></span>

## <a name="debian-9"></a><span data-ttu-id="7d474-185">Debian 9</span><span class="sxs-lookup"><span data-stu-id="7d474-185">Debian 9</span></span>

### <a name="installation-via-package-repository---debian-9"></a><span data-ttu-id="7d474-186">Installation über das Paketrepository: Debian 9</span><span class="sxs-lookup"><span data-stu-id="7d474-186">Installation via Package Repository - Debian 9</span></span>

<span data-ttu-id="7d474-187">PowerShell für Linux wird in Paketrepositorys veröffentlicht, um die Installation und die Updates zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="7d474-187">PowerShell for Linux is published to package repositories for easy installation and updates.</span></span>

<span data-ttu-id="7d474-188">Folgende Methode wird bevorzugt:</span><span class="sxs-lookup"><span data-stu-id="7d474-188">The preferred method is as follows:</span></span>

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

<span data-ttu-id="7d474-189">Registrieren Sie das Microsoft-Repository einmal als Superuser.</span><span class="sxs-lookup"><span data-stu-id="7d474-189">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="7d474-190">Nach der Registrierung können Sie PowerShell mit `sudo apt-get install powershell` aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="7d474-190">After registration, you can update PowerShell with `sudo apt-get install powershell`.</span></span>

### <a name="installation-via-direct-download---debian-9"></a><span data-ttu-id="7d474-191">Installation über einen direkten Download: Debian 9</span><span class="sxs-lookup"><span data-stu-id="7d474-191">Installation via Direct Download - Debian 9</span></span>

<span data-ttu-id="7d474-192">Laden Sie das Debian-Paket `powershell-lts_7.0.3-1.debian.9_amd64.deb` über die Seite [Freigaben][] auf den Debian-Computer herunter.</span><span class="sxs-lookup"><span data-stu-id="7d474-192">Download the Debian package `powershell-lts_7.0.3-1.debian.9_amd64.deb` from the [releases][] page onto the Debian machine.</span></span>

<span data-ttu-id="7d474-193">Führen Sie dann im Terminal folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="7d474-193">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo dpkg -i powershell-lts_7.0.3-1.debian.9_amd64.deb
sudo apt-get install -f
```

### <a name="uninstallation---debian-9"></a><span data-ttu-id="7d474-194">Deinstallation: Debian 9</span><span class="sxs-lookup"><span data-stu-id="7d474-194">Uninstallation - Debian 9</span></span>

```sh
sudo apt-get remove powershell
```

## <a name="debian-10"></a><span data-ttu-id="7d474-195">Debian 10</span><span class="sxs-lookup"><span data-stu-id="7d474-195">Debian 10</span></span>

> [!NOTE]
> <span data-ttu-id="7d474-196">Debian 10 wird nur in PowerShell 7.0 und höher unterstützt.</span><span class="sxs-lookup"><span data-stu-id="7d474-196">Debian 10 is only supported in PowerShell 7.0 and newer.</span></span>

### <a name="installation-via-package-repository---debian-10"></a><span data-ttu-id="7d474-197">Installation über das Paketrepository: Debian 10</span><span class="sxs-lookup"><span data-stu-id="7d474-197">Installation via Package Repository - Debian 10</span></span>

<span data-ttu-id="7d474-198">PowerShell für Linux wird in Paketrepositorys veröffentlicht, um die Installation und die Updates zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="7d474-198">PowerShell for Linux is published to package repositories for easy installation and updates.</span></span>

<span data-ttu-id="7d474-199">Folgende Methode wird bevorzugt:</span><span class="sxs-lookup"><span data-stu-id="7d474-199">The preferred method is as follows:</span></span>

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

### <a name="installation-via-direct-download---debian-10"></a><span data-ttu-id="7d474-200">Installation über direkten Download: Debian 10</span><span class="sxs-lookup"><span data-stu-id="7d474-200">Installation via Direct Download - Debian 10</span></span>

<span data-ttu-id="7d474-201">Laden Sie das tar.gz-Paket `powershell-7.0.3-linux-x64.tar.gz` über die Seite [Freigaben][] auf den Debian-Computer herunter.</span><span class="sxs-lookup"><span data-stu-id="7d474-201">Download the tar.gz package `powershell-7.0.3-linux-x64.tar.gz` from the [releases][] page onto the Debian machine.</span></span>

<span data-ttu-id="7d474-202">Führen Sie dann im Terminal folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="7d474-202">Then, in the terminal, execute the following commands:</span></span>

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
curl -L  https://github.com/PowerShell/PowerShell/releases/download/v7.0.3/powershell-7.0.3-linux-x64.tar.gz -o /tmp/powershell.tar.gz

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

## <a name="alpine-39-and-310"></a><span data-ttu-id="7d474-203">Alpine 3.9 und 3.10</span><span class="sxs-lookup"><span data-stu-id="7d474-203">Alpine 3.9 and 3.10</span></span>

> [!NOTE]
> <span data-ttu-id="7d474-204">Alpine 3.9 und 3.10 werden nur in PowerShell 7.0 und höher unterstützt.</span><span class="sxs-lookup"><span data-stu-id="7d474-204">Alpine 3.9 and 3.10 are only supported in PowerShell 7.0 and newer.</span></span>

### <a name="installation-via-direct-download---alpine-39-and-310"></a><span data-ttu-id="7d474-205">Installation über direkten Download: Alpine 3.9 und 3.10</span><span class="sxs-lookup"><span data-stu-id="7d474-205">Installation via Direct Download - Alpine 3.9 and 3.10</span></span>

<span data-ttu-id="7d474-206">Laden Sie das tar.gz-Paket `powershell-7.0.3-linux-alpine-x64.tar.gz` über die Seite [Freigaben][] auf den Alpine-Computer herunter.</span><span class="sxs-lookup"><span data-stu-id="7d474-206">Download the tar.gz package `powershell-7.0.3-linux-alpine-x64.tar.gz` from the [releases][] page onto the Alpine machine.</span></span>

<span data-ttu-id="7d474-207">Führen Sie dann im Terminal folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="7d474-207">Then, in the terminal, execute the following commands:</span></span>

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
curl -L https://github.com/PowerShell/PowerShell/releases/download/v7.0.3/powershell-7.0.3-linux-alpine-x64.tar.gz -o /tmp/powershell.tar.gz

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

## <a name="centos-7"></a><span data-ttu-id="7d474-208">CentOS 7:</span><span class="sxs-lookup"><span data-stu-id="7d474-208">CentOS 7</span></span>

> [!NOTE]
> <span data-ttu-id="7d474-209">Dieses Paket funktioniert unter Oracle Linux 7.</span><span class="sxs-lookup"><span data-stu-id="7d474-209">This package works on Oracle Linux 7.</span></span>

### <a name="installation-via-package-repository-preferred---centos-7"></a><span data-ttu-id="7d474-210">Installation über das Paketrepository (bevorzugt): CentOS 7</span><span class="sxs-lookup"><span data-stu-id="7d474-210">Installation via Package Repository (preferred) - CentOS 7</span></span>

<span data-ttu-id="7d474-211">PowerShell für Linux wird in offiziellen Microsoft-Repositorys veröffentlicht, um die Installation und die Updates zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="7d474-211">PowerShell for Linux is published to official Microsoft repositories for easy installation and updates.</span></span>

```sh
# Register the Microsoft RedHat repository
curl https://packages.microsoft.com/config/rhel/7/prod.repo | sudo tee /etc/yum.repos.d/microsoft.repo

# Install PowerShell
sudo yum install -y powershell

# Start PowerShell
pwsh
```

<span data-ttu-id="7d474-212">Registrieren Sie das Microsoft-Repository einmal als Superuser.</span><span class="sxs-lookup"><span data-stu-id="7d474-212">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="7d474-213">Nach der Registrierung können Sie PowerShell mit `sudo yum update powershell` aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="7d474-213">After registration, you can update PowerShell with `sudo yum update powershell`.</span></span>

### <a name="installation-via-direct-download---centos-7"></a><span data-ttu-id="7d474-214">Installation über einen direkten Download: CentOS 7</span><span class="sxs-lookup"><span data-stu-id="7d474-214">Installation via Direct Download - CentOS 7</span></span>

<span data-ttu-id="7d474-215">Für [CentOS 7][]: Laden Sie das RPM-Paket `powershell-lts-7.0.3-1.rhel.7.x86_64.rpm` über die Seite [Freigaben][] auf den CentOS-Computer herunter.</span><span class="sxs-lookup"><span data-stu-id="7d474-215">Using [CentOS 7][], download the RPM package `powershell-lts-7.0.3-1.rhel.7.x86_64.rpm` from the [releases][] page onto the CentOS machine.</span></span>

<span data-ttu-id="7d474-216">Führen Sie dann im Terminal folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="7d474-216">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo yum install powershell-lts-7.0.3-1.rhel.7.x86_64.rpm
```

<span data-ttu-id="7d474-217">Sie können RPM ohne Download installieren:</span><span class="sxs-lookup"><span data-stu-id="7d474-217">You can install the RPM without the intermediate step of downloading it:</span></span>

```sh
sudo yum install https://github.com/PowerShell/PowerShell/releases/download/v7.0.3/powershell-lts-7.0.3-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---centos-7"></a><span data-ttu-id="7d474-218">Deinstallation: CentOS 7</span><span class="sxs-lookup"><span data-stu-id="7d474-218">Uninstallation - CentOS 7</span></span>

```sh
sudo yum remove powershell
```

[CentOS 7]: https://www.centos.org/download/

## <a name="red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="7d474-220">Red Hat Enterprise Linux 7 (RHEL)</span><span class="sxs-lookup"><span data-stu-id="7d474-220">Red Hat Enterprise Linux (RHEL) 7</span></span>

### <a name="installation-via-package-repository-preferred---red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="7d474-221">Installation über ein Paketrepository (bevorzugt): Red Hat Enterprise Linux 7 (RHEL)</span><span class="sxs-lookup"><span data-stu-id="7d474-221">Installation via Package Repository (preferred) - Red Hat Enterprise Linux (RHEL) 7</span></span>

<span data-ttu-id="7d474-222">PowerShell für Linux wird in offiziellen Microsoft-Repositorys veröffentlicht, um die Installation und die Updates zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="7d474-222">PowerShell for Linux is published to official Microsoft repositories for easy installation and updates.</span></span>

```sh
# Register the Microsoft RedHat repository
curl https://packages.microsoft.com/config/rhel/7/prod.repo | sudo tee /etc/yum.repos.d/microsoft.repo

# Install PowerShell
sudo yum install -y powershell

# Start PowerShell
pwsh
```

<span data-ttu-id="7d474-223">Registrieren Sie das Microsoft-Repository einmal als Superuser.</span><span class="sxs-lookup"><span data-stu-id="7d474-223">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="7d474-224">Nach der Registrierung können Sie PowerShell mit `sudo yum update powershell` aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="7d474-224">After registration, you can update PowerShell with `sudo yum update powershell`.</span></span>

### <a name="installation-via-direct-download---red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="7d474-225">Installation über einen direkten Download: Red Hat Enterprise Linux 7 (RHEL)</span><span class="sxs-lookup"><span data-stu-id="7d474-225">Installation via Direct Download - Red Hat Enterprise Linux (RHEL) 7</span></span>

<span data-ttu-id="7d474-226">Laden Sie das RPM-Paket `powershell-lts-7.0.3-1.rhel.7.x86_64.rpm` über die Seite [Freigaben][] auf den Red Hat Enterprise Linux-Computer herunter.</span><span class="sxs-lookup"><span data-stu-id="7d474-226">Download the RPM package `powershell-lts-7.0.3-1.rhel.7.x86_64.rpm` from the [releases][] page onto the Red Hat Enterprise Linux machine.</span></span>

<span data-ttu-id="7d474-227">Führen Sie dann im Terminal folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="7d474-227">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo yum install powershell-lts-7.0.3-1.rhel.7.x86_64.rpm
```

<span data-ttu-id="7d474-228">Sie können RPM ohne Download installieren:</span><span class="sxs-lookup"><span data-stu-id="7d474-228">You can install the RPM without the intermediate step of downloading it:</span></span>

```sh
sudo yum install https://github.com/PowerShell/PowerShell/releases/download/v7.0.3/powershell-lts-7.0.3-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="7d474-229">Deinstallation: Red Hat Enterprise Linux 7 (RHEL)</span><span class="sxs-lookup"><span data-stu-id="7d474-229">Uninstallation - Red Hat Enterprise Linux (RHEL) 7</span></span>

```sh
sudo yum remove powershell
```

## <a name="opensuse"></a><span data-ttu-id="7d474-230">openSUSE</span><span class="sxs-lookup"><span data-stu-id="7d474-230">openSUSE</span></span>

### <a name="installation---opensuse-423"></a><span data-ttu-id="7d474-231">Installation: openSUSE 42.3</span><span class="sxs-lookup"><span data-stu-id="7d474-231">Installation - openSUSE 42.3</span></span>

```sh
# Install dependencies
zypper update && zypper --non-interactive install curl tar libicu52_1

# Download the powershell '.tar.gz' archive
curl -L https://github.com/PowerShell/PowerShell/releases/download/v7.0.3/powershell-7.0.3-linux-x64.tar.gz -o /tmp/powershell.tar.gz

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

### <a name="installation---opensuse-leap-15"></a><span data-ttu-id="7d474-232">Installation: openSUSE Leap 15</span><span class="sxs-lookup"><span data-stu-id="7d474-232">Installation - openSUSE Leap 15</span></span>

```sh
# Install dependencies
zypper update && zypper --non-interactive install curl tar gzip libopenssl1_0_0 libicu60_2

# Download the powershell '.tar.gz' archive
curl -L https://github.com/PowerShell/PowerShell/releases/download/v7.0.3/powershell-7.0.3-linux-x64.tar.gz -o /tmp/powershell.tar.gz

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

### <a name="uninstallation---opensuse-423-opensuse-leap-15"></a><span data-ttu-id="7d474-233">Deinstallation: openSUSE 42.3, openSUSE Leap 15</span><span class="sxs-lookup"><span data-stu-id="7d474-233">Uninstallation - openSUSE 42.3, openSUSE Leap 15</span></span>

```sh
rm -rf /usr/bin/pwsh /opt/microsoft/powershell
```

## <a name="fedora"></a><span data-ttu-id="7d474-234">Fedora</span><span class="sxs-lookup"><span data-stu-id="7d474-234">Fedora</span></span>

> [!NOTE]
> <span data-ttu-id="7d474-235">Fedora 28 wird nur in PowerShell 6.1 und höher unterstützt.</span><span class="sxs-lookup"><span data-stu-id="7d474-235">Fedora 28 is only supported in PowerShell 6.1 and newer.</span></span>

> [!NOTE]
> <span data-ttu-id="7d474-236">Fedora 29 und 30 werden nur in PowerShell 7.0 und höher unterstützt.</span><span class="sxs-lookup"><span data-stu-id="7d474-236">Fedora 29 and 30 are only supported in PowerShell 7.0 and newer.</span></span>

### <a name="installation-via-package-repository-preferred---fedora-28-29-and-30"></a><span data-ttu-id="7d474-237">Installation über das Paketrepository (bevorzugt): Fedora 28, 29 und 30</span><span class="sxs-lookup"><span data-stu-id="7d474-237">Installation via Package Repository (preferred) - Fedora 28, 29, and 30</span></span>

<span data-ttu-id="7d474-238">PowerShell für Linux wird in offiziellen Microsoft-Repositorys veröffentlicht, um die Installation und die Updates zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="7d474-238">PowerShell for Linux is published to official Microsoft repositories for easy installation and updates.</span></span>

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

### <a name="installation-via-direct-download---fedora-28-29-and-30"></a><span data-ttu-id="7d474-239">Installation über direkten Download: Fedora 28, 29 und 30</span><span class="sxs-lookup"><span data-stu-id="7d474-239">Installation via Direct Download - Fedora 28, 29, and 30</span></span>

<span data-ttu-id="7d474-240">Laden Sie das RPM-Paket `powershell-7.0.3-1.rhel.7.x86_64.rpm` über die Seite [Freigaben][] auf den Fedora-Computer herunter.</span><span class="sxs-lookup"><span data-stu-id="7d474-240">Download the RPM package `powershell-7.0.3-1.rhel.7.x86_64.rpm` from the [releases][] page onto the Fedora machine.</span></span>

<span data-ttu-id="7d474-241">Führen Sie dann im Terminal folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="7d474-241">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo dnf install compat-openssl10
sudo dnf install powershell-7.0.3-1.rhel.7.x86_64.rpm
```

<span data-ttu-id="7d474-242">Sie können RPM ohne Download installieren:</span><span class="sxs-lookup"><span data-stu-id="7d474-242">You can install the RPM without the intermediate step of downloading it:</span></span>

```sh
sudo dnf install compat-openssl10
sudo dnf install https://github.com/PowerShell/PowerShell/releases/download/v7.0.3/powershell-7.0.3-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---fedora-28-29-and-30"></a><span data-ttu-id="7d474-243">Deinstallation: Fedora 28, 29 und 30</span><span class="sxs-lookup"><span data-stu-id="7d474-243">Uninstallation - Fedora 28, 29, and 30</span></span>

```sh
sudo dnf remove powershell
```

## <a name="arch-linux"></a><span data-ttu-id="7d474-244">Arch Linux</span><span class="sxs-lookup"><span data-stu-id="7d474-244">Arch Linux</span></span>

> [!NOTE]
> <span data-ttu-id="7d474-245">Arch Linux wird offiziell nicht von Microsoft unterstützt und daher von der Community verwaltet.</span><span class="sxs-lookup"><span data-stu-id="7d474-245">Arch support is not officially supported by Microsoft and is maintained by the community.</span></span>

<span data-ttu-id="7d474-246">PowerShell ist über das Benutzerrepository [Arch Linux][] verfügbar.</span><span class="sxs-lookup"><span data-stu-id="7d474-246">PowerShell is available from the [Arch Linux][] User Repository (AUR).</span></span>

- <span data-ttu-id="7d474-247">Es kann gemeinsam mit dem [zuletzt markierten Release][arch-release] kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="7d474-247">It can be compiled with the [latest tagged release][arch-release]</span></span>
- <span data-ttu-id="7d474-248">Es kann gemeinsam vom [letzten Commit für den Master][arch-git] aus kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="7d474-248">It can be compiled from the [latest commit to master][arch-git]</span></span>
- <span data-ttu-id="7d474-249">Es kann mithilfe der [zuletzt zur Veröffentlichung bestimmten Binärdatei][arch-bin] installiert werden.</span><span class="sxs-lookup"><span data-stu-id="7d474-249">It can be installed using the [latest release binary][arch-bin]</span></span>

<span data-ttu-id="7d474-250">Pakete im Benutzerrepository „Arch Linux“ werden von der Community verwaltet. Es gibt keinen offiziellen Support.</span><span class="sxs-lookup"><span data-stu-id="7d474-250">Packages in the AUR are community maintained; there's no official support.</span></span>

<span data-ttu-id="7d474-251">Weitere Informationen zum Installieren von Paketen aus dem Benutzerrepository „Arch Linux“ finden Sie im [Arch Linux-Wiki](https://wiki.archlinux.org/index.php/Arch_User_Repository#Installing_packages) oder unter [Verwenden von PowerShell in Docker](powershell-in-docker.md).</span><span class="sxs-lookup"><span data-stu-id="7d474-251">For more information on installing packages from the AUR, see the [Arch Linux wiki](https://wiki.archlinux.org/index.php/Arch_User_Repository#Installing_packages) or [Using PowerShell in Docker](powershell-in-docker.md).</span></span>

[Arch Linux]: https://www.archlinux.org/download/
[arch-release]: https://aur.archlinux.org/packages/powershell/
[arch-git]: https://aur.archlinux.org/packages/powershell-git/
[arch-bin]: https://aur.archlinux.org/packages/powershell-bin/

## <a name="snap-package"></a><span data-ttu-id="7d474-253">Snap-Paket</span><span class="sxs-lookup"><span data-stu-id="7d474-253">Snap Package</span></span>

### <a name="getting-snapd"></a><span data-ttu-id="7d474-254">Abrufen von snapd</span><span class="sxs-lookup"><span data-stu-id="7d474-254">Getting snapd</span></span>

<span data-ttu-id="7d474-255">`snapd` ist für das Ausführen von Snap-Paketen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="7d474-255">`snapd` is required to run snaps.</span></span> <span data-ttu-id="7d474-256">Halten Sie sich an [diese Anweisungen](https://docs.snapcraft.io/core/install), um sicherzustellen, dass `snapd` installiert ist.</span><span class="sxs-lookup"><span data-stu-id="7d474-256">Use [these instructions](https://docs.snapcraft.io/core/install) to make sure you have `snapd` installed.</span></span>

### <a name="installation-via-snap"></a><span data-ttu-id="7d474-257">Installation über Snap</span><span class="sxs-lookup"><span data-stu-id="7d474-257">Installation via Snap</span></span>

<span data-ttu-id="7d474-258">PowerShell für Linux wird im [Snap-Store](https://snapcraft.io/store) veröffentlicht, um die Installation und die Updates zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="7d474-258">PowerShell for Linux is published to the [Snap store](https://snapcraft.io/store) for easy installation and updates.</span></span>

<span data-ttu-id="7d474-259">Folgende Methode wird bevorzugt:</span><span class="sxs-lookup"><span data-stu-id="7d474-259">The preferred method is as follows:</span></span>

```sh
# Install PowerShell
sudo snap install powershell --classic

# Start PowerShell
pwsh
```

<span data-ttu-id="7d474-260">Gehen Sie folgendermaßen vor, wenn Sie eine Vorschauversion installieren möchten:</span><span class="sxs-lookup"><span data-stu-id="7d474-260">To install a preview version, use the following method:</span></span>

```sh
# Install PowerShell
sudo snap install powershell-preview --classic

# Start PowerShell
pwsh-preview
```

<span data-ttu-id="7d474-261">Nach der Installation wird für Snap automatisch ein Upgrade durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="7d474-261">After installation, Snap will automatically upgrade.</span></span> <span data-ttu-id="7d474-262">Sie können ein Upgrade mit `sudo snap refresh powershell` oder `sudo snap refresh powershell-preview` auslösen.</span><span class="sxs-lookup"><span data-stu-id="7d474-262">You can trigger an upgrade using `sudo snap refresh powershell` or `sudo snap refresh powershell-preview`.</span></span>

### <a name="uninstallation"></a><span data-ttu-id="7d474-263">Deinstallation</span><span class="sxs-lookup"><span data-stu-id="7d474-263">Uninstallation</span></span>

```sh
sudo snap remove powershell
```

<span data-ttu-id="7d474-264">oder</span><span class="sxs-lookup"><span data-stu-id="7d474-264">or</span></span>

```sh
sudo snap remove powershell-preview
```

## <a name="kali"></a><span data-ttu-id="7d474-265">Kali</span><span class="sxs-lookup"><span data-stu-id="7d474-265">Kali</span></span>

> [!NOTE]
> <span data-ttu-id="7d474-266">Kali wird offiziell nicht von Microsoft unterstützt und daher von der Community verwaltet.</span><span class="sxs-lookup"><span data-stu-id="7d474-266">Kali support is not officially supported by Microsoft and is maintained by the community.</span></span>

### <a name="installation---kali"></a><span data-ttu-id="7d474-267">Installation: Kali</span><span class="sxs-lookup"><span data-stu-id="7d474-267">Installation - Kali</span></span>

```sh
# Install PowerShell package
apt update && apt -y install powershell

# Start PowerShell
pwsh
```

### <a name="uninstallation---kali"></a><span data-ttu-id="7d474-268">Deinstallation: Kali</span><span class="sxs-lookup"><span data-stu-id="7d474-268">Uninstallation - Kali</span></span>

```sh
# Uninstall PowerShell package
apt -y remove powershell
```

## <a name="raspbian"></a><span data-ttu-id="7d474-269">Raspbian</span><span class="sxs-lookup"><span data-stu-id="7d474-269">Raspbian</span></span>

> [!NOTE]
> <span data-ttu-id="7d474-270">Die Unterstützung von Raspbian wird noch getestet.</span><span class="sxs-lookup"><span data-stu-id="7d474-270">Raspbian support is experimental.</span></span>

<span data-ttu-id="7d474-271">Derzeit wird PowerShell nur unter Raspbian Stretch unterstützt.</span><span class="sxs-lookup"><span data-stu-id="7d474-271">Currently, PowerShell is only supported on Raspbian Stretch.</span></span>

<span data-ttu-id="7d474-272">Außerdem funktionieren CoreCLR und PowerShell nur auf Geräten mit Pi 2 und Pi 3, da andere Geräte, wie z. B. [Pi Zero](https://github.com/dotnet/coreclr/issues/10605), einen nicht unterstützten Prozessor haben.</span><span class="sxs-lookup"><span data-stu-id="7d474-272">CoreCLR and PowerShell will only work on Pi 2 and Pi 3 devices as other devices, like [Pi Zero](https://github.com/dotnet/coreclr/issues/10605), have an unsupported processor.</span></span>

<span data-ttu-id="7d474-273">Laden Sie [Raspbian Stretch](https://www.raspberrypi.org/downloads/raspbian/) herunter, und folgen Sie den [Installationsanweisungen](https://www.raspberrypi.org/documentation/installation/installing-images/README.md), um es zu installieren.</span><span class="sxs-lookup"><span data-stu-id="7d474-273">Download [Raspbian Stretch](https://www.raspberrypi.org/downloads/raspbian/) and follow the [installation instructions](https://www.raspberrypi.org/documentation/installation/installing-images/README.md) to get it onto your Pi.</span></span>

### <a name="installation---raspbian"></a><span data-ttu-id="7d474-274">Installation: Raspbian</span><span class="sxs-lookup"><span data-stu-id="7d474-274">Installation - Raspbian</span></span>

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
wget https://github.com/PowerShell/PowerShell/releases/download/v7.0.3/powershell-7.0.3-linux-arm32.tar.gz

# Make folder to put powershell
mkdir ~/powershell

# Unpack the tar.gz file
tar -xvf ./powershell-7.0.3-linux-arm32.tar.gz -C ~/powershell

# Start PowerShell
~/powershell/pwsh
```

<span data-ttu-id="7d474-275">Optional können Sie eine symbolische Verknüpfung erstellen, damit Sie PowerShell ohne Angabe des Pfads zur Binärdatei `pwsh` starten können.</span><span class="sxs-lookup"><span data-stu-id="7d474-275">Optionally, you can create a symbolic link to start PowerShell without specifying the path to the `pwsh` binary.</span></span>

```sh
# Start PowerShell from bash with sudo to create a symbolic link
sudo ~/powershell/pwsh -c New-Item -ItemType SymbolicLink -Path "/usr/bin/pwsh" -Target "$PSHOME/pwsh" -Force

# alternatively you can run following to create a symbolic link
# sudo ln -s ~/powershell/pwsh /usr/bin/pwsh

# Now to start PowerShell you can just run "pwsh"
```

### <a name="uninstallation---raspbian"></a><span data-ttu-id="7d474-276">Deinstallation: Raspbian</span><span class="sxs-lookup"><span data-stu-id="7d474-276">Uninstallation - Raspbian</span></span>

```sh
rm -rf ~/powershell
```

## <a name="installing-preview-releases"></a><span data-ttu-id="7d474-277">Installieren von Vorschauversionen</span><span class="sxs-lookup"><span data-stu-id="7d474-277">Installing Preview Releases</span></span>

<span data-ttu-id="7d474-278">Wenn eine Vorschauversion von PowerShell für Linux über ein Paketrepository installiert wird, ändert sich der Paketname von `powershell` in `powershell-preview`.</span><span class="sxs-lookup"><span data-stu-id="7d474-278">When installing a PowerShell Preview release for Linux via a Package Repository, the package name changes from `powershell` to `powershell-preview`.</span></span>

<span data-ttu-id="7d474-279">Bei einer Installation über einen direkten Download wird nur der Dateiname geändert.</span><span class="sxs-lookup"><span data-stu-id="7d474-279">Installing via direct download doesn't change, other than the file name.</span></span>

<span data-ttu-id="7d474-280">In der nachfolgenden Tabelle werden die Befehle aufgeführt, über die Sie Pakete stabiler Versionen und von Vorschauversionen mithilfe der verschiedenen Paket-Manager installieren können:</span><span class="sxs-lookup"><span data-stu-id="7d474-280">The following table contains the commands to install the stable and preview packages using the various package managers:</span></span>

| <span data-ttu-id="7d474-281">Distribution(en)</span><span class="sxs-lookup"><span data-stu-id="7d474-281">Distribution(s)</span></span> |            <span data-ttu-id="7d474-282">Befehl für die stabile Version</span><span class="sxs-lookup"><span data-stu-id="7d474-282">Stable Command</span></span>            |               <span data-ttu-id="7d474-283">Befehl für die Vorschauversion</span><span class="sxs-lookup"><span data-stu-id="7d474-283">Preview Command</span></span>                |
| --------------- | ------------------------------------ | -------------------------------------------- |
| <span data-ttu-id="7d474-284">Ubuntu, Debian</span><span class="sxs-lookup"><span data-stu-id="7d474-284">Ubuntu, Debian</span></span>  | `sudo apt-get install -y powershell` | `sudo apt-get install -y powershell-preview` |
| <span data-ttu-id="7d474-285">CentOS, RedHat</span><span class="sxs-lookup"><span data-stu-id="7d474-285">CentOS, RedHat</span></span>  | `sudo yum install -y powershell`     | `sudo yum install -y powershell-preview`     |
| <span data-ttu-id="7d474-286">Fedora</span><span class="sxs-lookup"><span data-stu-id="7d474-286">Fedora</span></span>          | `sudo dnf install -y powershell`     | `sudo dnf install -y powershell-preview`     |

## <a name="install-as-a-net-global-tool"></a><span data-ttu-id="7d474-287">Installieren als globales .NET-Tool</span><span class="sxs-lookup"><span data-stu-id="7d474-287">Install as a .NET Global tool</span></span>

<span data-ttu-id="7d474-288">Wenn Sie das [.NET Core SDK](/dotnet/core/sdk) bereits installiert haben, können Sie PowerShell einfach als [globales .NET-Tool](/dotnet/core/tools/global-tools) installieren.</span><span class="sxs-lookup"><span data-stu-id="7d474-288">If you already have the [.NET Core SDK](/dotnet/core/sdk) installed, it's easy to install PowerShell as a [.NET Global tool](/dotnet/core/tools/global-tools).</span></span>

```
dotnet tool install --global PowerShell
```

<span data-ttu-id="7d474-289">Der .NET-Toolinstaller fügt `~/.dotnet/tools` Ihrer `PATH`-Umgebungsvariablen hinzu.</span><span class="sxs-lookup"><span data-stu-id="7d474-289">The dotnet tool installer adds `~/.dotnet/tools` to your `PATH` environment variable.</span></span> <span data-ttu-id="7d474-290">Die aktuell ausgeführte Shell verfügt jedoch nicht über den aktualisierten `PATH`.</span><span class="sxs-lookup"><span data-stu-id="7d474-290">However, the currently running shell does not have the updated `PATH`.</span></span> <span data-ttu-id="7d474-291">Sie sollten PowerShell über eine neue Shell starten können, indem Sie `pwsh` eingeben.</span><span class="sxs-lookup"><span data-stu-id="7d474-291">You should be able to start PowerShell from a new shell by typing `pwsh`.</span></span>

## <a name="binary-archives"></a><span data-ttu-id="7d474-292">Archive der Binärdateien</span><span class="sxs-lookup"><span data-stu-id="7d474-292">Binary Archives</span></span>

<span data-ttu-id="7d474-293">`tar.gz`-Archive der PowerShell-Binärdateien werden für Linux-Plattformen zur Verfügung gestellt, um erweiterte Bereitstellungsszenarios zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="7d474-293">PowerShell binary `tar.gz` archives are provided for Linux platforms to enable advanced deployment scenarios.</span></span>

### <a name="dependencies"></a><span data-ttu-id="7d474-294">Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="7d474-294">Dependencies</span></span>

<span data-ttu-id="7d474-295">PowerShell erstellt portierbare Binärdateien für alle Linux-Distributionen.</span><span class="sxs-lookup"><span data-stu-id="7d474-295">PowerShell builds portable binaries for all Linux distributions.</span></span> <span data-ttu-id="7d474-296">Allerdings erfordern die .NET Core-Runtime und PowerShell verschiedene Abhängigkeiten für die verschiedenen Distributionen.</span><span class="sxs-lookup"><span data-stu-id="7d474-296">But, .NET Core runtime requires different dependencies on different distributions, and PowerShell does too.</span></span>

<span data-ttu-id="7d474-297">Im folgenden Diagramm werden die Abhängigkeiten von .NET Core 2.0 für die verschiedenen Linux-Distributionen dargestellt, die offiziell unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="7d474-297">The following chart shows the .NET Core 2.0 dependencies that are officially supported on different Linux distributions.</span></span>

| <span data-ttu-id="7d474-298">OS</span><span class="sxs-lookup"><span data-stu-id="7d474-298">OS</span></span>                 | <span data-ttu-id="7d474-299">Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="7d474-299">Dependencies</span></span> |
| ------------------ | ------------ |
| <span data-ttu-id="7d474-300">Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="7d474-300">Ubuntu 16.04</span></span>       | <span data-ttu-id="7d474-301">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span><span class="sxs-lookup"><span data-stu-id="7d474-301">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="7d474-302">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu55</span><span class="sxs-lookup"><span data-stu-id="7d474-302">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu55</span></span> |
| <span data-ttu-id="7d474-303">Ubuntu 17.10</span><span class="sxs-lookup"><span data-stu-id="7d474-303">Ubuntu 17.10</span></span>       | <span data-ttu-id="7d474-304">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span><span class="sxs-lookup"><span data-stu-id="7d474-304">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="7d474-305">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu57</span><span class="sxs-lookup"><span data-stu-id="7d474-305">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu57</span></span> |
| <span data-ttu-id="7d474-306">Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="7d474-306">Ubuntu 18.04</span></span>       | <span data-ttu-id="7d474-307">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span><span class="sxs-lookup"><span data-stu-id="7d474-307">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="7d474-308">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu60</span><span class="sxs-lookup"><span data-stu-id="7d474-308">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu60</span></span> |
| <span data-ttu-id="7d474-309">Debian 8 (Jessie)</span><span class="sxs-lookup"><span data-stu-id="7d474-309">Debian 8 (Jessie)</span></span>  | <span data-ttu-id="7d474-310">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span><span class="sxs-lookup"><span data-stu-id="7d474-310">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="7d474-311">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu52</span><span class="sxs-lookup"><span data-stu-id="7d474-311">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu52</span></span> |
| <span data-ttu-id="7d474-312">Debian 9 (Stretch)</span><span class="sxs-lookup"><span data-stu-id="7d474-312">Debian 9 (Stretch)</span></span> | <span data-ttu-id="7d474-313">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span><span class="sxs-lookup"><span data-stu-id="7d474-313">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="7d474-314">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.2, libicu57</span><span class="sxs-lookup"><span data-stu-id="7d474-314">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.2, libicu57</span></span> |
| <span data-ttu-id="7d474-315">CentOS 7:</span><span class="sxs-lookup"><span data-stu-id="7d474-315">CentOS 7</span></span> <br> <span data-ttu-id="7d474-316">Oracle Linux 7</span><span class="sxs-lookup"><span data-stu-id="7d474-316">Oracle Linux 7</span></span> <br> <span data-ttu-id="7d474-317">RHEL 7</span><span class="sxs-lookup"><span data-stu-id="7d474-317">RHEL 7</span></span> | <span data-ttu-id="7d474-318">libunwind, libcurl, openssl-libs, libicu</span><span class="sxs-lookup"><span data-stu-id="7d474-318">libunwind, libcurl, openssl-libs, libicu</span></span> |
| <span data-ttu-id="7d474-319">openSUSE 42.3</span><span class="sxs-lookup"><span data-stu-id="7d474-319">openSUSE 42.3</span></span> | <span data-ttu-id="7d474-320">libcurl4, libopenssl1_0_0, libicu52_1</span><span class="sxs-lookup"><span data-stu-id="7d474-320">libcurl4, libopenssl1_0_0, libicu52_1</span></span> |
| <span data-ttu-id="7d474-321">openSUSE Leap 15</span><span class="sxs-lookup"><span data-stu-id="7d474-321">openSUSE Leap 15</span></span> | <span data-ttu-id="7d474-322">libcurl4, libopenssl1_0_0, libicu60_2</span><span class="sxs-lookup"><span data-stu-id="7d474-322">libcurl4, libopenssl1_0_0, libicu60_2</span></span> |
| <span data-ttu-id="7d474-323">Fedora 27</span><span class="sxs-lookup"><span data-stu-id="7d474-323">Fedora 27</span></span> <br> <span data-ttu-id="7d474-324">Fedora 28</span><span class="sxs-lookup"><span data-stu-id="7d474-324">Fedora 28</span></span> | <span data-ttu-id="7d474-325">libunwind, libcurl, openssl-libs, libicu, compat-openssl10</span><span class="sxs-lookup"><span data-stu-id="7d474-325">libunwind, libcurl, openssl-libs, libicu, compat-openssl10</span></span> |

<span data-ttu-id="7d474-326">Sie müssen zur Bereitstellung von PowerShell-Binärdateien für nicht offiziell unterstützte Linux-Distributionen die notwendigen Abhängigkeiten für das Zielbetriebssystem über zusätzliche Schritte installieren.</span><span class="sxs-lookup"><span data-stu-id="7d474-326">To deploy PowerShell binaries on Linux distributions that aren't officially supported, you need to install the necessary dependencies for the target OS in separate steps.</span></span> <span data-ttu-id="7d474-327">Beispielsweise installiert die [Amazon Linux-Dockerfile][amazon-dockerfile] zuerst die Abhängigkeiten und extrahiert anschließend das `tar.gz`-Archiv für Linux.</span><span class="sxs-lookup"><span data-stu-id="7d474-327">For example, our [Amazon Linux dockerfile][amazon-dockerfile] installs dependencies first, and then extracts the Linux `tar.gz` archive.</span></span>

[amazon-dockerfile]: https://github.com/PowerShell/PowerShell-Docker/blob/master/release/community-stable/amazonlinux/docker/Dockerfile

### <a name="installation---binary-archives"></a><span data-ttu-id="7d474-328">Installation: Archive von Binärdateien</span><span class="sxs-lookup"><span data-stu-id="7d474-328">Installation - Binary Archives</span></span>

#### <a name="linux"></a><span data-ttu-id="7d474-329">Linux</span><span class="sxs-lookup"><span data-stu-id="7d474-329">Linux</span></span>

```sh
# Download the powershell '.tar.gz' archive
curl -L -o /tmp/powershell.tar.gz https://github.com/PowerShell/PowerShell/releases/download/v7.0.3/powershell-7.0.3-linux-x64.tar.gz

# Create the target folder where powershell will be placed
sudo mkdir -p /opt/microsoft/powershell/7

# Expand powershell to the target folder
sudo tar zxf /tmp/powershell.tar.gz -C /opt/microsoft/powershell/7

# Set execute permissions
sudo chmod +x /opt/microsoft/powershell/7/pwsh

# Create the symbolic link that points to pwsh
sudo ln -s /opt/microsoft/powershell/7/pwsh /usr/bin/pwsh
```

### <a name="uninstalling-binary-archives"></a><span data-ttu-id="7d474-330">Deinstallation: Archive von Binärdateien</span><span class="sxs-lookup"><span data-stu-id="7d474-330">Uninstalling binary archives</span></span>

```sh
sudo rm -rf /usr/bin/pwsh /opt/microsoft/powershell
```

## <a name="paths"></a><span data-ttu-id="7d474-331">Paths</span><span class="sxs-lookup"><span data-stu-id="7d474-331">Paths</span></span>

- <span data-ttu-id="7d474-332">`$PSHOME` ist `/opt/microsoft/powershell/7/`.</span><span class="sxs-lookup"><span data-stu-id="7d474-332">`$PSHOME` is `/opt/microsoft/powershell/7/`</span></span>
- <span data-ttu-id="7d474-333">Benutzerprofile werden über `~/.config/powershell/profile.ps1` gelesen.</span><span class="sxs-lookup"><span data-stu-id="7d474-333">User profiles will be read from `~/.config/powershell/profile.ps1`</span></span>
- <span data-ttu-id="7d474-334">Standardprofile werden über `$PSHOME/profile.ps1` gelesen.</span><span class="sxs-lookup"><span data-stu-id="7d474-334">Default profiles will be read from `$PSHOME/profile.ps1`</span></span>
- <span data-ttu-id="7d474-335">Benutzermodule werden über `~/.local/share/powershell/Modules` gelesen.</span><span class="sxs-lookup"><span data-stu-id="7d474-335">User modules will be read from `~/.local/share/powershell/Modules`</span></span>
- <span data-ttu-id="7d474-336">Freigegebene Module werden über `/usr/local/share/powershell/Modules` gelesen.</span><span class="sxs-lookup"><span data-stu-id="7d474-336">Shared modules will be read from `/usr/local/share/powershell/Modules`</span></span>
- <span data-ttu-id="7d474-337">Standardmodule werden über `$PSHOME/Modules` gelesen.</span><span class="sxs-lookup"><span data-stu-id="7d474-337">Default modules will be read from `$PSHOME/Modules`</span></span>
- <span data-ttu-id="7d474-338">Der Verlauf von „PSReadline“ wird in `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt` aufgezeichnet.</span><span class="sxs-lookup"><span data-stu-id="7d474-338">PSReadLine history will be recorded to `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt`</span></span>

<span data-ttu-id="7d474-339">Die Profile beachten die Konfigurationen von PowerShell pro Host. Das bedeutet, die hostspezifischen Standardprofile sind an denselben Orten unter `Microsoft.PowerShell_profile.ps1` gespeichert.</span><span class="sxs-lookup"><span data-stu-id="7d474-339">The profiles respect PowerShell's per-host configuration, so the default host-specific profiles exists at `Microsoft.PowerShell_profile.ps1` in the same locations.</span></span>

<span data-ttu-id="7d474-340">PowerShell hält die [XDG Base Directory Specification (XDG Base Directory-Spezifikation)][xdg-bds] unter Linux ein.</span><span class="sxs-lookup"><span data-stu-id="7d474-340">PowerShell respects the [XDG Base Directory Specification][xdg-bds] on Linux.</span></span>

## <a name="installation-support"></a><span data-ttu-id="7d474-341">Installationsunterstützung</span><span class="sxs-lookup"><span data-stu-id="7d474-341">Installation support</span></span>

<span data-ttu-id="7d474-342">Microsoft unterstützt die in diesem Dokument beschriebenen Installationsmethoden.</span><span class="sxs-lookup"><span data-stu-id="7d474-342">Microsoft supports the installation methods in this document.</span></span> <span data-ttu-id="7d474-343">Möglicherweise stehen andere Installationsmethoden aus anderen Quellen zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="7d474-343">There may be other methods of installation available from other sources.</span></span> <span data-ttu-id="7d474-344">Auch wenn diese Tools und Methoden funktionieren, kann Microsoft sie nicht unterstützen.</span><span class="sxs-lookup"><span data-stu-id="7d474-344">While those tools and methods may work, Microsoft cannot support those methods.</span></span>

<!-- link references -->
[Freigaben]: https://github.com/PowerShell/PowerShell/releases/latest
[releases]: https://github.com/PowerShell/PowerShell/releases/latest
[xdg-bds]: https://specifications.freedesktop.org/basedir-spec/basedir-spec-latest.html
[distros]: https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md#linux
[Anforderung von Verteilungsunterstützung]: https://github.com/PowerShell/PowerShell/issues/new?assignees=&labels=Distribution-Request&template=Distribution_Request.md&title=Distribution+Support+Request
[Distribution Support Request]: https://github.com/PowerShell/PowerShell/issues/new?assignees=&labels=Distribution-Request&template=Distribution_Request.md&title=Distribution+Support+Request
