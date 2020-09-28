---
title: Installieren von PowerShell unter macOS
description: Informationen zur Installation von PowerShell unter macOS
ms.date: 09/23/2020
ms.openlocfilehash: 86647888910fb27528fb78c46a457fa1da856eb0
ms.sourcegitcommit: 51104c7932a185b4d3293dbca306625369687468
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2020
ms.locfileid: "91224683"
---
# <a name="installing-powershell-on-macos"></a><span data-ttu-id="78a80-103">Installieren von PowerShell unter macOS</span><span class="sxs-lookup"><span data-stu-id="78a80-103">Installing PowerShell on macOS</span></span>

<span data-ttu-id="78a80-104">PowerShell unterstützt macOS 10.12 und höher.</span><span class="sxs-lookup"><span data-stu-id="78a80-104">PowerShell supports macOS 10.12 and higher.</span></span> <span data-ttu-id="78a80-105">PowerShell 7.0.3 und höher sowie die PowerShell-Vorschauversionen 7.1.0 und höher erfordern macOS 10.13 und höher.</span><span class="sxs-lookup"><span data-stu-id="78a80-105">PowerShell 7.0.3 or higher and PowerShell Preview 7.1.0 or higher require macOS 10.13 and higher.</span></span> <span data-ttu-id="78a80-106">Sämtliche Pakete sind auf der Seite [Freigaben][] über GitHub verfügbar.</span><span class="sxs-lookup"><span data-stu-id="78a80-106">All packages are available on our GitHub [releases][] page.</span></span> <span data-ttu-id="78a80-107">Nachdem Sie das Paket installiert haben, führen Sie `pwsh` über das Terminal aus.</span><span class="sxs-lookup"><span data-stu-id="78a80-107">After the package is installed, run `pwsh` from a terminal.</span></span>

> [!NOTE]
> <span data-ttu-id="78a80-108">PowerShell 7 ist ein direktes Upgrade, mit dem PowerShell Core 6.x entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="78a80-108">PowerShell 7 is an in-place upgrade that removes PowerShell Core 6.x.</span></span>
>
> <span data-ttu-id="78a80-109">Der Ordner `/usr/local/microsoft/powershell/6` wird durch `/usr/local/microsoft/powershell/7` ersetzt.</span><span class="sxs-lookup"><span data-stu-id="78a80-109">The `/usr/local/microsoft/powershell/6` folder is replaced by `/usr/local/microsoft/powershell/7`.</span></span>
>
> <span data-ttu-id="78a80-110">Wenn Sie PowerShell 6 und PowerShell 7 parallel ausführen müssen, installieren Sie PowerShell 6 mithilfe der [binary archive](#binary-archives)-Methode neu.</span><span class="sxs-lookup"><span data-stu-id="78a80-110">If you need to run PowerShell 6 side-by-side with PowerShell 7, reinstall PowerShell 6 using the [binary archive](#binary-archives) method.</span></span>

<span data-ttu-id="78a80-111">Es gibt mehrere Möglichkeiten, PowerShell unter macOS zu installieren.</span><span class="sxs-lookup"><span data-stu-id="78a80-111">There are several ways to install PowerShell on macOS.</span></span> <span data-ttu-id="78a80-112">Wählen Sie eine der folgenden Methoden:</span><span class="sxs-lookup"><span data-stu-id="78a80-112">Choose one of the following methods:</span></span>

- <span data-ttu-id="78a80-113">Verwenden Sie für die Installation Homebrew.</span><span class="sxs-lookup"><span data-stu-id="78a80-113">Install using Homebrew.</span></span> <span data-ttu-id="78a80-114">Bei Homebrew handelt es sich um den bevorzugten Paket-Manager für macOS.</span><span class="sxs-lookup"><span data-stu-id="78a80-114">Homebrew is the preferred package manager for macOS.</span></span>
- <span data-ttu-id="78a80-115">Installieren Sie PowerShell über einen [direkten Download](#installation-via-direct-download).</span><span class="sxs-lookup"><span data-stu-id="78a80-115">Install PowerShell via [Direct Download](#installation-via-direct-download)</span></span>
- <span data-ttu-id="78a80-116">Führen Sie die Installation über [Archive der Binärdateien](#binary-archives) aus.</span><span class="sxs-lookup"><span data-stu-id="78a80-116">Install from [binary archives](#binary-archives).</span></span>

<span data-ttu-id="78a80-117">Installieren Sie nach der Installation von PowerShell [OpenSSL](#installing-dependencies).</span><span class="sxs-lookup"><span data-stu-id="78a80-117">After installing PowerShell, you should install [OpenSSL](#installing-dependencies).</span></span> <span data-ttu-id="78a80-118">OpenSSL ist für PowerShell-Remotingfunktionen und CIM-Vorgänge erforderlich.</span><span class="sxs-lookup"><span data-stu-id="78a80-118">OpenSSL is needed for PowerShell remoting and CIM operations.</span></span>

## <a name="installation-of-latest-stable-release-via-homebrew-on-macos-1013-or-higher"></a><span data-ttu-id="78a80-119">Installation des neuesten stabilen Releases über Homebrew unter macOS 10.13 oder höher</span><span class="sxs-lookup"><span data-stu-id="78a80-119">Installation of latest stable release via Homebrew on macOS 10.13 or higher</span></span>

<span data-ttu-id="78a80-120">Wenn der Befehl `brew` nicht gefunden wird, müssen Sie Homebrew installieren, indem Sie [die entsprechenden Anweisungen][brew] ausführen.</span><span class="sxs-lookup"><span data-stu-id="78a80-120">If the `brew` command is not found, you need to install Homebrew following [their instructions][brew].</span></span>

<span data-ttu-id="78a80-121">Jetzt können Sie PowerShell installieren:</span><span class="sxs-lookup"><span data-stu-id="78a80-121">Now, you can install PowerShell:</span></span>

```sh
brew cask install powershell
```

<span data-ttu-id="78a80-122">Vergewissern Sie sich abschließend, dass Ihre Installation voll funktionsfähig ist:</span><span class="sxs-lookup"><span data-stu-id="78a80-122">Finally, verify that your install is working properly:</span></span>

```sh
pwsh
```

<span data-ttu-id="78a80-123">Wenn neue Versionen von PowerShell veröffentlicht werden, aktualisieren Sie die Formeln für Homebrew, und führen Sie ein Upgrade für PowerShell aus:</span><span class="sxs-lookup"><span data-stu-id="78a80-123">When new versions of PowerShell are released, update Homebrew's formulae and upgrade PowerShell:</span></span>

```sh
brew update
brew upgrade powershell --cask
```

> [!NOTE]
> <span data-ttu-id="78a80-124">Die oben genannten Befehle können innerhalb eines PowerShell-Hosts (pwsh) aufgerufen werden. Allerdings muss dann die Shell von PowerShell beendet und neu gestartet werden, um das Upgrade abzuschließen und die in `$PSVersionTable` dargestellten Werte zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="78a80-124">The commands above can be called from within a PowerShell (pwsh) host, but then the PowerShell shell must be exited and restarted to complete the upgrade and refresh the values shown in `$PSVersionTable`.</span></span>

[brew]: https://brew.sh/

## <a name="installation-of-latest-preview-release-via-homebrew-on-macos-1013-or-higher"></a><span data-ttu-id="78a80-125">Installation der neuesten Vorschauversion über Homebrew unter macOS 10.13 oder höher</span><span class="sxs-lookup"><span data-stu-id="78a80-125">Installation of latest preview release via Homebrew on macOS 10.13 or higher</span></span>

<span data-ttu-id="78a80-126">Nachdem Sie Homebrew installiert haben, können Sie PowerShell installieren.</span><span class="sxs-lookup"><span data-stu-id="78a80-126">After you've installed Homebrew, you can install PowerShell.</span></span> <span data-ttu-id="78a80-127">Installieren Sie zunächst das Paket [Cask-Versions][cask-versions]. Dies ermöglicht Ihnen das Installieren alternativer Versionen von Cask-Paketen:</span><span class="sxs-lookup"><span data-stu-id="78a80-127">First, install the [Cask-Versions][cask-versions] package that lets you install alternative versions of cask packages:</span></span>

```sh
brew tap homebrew/cask-versions
```

<span data-ttu-id="78a80-128">Jetzt können Sie PowerShell installieren:</span><span class="sxs-lookup"><span data-stu-id="78a80-128">Now, you can install PowerShell:</span></span>

```sh
brew cask install powershell-preview
```

<span data-ttu-id="78a80-129">Vergewissern Sie sich abschließend, dass Ihre Installation voll funktionsfähig ist:</span><span class="sxs-lookup"><span data-stu-id="78a80-129">Finally, verify that your install is working properly:</span></span>

```sh
pwsh-preview
```

<span data-ttu-id="78a80-130">Wenn neue Versionen von PowerShell veröffentlicht werden, aktualisieren Sie die Formeln für Homebrew, und führen Sie ein Upgrade für PowerShell aus:</span><span class="sxs-lookup"><span data-stu-id="78a80-130">When new versions of PowerShell are released, update Homebrew's formulae and upgrade PowerShell:</span></span>

```sh
brew update
brew upgrade powershell-preview --cask
```

> [!NOTE]
> <span data-ttu-id="78a80-131">Die oben genannten Befehle können innerhalb eines PowerShell-Hosts (pwsh) aufgerufen werden, die Shell von PowerShell muss dann jedoch beendet und neu angegeben werden, um das Upgrade abzuschließen</span><span class="sxs-lookup"><span data-stu-id="78a80-131">The commands above can be called from within a PowerShell (pwsh) host, but then the PowerShell shell must be exited and restarted to complete the upgrade.</span></span>
> <span data-ttu-id="78a80-132">und die in `$PSVersionTable` dargestellten Werte zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="78a80-132">and refresh the values shown in `$PSVersionTable`.</span></span>

<span data-ttu-id="78a80-133">Die Installation von PowerShell über die TAP-Methode Homebrew wird auch für stabile und LTS-Versionen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="78a80-133">Installing PowerShell using the Homebrew tap method is also supported for stable and LTS versions.</span></span>

```sh
brew install powershell/tap/powershell
```

<span data-ttu-id="78a80-134">Überprüfen Sie nun die Installation.</span><span class="sxs-lookup"><span data-stu-id="78a80-134">You can now verify your install</span></span>

```sh
pwsh
```

<span data-ttu-id="78a80-135">Wurden bereits neue Versionen von PowerShell veröffentlicht, führen Sie einfach den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="78a80-135">When new versions of PowerShell are released, simply run the following command.</span></span>

```sh
brew upgrade powershell
```

> [!NOTE]
> <span data-ttu-id="78a80-136">Verwenden Sie bei einem Update auf eine neuere PowerShell-Version dieselbe Methode (CASK oder TAP), die Sie bei der Erstinstallation von PowerShell verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="78a80-136">Whether you use the cask or the tap method, when updating to a newer version of PowerShell, use the same method you used to initially install PowerShell.</span></span> <span data-ttu-id="78a80-137">Andernfalls wird beim Öffnen einer neuen pwsh-Sitzung weiterhin die ältere Version von PowerShell verwendet.</span><span class="sxs-lookup"><span data-stu-id="78a80-137">If you use a different method, opening a new pwsh session will continue to use the older version of PowerShell.</span></span>
>
> <span data-ttu-id="78a80-138">Wenn Sie sich dennoch für unterschiedliche Methoden entscheiden, können Sie das Problem mithilfe der [LINK-Methode von Homebrew](https://docs.brew.sh/Manpage#link-ln-options-formula) beheben.</span><span class="sxs-lookup"><span data-stu-id="78a80-138">If you do decide to use different methods, there are ways to correct the issue using the [Homebrew link method](https://docs.brew.sh/Manpage#link-ln-options-formula).</span></span>

## <a name="installation-via-direct-download"></a><span data-ttu-id="78a80-139">Installation über einen direkten Download</span><span class="sxs-lookup"><span data-stu-id="78a80-139">Installation via Direct Download</span></span>

<span data-ttu-id="78a80-140">Laden Sie das PKG-Paket `powershell-lts-7.0.3-osx-x64.pkg` über die Seite [Releases][] auf den macOS-Computer herunter.</span><span class="sxs-lookup"><span data-stu-id="78a80-140">Download the PKG package `powershell-lts-7.0.3-osx-x64.pkg` from the [releases][] page onto your macOS machine.</span></span>

<span data-ttu-id="78a80-141">Doppelklicken Sie entweder auf die Datei, und befolgen Sie die Anweisungen, oder installieren Sie das Paket über das Terminal:</span><span class="sxs-lookup"><span data-stu-id="78a80-141">You can double-click the file and follow the prompts, or install it from the terminal:</span></span>

```sh
sudo installer -pkg powershell-lts-7.0.3-osx-x64.pkg -target /
```

<span data-ttu-id="78a80-142">Installieren Sie [OpenSSL](#installing-dependencies).</span><span class="sxs-lookup"><span data-stu-id="78a80-142">Install [OpenSSL](#installing-dependencies).</span></span> <span data-ttu-id="78a80-143">OpenSSL ist für PowerShell-Remotingfunktionen und CIM-Vorgänge erforderlich.</span><span class="sxs-lookup"><span data-stu-id="78a80-143">OpenSSL is needed for PowerShell remoting and CIM operations.</span></span>

## <a name="install-as-a-net-global-tool"></a><span data-ttu-id="78a80-144">Installieren als globales .NET-Tool</span><span class="sxs-lookup"><span data-stu-id="78a80-144">Install as a .NET Global tool</span></span>

<span data-ttu-id="78a80-145">Wenn Sie das [.NET Core SDK](/dotnet/core/sdk) bereits installiert haben, können Sie PowerShell einfach als [globales .NET-Tool](/dotnet/core/tools/global-tools) installieren.</span><span class="sxs-lookup"><span data-stu-id="78a80-145">If you already have the [.NET Core SDK](/dotnet/core/sdk) installed, it's easy to install PowerShell as a [.NET Global tool](/dotnet/core/tools/global-tools).</span></span>

```
dotnet tool install --global PowerShell
```

<span data-ttu-id="78a80-146">Der .NET-Toolinstaller fügt `~/.dotnet/tools` Ihrer `PATH`-Umgebungsvariablen hinzu.</span><span class="sxs-lookup"><span data-stu-id="78a80-146">The dotnet tool installer adds `~/.dotnet/tools` to your `PATH` environment variable.</span></span> <span data-ttu-id="78a80-147">Die aktuell ausgeführte Shell verfügt jedoch nicht über den aktualisierten `PATH`.</span><span class="sxs-lookup"><span data-stu-id="78a80-147">However, the currently running shell does not have the updated `PATH`.</span></span> <span data-ttu-id="78a80-148">Sie sollten PowerShell über eine neue Shell starten können, indem Sie `pwsh` eingeben.</span><span class="sxs-lookup"><span data-stu-id="78a80-148">You should be able to start PowerShell from a new shell by typing `pwsh`.</span></span>

<span data-ttu-id="78a80-149">Installieren Sie [OpenSSL](#installing-dependencies).</span><span class="sxs-lookup"><span data-stu-id="78a80-149">Install [OpenSSL](#installing-dependencies).</span></span> <span data-ttu-id="78a80-150">OpenSSL ist für PowerShell-Remotingfunktionen und CIM-Vorgänge erforderlich.</span><span class="sxs-lookup"><span data-stu-id="78a80-150">OpenSSL is needed for PowerShell remoting and CIM operations.</span></span>

## <a name="binary-archives"></a><span data-ttu-id="78a80-151">Archive der Binärdateien</span><span class="sxs-lookup"><span data-stu-id="78a80-151">Binary Archives</span></span>

<span data-ttu-id="78a80-152">`tar.gz`-Archive der PowerShell-Binärdateien werden für die macOS-Plattform zur Verfügung gestellt, um erweiterte Bereitstellungsszenarios zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="78a80-152">PowerShell binary `tar.gz` archives are provided for the macOS platform to enable advanced deployment scenarios.</span></span> <span data-ttu-id="78a80-153">Wenn Sie die Installation mit dieser Methode durchführen, müssen Sie auch alle Abhängigkeiten manuell installieren.</span><span class="sxs-lookup"><span data-stu-id="78a80-153">When you install using this method you must also manually install any dependencies.</span></span>

<span data-ttu-id="78a80-154">Installieren Sie [OpenSSL](#installing-dependencies).</span><span class="sxs-lookup"><span data-stu-id="78a80-154">Install [OpenSSL](#installing-dependencies).</span></span> <span data-ttu-id="78a80-155">OpenSSL ist für PowerShell-Remotingfunktionen und CIM-Vorgänge erforderlich.</span><span class="sxs-lookup"><span data-stu-id="78a80-155">OpenSSL is needed for PowerShell remoting and CIM operations.</span></span>

### <a name="installing-binary-archives-on-macos"></a><span data-ttu-id="78a80-156">Installieren von Archiven der Binärdateien unter macOS</span><span class="sxs-lookup"><span data-stu-id="78a80-156">Installing binary archives on macOS</span></span>

```sh
# Download the powershell '.tar.gz' archive
curl -L -o /tmp/powershell.tar.gz https://github.com/PowerShell/PowerShell/releases/download/v7.0.3/powershell-7.0.3-osx-x64.tar.gz

# Create the target folder where powershell will be placed
sudo mkdir -p /usr/local/microsoft/powershell/7.0.3

# Expand powershell to the target folder
sudo tar zxf /tmp/powershell.tar.gz -C /usr/local/microsoft/powershell/7.0.3

# Set execute permissions
sudo chmod +x /usr/local/microsoft/powershell/7.0.3/pwsh

# Create the symbolic link that points to pwsh
sudo ln -s /usr/local/microsoft/powershell/7.0.3/pwsh /usr/local/bin/pwsh
```

## <a name="installing-dependencies"></a><span data-ttu-id="78a80-157">Installieren von Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="78a80-157">Installing dependencies</span></span>

<span data-ttu-id="78a80-158">Für PowerShell-Remoting und CIM-Vorgänge ist OpenSSL erforderlich.</span><span class="sxs-lookup"><span data-stu-id="78a80-158">OpenSSL is required for PowerShell remoting and CIM operations.</span></span> <span data-ttu-id="78a80-159">Bei Bedarf können Sie OpenSSL über MacPorts installieren.</span><span class="sxs-lookup"><span data-stu-id="78a80-159">You can install OpenSSL via MacPorts if needed.</span></span>

> [!NOTE]
> <span data-ttu-id="78a80-160">Werden MacPorts und Homebrew im selben System verwendet, können Probleme auftreten.</span><span class="sxs-lookup"><span data-stu-id="78a80-160">MacPorts and Homebrew can have problems when used to together on the same system.</span></span> <span data-ttu-id="78a80-161">Homebrew verfügt jedoch über kein Paket für OpenSSL 1.0.</span><span class="sxs-lookup"><span data-stu-id="78a80-161">However, Homebrew does not have a package for OpenSSL 1.0.</span></span> <span data-ttu-id="78a80-162">Weitere Informationen finden Sie in den [Häufig gestellten Fragen zu MacPorts](https://trac.macports.org/wiki/FAQ).</span><span class="sxs-lookup"><span data-stu-id="78a80-162">For more information, see the [MacPorts FAQ](https://trac.macports.org/wiki/FAQ).</span></span>

1. <span data-ttu-id="78a80-163">Installieren Sie die Xcode-Befehlszeilentools.</span><span class="sxs-lookup"><span data-stu-id="78a80-163">Install the Xcode command-line tools.</span></span> <span data-ttu-id="78a80-164">Diese sind für MacPorts erforderlich.</span><span class="sxs-lookup"><span data-stu-id="78a80-164">The Xcode tools are required by MacPorts.</span></span>

   ```sh
   xcode-select --install
   ```

1. <span data-ttu-id="78a80-165">Installieren Sie MacPorts.</span><span class="sxs-lookup"><span data-stu-id="78a80-165">Install MacPorts.</span></span> <span data-ttu-id="78a80-166">Wenn Sie Anleitungen dazu benötigen, lesen Sie das [Installationshandbuch](https://www.macports.org/install.php).</span><span class="sxs-lookup"><span data-stu-id="78a80-166">If you need instructions, refer to the [installation guide](https://www.macports.org/install.php).</span></span>
1. <span data-ttu-id="78a80-167">Aktualisieren Sie MacPorts durch Ausführen von `sudo port selfupdate`.</span><span class="sxs-lookup"><span data-stu-id="78a80-167">Update MacPorts by running `sudo port selfupdate`.</span></span>
1. <span data-ttu-id="78a80-168">Führen Sie eine Upgrade von MacPorts-Paketen durch Ausführen von `sudo port upgrade outdated` durch.</span><span class="sxs-lookup"><span data-stu-id="78a80-168">Upgrade MacPorts packages by running `sudo port upgrade outdated`.</span></span>
1. <span data-ttu-id="78a80-169">Installieren Sie OpenSSL durch Ausführen von `sudo port install openssl10`.</span><span class="sxs-lookup"><span data-stu-id="78a80-169">Install OpenSSL by running `sudo port install openssl10`.</span></span>
1. <span data-ttu-id="78a80-170">Verknüpfen Sie die Bibliotheken, um sie PowerShell zur Verfügung zu stellen:</span><span class="sxs-lookup"><span data-stu-id="78a80-170">Link the libraries to make them available to PowerShell:</span></span>

   ```sh
   sudo mkdir -p /usr/local/opt/openssl
   sudo ln -s /opt/local/lib/openssl-1.0 /usr/local/opt/openssl/lib
   ```

## <a name="uninstalling-powershell"></a><span data-ttu-id="78a80-171">Deinstallieren von PowerShell</span><span class="sxs-lookup"><span data-stu-id="78a80-171">Uninstalling PowerShell</span></span>

<span data-ttu-id="78a80-172">Wenn Sie PowerShell mit Homebrew installiert haben, verwenden Sie den folgenden Befehl zum Deinstallieren:</span><span class="sxs-lookup"><span data-stu-id="78a80-172">If you installed PowerShell with Homebrew, use the following command to uninstall:</span></span>

```sh
brew cask uninstall powershell
```

<span data-ttu-id="78a80-173">Wenn Sie PowerShell über einen direkten Download installiert haben, muss PowerShell manuell entfernt werden:</span><span class="sxs-lookup"><span data-stu-id="78a80-173">If you installed PowerShell via direct download, PowerShell must be removed manually:</span></span>

```sh
sudo rm -rf /usr/local/bin/pwsh /usr/local/microsoft/powershell
```

<span data-ttu-id="78a80-174">Lesen Sie den Abschnitt [Pfade](#paths) in diesem Artikel, um zu erfahren, wie Sie zusätzliche PowerShell-Pfade deinstallieren können. Entfernen Sie die Pfade mithilfe von `sudo rm`.</span><span class="sxs-lookup"><span data-stu-id="78a80-174">To remove the additional PowerShell paths, refer to the [paths](#paths) section in this document and remove the paths using `sudo rm`.</span></span>

> [!NOTE]
> <span data-ttu-id="78a80-175">Dies ist nicht notwendig, wenn Sie eine Installation mit Homebrew durchgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="78a80-175">This is not necessary if you installed with Homebrew.</span></span>

## <a name="paths"></a><span data-ttu-id="78a80-176">Paths</span><span class="sxs-lookup"><span data-stu-id="78a80-176">Paths</span></span>

- <span data-ttu-id="78a80-177">`$PSHOME` ist `/usr/local/microsoft/powershell/7.0.3/`.</span><span class="sxs-lookup"><span data-stu-id="78a80-177">`$PSHOME` is `/usr/local/microsoft/powershell/7.0.3/`</span></span>
- <span data-ttu-id="78a80-178">Benutzerprofile werden über `~/.config/powershell/profile.ps1` gelesen.</span><span class="sxs-lookup"><span data-stu-id="78a80-178">User profiles will be read from `~/.config/powershell/profile.ps1`</span></span>
- <span data-ttu-id="78a80-179">Standardprofile werden über `$PSHOME/profile.ps1` gelesen.</span><span class="sxs-lookup"><span data-stu-id="78a80-179">Default profiles will be read from `$PSHOME/profile.ps1`</span></span>
- <span data-ttu-id="78a80-180">Benutzermodule werden über `~/.local/share/powershell/Modules` gelesen.</span><span class="sxs-lookup"><span data-stu-id="78a80-180">User modules will be read from `~/.local/share/powershell/Modules`</span></span>
- <span data-ttu-id="78a80-181">Freigegebene Module werden über `/usr/local/share/powershell/Modules` gelesen.</span><span class="sxs-lookup"><span data-stu-id="78a80-181">Shared modules will be read from `/usr/local/share/powershell/Modules`</span></span>
- <span data-ttu-id="78a80-182">Standardmodule werden über `$PSHOME/Modules` gelesen.</span><span class="sxs-lookup"><span data-stu-id="78a80-182">Default modules will be read from `$PSHOME/Modules`</span></span>
- <span data-ttu-id="78a80-183">Der Verlauf von „PSReadline“ wird in `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt` aufgezeichnet.</span><span class="sxs-lookup"><span data-stu-id="78a80-183">PSReadline history will be recorded to `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt`</span></span>

<span data-ttu-id="78a80-184">Die Profile halten sich an die Konfiguration von PowerShell pro Host.</span><span class="sxs-lookup"><span data-stu-id="78a80-184">The profiles respect PowerShell's per-host configuration.</span></span> <span data-ttu-id="78a80-185">Dies bedeutet, dass hostspezifische Standardprofile in `Microsoft.PowerShell_profile.ps1` am gleichen Speicherort vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="78a80-185">So the default host-specific profile exists at `Microsoft.PowerShell_profile.ps1` in the same locations.</span></span>

<span data-ttu-id="78a80-186">PowerShell hält die [XDG Base Directory Specification (XDG Base Directory-Spezifikation)][xdg-bds] unter macOs ein.</span><span class="sxs-lookup"><span data-stu-id="78a80-186">PowerShell respects the [XDG Base Directory Specification][xdg-bds] on macOS.</span></span>

<span data-ttu-id="78a80-187">Da macOS eine Ableitung von BSD ist, wird das Präfix `/usr/local` anstelle von `/opt` verwendet.</span><span class="sxs-lookup"><span data-stu-id="78a80-187">Because macOS is a derivation of BSD, the prefix `/usr/local` is used instead of `/opt`.</span></span> <span data-ttu-id="78a80-188">Daher ist `$PSHOME` gleich `/usr/local/microsoft/powershell/7.0.3/`, und der symbolische Link wird unter `/usr/local/bin/pwsh` gespeichert.</span><span class="sxs-lookup"><span data-stu-id="78a80-188">So, `$PSHOME` is `/usr/local/microsoft/powershell/7.0.3/`, and the symbolic link is placed at `/usr/local/bin/pwsh`.</span></span>

## <a name="installation-support"></a><span data-ttu-id="78a80-189">Installationsunterstützung</span><span class="sxs-lookup"><span data-stu-id="78a80-189">Installation support</span></span>

<span data-ttu-id="78a80-190">Microsoft unterstützt die in diesem Dokument beschriebenen Installationsmethoden.</span><span class="sxs-lookup"><span data-stu-id="78a80-190">Microsoft supports the installation methods in this document.</span></span> <span data-ttu-id="78a80-191">Möglicherweise stehen andere Installationsmethoden aus anderen Quellen zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="78a80-191">There may be other methods of installation available from other sources.</span></span> <span data-ttu-id="78a80-192">Auch wenn diese Tools und Methoden funktionieren, kann Microsoft sie nicht unterstützen.</span><span class="sxs-lookup"><span data-stu-id="78a80-192">While those tools and methods may work, Microsoft cannot support those methods.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="78a80-193">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="78a80-193">Additional Resources</span></span>

- <span data-ttu-id="78a80-194">[Homebrew-Website][brew]</span><span class="sxs-lookup"><span data-stu-id="78a80-194">[Homebrew Web][brew]</span></span>
- <span data-ttu-id="78a80-195">[Homebrew-GitHub-Repository][GitHub]</span><span class="sxs-lookup"><span data-stu-id="78a80-195">[Homebrew Github Repository][GitHub]</span></span>
- <span data-ttu-id="78a80-196">[Homebrew-Cask][cask]</span><span class="sxs-lookup"><span data-stu-id="78a80-196">[Homebrew-Cask][cask]</span></span>

[brew]: http://brew.sh/
[Cask]: https://github.com/Homebrew/homebrew-cask
[cask-versions]: https://github.com/Homebrew/homebrew-cask-versions
[GitHub]: https://github.com/Homebrew
[Freigaben]: https://github.com/PowerShell/PowerShell/releases/latest
[releases]: https://github.com/PowerShell/PowerShell/releases/latest
[xdg-bds]: https://specifications.freedesktop.org/basedir-spec/basedir-spec-latest.html
