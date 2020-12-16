---
title: Installieren von PowerShell unter macOS
description: Informationen zur Installation von PowerShell unter macOS
ms.date: 11/11/2020
ms.openlocfilehash: 1ce96e993d8fc87edd93fca840ede250d5632577
ms.sourcegitcommit: 3ab2951a5460a39ca5fb3d25ffcb1d8868f4e011
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2020
ms.locfileid: "96535099"
---
# <a name="installing-powershell-on-macos"></a><span data-ttu-id="b4f05-103">Installieren von PowerShell unter macOS</span><span class="sxs-lookup"><span data-stu-id="b4f05-103">Installing PowerShell on macOS</span></span>

<span data-ttu-id="b4f05-104">Ab PowerShell 7.0 ist mindestens macOS 10.13 erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b4f05-104">PowerShell 7.0 or higher require macOS 10.13 and higher.</span></span> <span data-ttu-id="b4f05-105">Sämtliche Pakete sind auf der Seite [Freigaben][] über GitHub verfügbar.</span><span class="sxs-lookup"><span data-stu-id="b4f05-105">All packages are available on our GitHub [releases][] page.</span></span> <span data-ttu-id="b4f05-106">Nachdem Sie das Paket installiert haben, führen Sie `pwsh` über das Terminal aus.</span><span class="sxs-lookup"><span data-stu-id="b4f05-106">After the package is installed, run `pwsh` from a terminal.</span></span>

> [!NOTE]
> <span data-ttu-id="b4f05-107">PowerShell 7.1 ist ein direktes Upgrade, das PowerShell Core 6.x und 7.0 ersetzt.</span><span class="sxs-lookup"><span data-stu-id="b4f05-107">PowerShell 7.1 is an in-place upgrade that removes PowerShell Core 6.x and 7.0.</span></span>
>
> <span data-ttu-id="b4f05-108">Der Ordner `/usr/local/microsoft/powershell/6` wird durch `/usr/local/microsoft/powershell/7` ersetzt.</span><span class="sxs-lookup"><span data-stu-id="b4f05-108">The `/usr/local/microsoft/powershell/6` folder is replaced by `/usr/local/microsoft/powershell/7`.</span></span>
>
> <span data-ttu-id="b4f05-109">Wenn Sie eine ältere Version von PowerShell Core parallel zu PowerShell 7.1 ausführen möchten, installieren Sie die gewünschte Version mithilfe der Methode unter [Archive der Binärdateien](#binary-archives).</span><span class="sxs-lookup"><span data-stu-id="b4f05-109">If you need to run and older version of PowerShell core side-by-side with PowerShell 7.1, install the version you want using the [binary archive](#binary-archives) method.</span></span>

<span data-ttu-id="b4f05-110">Es gibt mehrere Möglichkeiten, PowerShell unter macOS zu installieren.</span><span class="sxs-lookup"><span data-stu-id="b4f05-110">There are several ways to install PowerShell on macOS.</span></span> <span data-ttu-id="b4f05-111">Wählen Sie eine der folgenden Methoden:</span><span class="sxs-lookup"><span data-stu-id="b4f05-111">Choose one of the following methods:</span></span>

- <span data-ttu-id="b4f05-112">Verwenden Sie für die Installation Homebrew.</span><span class="sxs-lookup"><span data-stu-id="b4f05-112">Install using Homebrew.</span></span> <span data-ttu-id="b4f05-113">Bei Homebrew handelt es sich um den bevorzugten Paket-Manager für macOS.</span><span class="sxs-lookup"><span data-stu-id="b4f05-113">Homebrew is the preferred package manager for macOS.</span></span>
- <span data-ttu-id="b4f05-114">Installieren Sie PowerShell über einen [direkten Download](#installation-via-direct-download).</span><span class="sxs-lookup"><span data-stu-id="b4f05-114">Install PowerShell via [Direct Download](#installation-via-direct-download)</span></span>
- <span data-ttu-id="b4f05-115">Führen Sie die Installation über [Archive der Binärdateien](#binary-archives) aus.</span><span class="sxs-lookup"><span data-stu-id="b4f05-115">Install from [binary archives](#binary-archives).</span></span>

<span data-ttu-id="b4f05-116">Installieren Sie nach der Installation von PowerShell [OpenSSL](#installing-dependencies).</span><span class="sxs-lookup"><span data-stu-id="b4f05-116">After installing PowerShell, you should install [OpenSSL](#installing-dependencies).</span></span> <span data-ttu-id="b4f05-117">OpenSSL ist für PowerShell-Remotingfunktionen und CIM-Vorgänge erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b4f05-117">OpenSSL is needed for PowerShell remoting and CIM operations.</span></span>

## <a name="installation-of-latest-stable-release-via-homebrew-on-macos-1013-or-higher"></a><span data-ttu-id="b4f05-118">Installation des neuesten stabilen Releases über Homebrew unter macOS 10.13 oder höher</span><span class="sxs-lookup"><span data-stu-id="b4f05-118">Installation of latest stable release via Homebrew on macOS 10.13 or higher</span></span>

<span data-ttu-id="b4f05-119">Wenn der Befehl `brew` nicht gefunden wird, müssen Sie Homebrew installieren, indem Sie [die entsprechenden Anweisungen][brew] ausführen.</span><span class="sxs-lookup"><span data-stu-id="b4f05-119">If the `brew` command is not found, you need to install Homebrew following [their instructions][brew].</span></span>

<span data-ttu-id="b4f05-120">Jetzt können Sie PowerShell installieren:</span><span class="sxs-lookup"><span data-stu-id="b4f05-120">Now, you can install PowerShell:</span></span>

```sh
brew install --cask powershell
```

<span data-ttu-id="b4f05-121">Vergewissern Sie sich abschließend, dass Ihre Installation voll funktionsfähig ist:</span><span class="sxs-lookup"><span data-stu-id="b4f05-121">Finally, verify that your install is working properly:</span></span>

```sh
pwsh
```

<span data-ttu-id="b4f05-122">Wenn neue Versionen von PowerShell veröffentlicht werden, aktualisieren Sie die Formeln für Homebrew, und führen Sie ein Upgrade für PowerShell aus:</span><span class="sxs-lookup"><span data-stu-id="b4f05-122">When new versions of PowerShell are released, update Homebrew's formulae and upgrade PowerShell:</span></span>

```sh
brew update
brew upgrade powershell --cask
```

> [!NOTE]
> <span data-ttu-id="b4f05-123">Die oben genannten Befehle können innerhalb eines PowerShell-Hosts (pwsh) aufgerufen werden. Allerdings muss dann die Shell von PowerShell beendet und neu gestartet werden, um das Upgrade abzuschließen und die in `$PSVersionTable` dargestellten Werte zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="b4f05-123">The commands above can be called from within a PowerShell (pwsh) host, but then the PowerShell shell must be exited and restarted to complete the upgrade and refresh the values shown in `$PSVersionTable`.</span></span>

[brew]: https://brew.sh/

## <a name="installation-of-latest-preview-release-via-homebrew-on-macos-1013-or-higher"></a><span data-ttu-id="b4f05-124">Installation der neuesten Vorschauversion über Homebrew unter macOS 10.13 oder höher</span><span class="sxs-lookup"><span data-stu-id="b4f05-124">Installation of latest preview release via Homebrew on macOS 10.13 or higher</span></span>

<span data-ttu-id="b4f05-125">Nachdem Sie Homebrew installiert haben, können Sie PowerShell installieren.</span><span class="sxs-lookup"><span data-stu-id="b4f05-125">After you've installed Homebrew, you can install PowerShell.</span></span> <span data-ttu-id="b4f05-126">Installieren Sie zunächst das Paket [Cask-Versions][cask-versions]. Dies ermöglicht Ihnen das Installieren alternativer Versionen von Cask-Paketen:</span><span class="sxs-lookup"><span data-stu-id="b4f05-126">First, install the [Cask-Versions][cask-versions] package that lets you install alternative versions of cask packages:</span></span>

```sh
brew tap homebrew/cask-versions
```

<span data-ttu-id="b4f05-127">Jetzt können Sie PowerShell installieren:</span><span class="sxs-lookup"><span data-stu-id="b4f05-127">Now, you can install PowerShell:</span></span>

```sh
brew install --cask powershell-preview
```

<span data-ttu-id="b4f05-128">Vergewissern Sie sich abschließend, dass Ihre Installation voll funktionsfähig ist:</span><span class="sxs-lookup"><span data-stu-id="b4f05-128">Finally, verify that your install is working properly:</span></span>

```sh
pwsh-preview
```

<span data-ttu-id="b4f05-129">Wenn neue Versionen von PowerShell veröffentlicht werden, aktualisieren Sie die Formeln für Homebrew, und führen Sie ein Upgrade für PowerShell aus:</span><span class="sxs-lookup"><span data-stu-id="b4f05-129">When new versions of PowerShell are released, update Homebrew's formulae and upgrade PowerShell:</span></span>

```sh
brew update
brew upgrade powershell-preview --cask
```

> [!NOTE]
> <span data-ttu-id="b4f05-130">Die oben genannten Befehle können innerhalb eines PowerShell-Hosts (pwsh) aufgerufen werden, die Shell von PowerShell muss dann jedoch beendet und neu angegeben werden, um das Upgrade abzuschließen</span><span class="sxs-lookup"><span data-stu-id="b4f05-130">The commands above can be called from within a PowerShell (pwsh) host, but then the PowerShell shell must be exited and restarted to complete the upgrade.</span></span>
> <span data-ttu-id="b4f05-131">und die in `$PSVersionTable` dargestellten Werte zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="b4f05-131">and refresh the values shown in `$PSVersionTable`.</span></span>

<span data-ttu-id="b4f05-132">Die Installation von PowerShell über die TAP-Methode Homebrew wird auch für stabile und LTS-Versionen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b4f05-132">Installing PowerShell using the Homebrew tap method is also supported for stable and LTS versions.</span></span>

```sh
brew install powershell/tap/powershell
```

<span data-ttu-id="b4f05-133">Überprüfen Sie nun die Installation.</span><span class="sxs-lookup"><span data-stu-id="b4f05-133">You can now verify your install</span></span>

```sh
pwsh
```

<span data-ttu-id="b4f05-134">Wurden bereits neue Versionen von PowerShell veröffentlicht, führen Sie einfach den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="b4f05-134">When new versions of PowerShell are released, simply run the following command.</span></span>

```sh
brew upgrade powershell
```

> [!NOTE]
> <span data-ttu-id="b4f05-135">Verwenden Sie bei einem Update auf eine neuere PowerShell-Version dieselbe Methode (CASK oder TAP), die Sie bei der Erstinstallation von PowerShell verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="b4f05-135">Whether you use the cask or the tap method, when updating to a newer version of PowerShell, use the same method you used to initially install PowerShell.</span></span> <span data-ttu-id="b4f05-136">Andernfalls wird beim Öffnen einer neuen pwsh-Sitzung weiterhin die ältere Version von PowerShell verwendet.</span><span class="sxs-lookup"><span data-stu-id="b4f05-136">If you use a different method, opening a new pwsh session will continue to use the older version of PowerShell.</span></span>
>
> <span data-ttu-id="b4f05-137">Wenn Sie sich dennoch für unterschiedliche Methoden entscheiden, können Sie das Problem mithilfe der [LINK-Methode von Homebrew](https://docs.brew.sh/Manpage#link-ln-options-formula) beheben.</span><span class="sxs-lookup"><span data-stu-id="b4f05-137">If you do decide to use different methods, there are ways to correct the issue using the [Homebrew link method](https://docs.brew.sh/Manpage#link-ln-options-formula).</span></span>

## <a name="installation-via-direct-download"></a><span data-ttu-id="b4f05-138">Installation über einen direkten Download</span><span class="sxs-lookup"><span data-stu-id="b4f05-138">Installation via Direct Download</span></span>

<span data-ttu-id="b4f05-139">Laden Sie das PKG-Paket `powershell-7.1.0-osx-x64.pkg` über die Seite [Releases][] auf den macOS-Computer herunter.</span><span class="sxs-lookup"><span data-stu-id="b4f05-139">Download the PKG package `powershell-7.1.0-osx-x64.pkg` from the [releases][] page onto your macOS machine.</span></span>

<span data-ttu-id="b4f05-140">Doppelklicken Sie entweder auf die Datei, und befolgen Sie die Anweisungen, oder installieren Sie das Paket über das Terminal:</span><span class="sxs-lookup"><span data-stu-id="b4f05-140">You can double-click the file and follow the prompts, or install it from the terminal:</span></span>

```sh
sudo installer -pkg powershell-7.1.0-osx-x64.pkg -target /
```

<span data-ttu-id="b4f05-141">Installieren Sie [OpenSSL](#installing-dependencies).</span><span class="sxs-lookup"><span data-stu-id="b4f05-141">Install [OpenSSL](#installing-dependencies).</span></span> <span data-ttu-id="b4f05-142">OpenSSL ist für PowerShell-Remotingfunktionen und CIM-Vorgänge erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b4f05-142">OpenSSL is needed for PowerShell remoting and CIM operations.</span></span>

## <a name="install-as-a-net-global-tool"></a><span data-ttu-id="b4f05-143">Installieren als globales .NET-Tool</span><span class="sxs-lookup"><span data-stu-id="b4f05-143">Install as a .NET Global tool</span></span>

<span data-ttu-id="b4f05-144">Wenn Sie das [.NET Core SDK](/dotnet/core/sdk) bereits installiert haben, können Sie PowerShell einfach als [globales .NET-Tool](/dotnet/core/tools/global-tools) installieren.</span><span class="sxs-lookup"><span data-stu-id="b4f05-144">If you already have the [.NET Core SDK](/dotnet/core/sdk) installed, it's easy to install PowerShell as a [.NET Global tool](/dotnet/core/tools/global-tools).</span></span>

```
dotnet tool install --global PowerShell
```

<span data-ttu-id="b4f05-145">Der .NET-Toolinstaller fügt `~/.dotnet/tools` Ihrer `PATH`-Umgebungsvariablen hinzu.</span><span class="sxs-lookup"><span data-stu-id="b4f05-145">The dotnet tool installer adds `~/.dotnet/tools` to your `PATH` environment variable.</span></span> <span data-ttu-id="b4f05-146">Die aktuell ausgeführte Shell verfügt jedoch nicht über den aktualisierten `PATH`.</span><span class="sxs-lookup"><span data-stu-id="b4f05-146">However, the currently running shell does not have the updated `PATH`.</span></span> <span data-ttu-id="b4f05-147">Sie sollten PowerShell über eine neue Shell starten können, indem Sie `pwsh` eingeben.</span><span class="sxs-lookup"><span data-stu-id="b4f05-147">You should be able to start PowerShell from a new shell by typing `pwsh`.</span></span>

<span data-ttu-id="b4f05-148">Installieren Sie [OpenSSL](#installing-dependencies).</span><span class="sxs-lookup"><span data-stu-id="b4f05-148">Install [OpenSSL](#installing-dependencies).</span></span> <span data-ttu-id="b4f05-149">OpenSSL ist für PowerShell-Remotingfunktionen und CIM-Vorgänge erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b4f05-149">OpenSSL is needed for PowerShell remoting and CIM operations.</span></span>

## <a name="binary-archives"></a><span data-ttu-id="b4f05-150">Archive der Binärdateien</span><span class="sxs-lookup"><span data-stu-id="b4f05-150">Binary Archives</span></span>

<span data-ttu-id="b4f05-151">`tar.gz`-Archive der PowerShell-Binärdateien werden für die macOS-Plattform zur Verfügung gestellt, um erweiterte Bereitstellungsszenarios zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="b4f05-151">PowerShell binary `tar.gz` archives are provided for the macOS platform to enable advanced deployment scenarios.</span></span> <span data-ttu-id="b4f05-152">Wenn Sie die Installation mit dieser Methode durchführen, müssen Sie auch alle Abhängigkeiten manuell installieren.</span><span class="sxs-lookup"><span data-stu-id="b4f05-152">When you install using this method you must also manually install any dependencies.</span></span>

<span data-ttu-id="b4f05-153">Installieren Sie [OpenSSL](#installing-dependencies).</span><span class="sxs-lookup"><span data-stu-id="b4f05-153">Install [OpenSSL](#installing-dependencies).</span></span> <span data-ttu-id="b4f05-154">OpenSSL ist für PowerShell-Remotingfunktionen und CIM-Vorgänge erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b4f05-154">OpenSSL is needed for PowerShell remoting and CIM operations.</span></span>

### <a name="installing-binary-archives-on-macos"></a><span data-ttu-id="b4f05-155">Installieren von Archiven der Binärdateien unter macOS</span><span class="sxs-lookup"><span data-stu-id="b4f05-155">Installing binary archives on macOS</span></span>

```sh
# Download the powershell '.tar.gz' archive
curl -L -o /tmp/powershell.tar.gz https://github.com/PowerShell/PowerShell/releases/download/v7.1.0/powershell-7.1.0-osx-x64.tar.gz

# Create the target folder where powershell will be placed
sudo mkdir -p /usr/local/microsoft/powershell/7.1.0

# Expand powershell to the target folder
sudo tar zxf /tmp/powershell.tar.gz -C /usr/local/microsoft/powershell/7.1.0

# Set execute permissions
sudo chmod +x /usr/local/microsoft/powershell/7.1.0/pwsh

# Create the symbolic link that points to pwsh
sudo ln -s /usr/local/microsoft/powershell/7.1.0/pwsh /usr/local/bin/pwsh
```

## <a name="installing-dependencies"></a><span data-ttu-id="b4f05-156">Installieren von Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="b4f05-156">Installing dependencies</span></span>

<span data-ttu-id="b4f05-157">Für PowerShell-Remoting und CIM-Vorgänge ist OpenSSL erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b4f05-157">OpenSSL is required for PowerShell remoting and CIM operations.</span></span> <span data-ttu-id="b4f05-158">Bei Bedarf können Sie OpenSSL über MacPorts installieren.</span><span class="sxs-lookup"><span data-stu-id="b4f05-158">You can install OpenSSL via MacPorts if needed.</span></span>

> [!NOTE]
> <span data-ttu-id="b4f05-159">Werden MacPorts und Homebrew im selben System verwendet, können Probleme auftreten.</span><span class="sxs-lookup"><span data-stu-id="b4f05-159">MacPorts and Homebrew can have problems when used to together on the same system.</span></span> <span data-ttu-id="b4f05-160">Homebrew verfügt jedoch über kein Paket für OpenSSL 1.0.</span><span class="sxs-lookup"><span data-stu-id="b4f05-160">However, Homebrew does not have a package for OpenSSL 1.0.</span></span> <span data-ttu-id="b4f05-161">Weitere Informationen finden Sie in den [Häufig gestellten Fragen zu MacPorts](https://trac.macports.org/wiki/FAQ).</span><span class="sxs-lookup"><span data-stu-id="b4f05-161">For more information, see the [MacPorts FAQ](https://trac.macports.org/wiki/FAQ).</span></span>

1. <span data-ttu-id="b4f05-162">Installieren Sie die Xcode-Befehlszeilentools.</span><span class="sxs-lookup"><span data-stu-id="b4f05-162">Install the Xcode command-line tools.</span></span> <span data-ttu-id="b4f05-163">Diese sind für MacPorts erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b4f05-163">The Xcode tools are required by MacPorts.</span></span>

   ```sh
   xcode-select --install
   ```

1. <span data-ttu-id="b4f05-164">Installieren Sie MacPorts.</span><span class="sxs-lookup"><span data-stu-id="b4f05-164">Install MacPorts.</span></span> <span data-ttu-id="b4f05-165">Wenn Sie Anleitungen dazu benötigen, lesen Sie das [Installationshandbuch](https://www.macports.org/install.php).</span><span class="sxs-lookup"><span data-stu-id="b4f05-165">If you need instructions, refer to the [installation guide](https://www.macports.org/install.php).</span></span>
1. <span data-ttu-id="b4f05-166">Aktualisieren Sie MacPorts durch Ausführen von `sudo port selfupdate`.</span><span class="sxs-lookup"><span data-stu-id="b4f05-166">Update MacPorts by running `sudo port selfupdate`.</span></span>
1. <span data-ttu-id="b4f05-167">Führen Sie eine Upgrade von MacPorts-Paketen durch Ausführen von `sudo port upgrade outdated` durch.</span><span class="sxs-lookup"><span data-stu-id="b4f05-167">Upgrade MacPorts packages by running `sudo port upgrade outdated`.</span></span>
1. <span data-ttu-id="b4f05-168">Installieren Sie OpenSSL durch Ausführen von `sudo port install openssl10`.</span><span class="sxs-lookup"><span data-stu-id="b4f05-168">Install OpenSSL by running `sudo port install openssl10`.</span></span>
1. <span data-ttu-id="b4f05-169">Verknüpfen Sie die Bibliotheken, um sie PowerShell zur Verfügung zu stellen:</span><span class="sxs-lookup"><span data-stu-id="b4f05-169">Link the libraries to make them available to PowerShell:</span></span>

   ```sh
   sudo mkdir -p /usr/local/opt/openssl
   sudo ln -s /opt/local/lib/openssl-1.0 /usr/local/opt/openssl/lib
   ```

## <a name="uninstalling-powershell"></a><span data-ttu-id="b4f05-170">Deinstallieren von PowerShell</span><span class="sxs-lookup"><span data-stu-id="b4f05-170">Uninstalling PowerShell</span></span>

<span data-ttu-id="b4f05-171">Wenn Sie PowerShell mit Homebrew installiert haben, verwenden Sie den folgenden Befehl zum Deinstallieren:</span><span class="sxs-lookup"><span data-stu-id="b4f05-171">If you installed PowerShell with Homebrew, use the following command to uninstall:</span></span>

```sh
brew cask uninstall powershell
```

<span data-ttu-id="b4f05-172">Wenn Sie PowerShell über einen direkten Download installiert haben, muss PowerShell manuell entfernt werden:</span><span class="sxs-lookup"><span data-stu-id="b4f05-172">If you installed PowerShell via direct download, PowerShell must be removed manually:</span></span>

```sh
sudo rm -rf /usr/local/bin/pwsh /usr/local/microsoft/powershell
```

<span data-ttu-id="b4f05-173">Lesen Sie den Abschnitt [Pfade](#paths) in diesem Artikel, um zu erfahren, wie Sie zusätzliche PowerShell-Pfade deinstallieren können. Entfernen Sie die Pfade mithilfe von `sudo rm`.</span><span class="sxs-lookup"><span data-stu-id="b4f05-173">To remove the additional PowerShell paths, refer to the [paths](#paths) section in this document and remove the paths using `sudo rm`.</span></span>

> [!NOTE]
> <span data-ttu-id="b4f05-174">Dies ist nicht notwendig, wenn Sie eine Installation mit Homebrew durchgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="b4f05-174">This is not necessary if you installed with Homebrew.</span></span>

## <a name="paths"></a><span data-ttu-id="b4f05-175">Paths</span><span class="sxs-lookup"><span data-stu-id="b4f05-175">Paths</span></span>

- <span data-ttu-id="b4f05-176">`$PSHOME` ist `/usr/local/microsoft/powershell/7.1.0/`.</span><span class="sxs-lookup"><span data-stu-id="b4f05-176">`$PSHOME` is `/usr/local/microsoft/powershell/7.1.0/`</span></span>
- <span data-ttu-id="b4f05-177">Benutzerprofile werden über `~/.config/powershell/profile.ps1` gelesen.</span><span class="sxs-lookup"><span data-stu-id="b4f05-177">User profiles will be read from `~/.config/powershell/profile.ps1`</span></span>
- <span data-ttu-id="b4f05-178">Standardprofile werden über `$PSHOME/profile.ps1` gelesen.</span><span class="sxs-lookup"><span data-stu-id="b4f05-178">Default profiles will be read from `$PSHOME/profile.ps1`</span></span>
- <span data-ttu-id="b4f05-179">Benutzermodule werden über `~/.local/share/powershell/Modules` gelesen.</span><span class="sxs-lookup"><span data-stu-id="b4f05-179">User modules will be read from `~/.local/share/powershell/Modules`</span></span>
- <span data-ttu-id="b4f05-180">Freigegebene Module werden über `/usr/local/share/powershell/Modules` gelesen.</span><span class="sxs-lookup"><span data-stu-id="b4f05-180">Shared modules will be read from `/usr/local/share/powershell/Modules`</span></span>
- <span data-ttu-id="b4f05-181">Standardmodule werden über `$PSHOME/Modules` gelesen.</span><span class="sxs-lookup"><span data-stu-id="b4f05-181">Default modules will be read from `$PSHOME/Modules`</span></span>
- <span data-ttu-id="b4f05-182">Der Verlauf von „PSReadline“ wird in `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt` aufgezeichnet.</span><span class="sxs-lookup"><span data-stu-id="b4f05-182">PSReadline history will be recorded to `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt`</span></span>

<span data-ttu-id="b4f05-183">Die Profile halten sich an die Konfiguration von PowerShell pro Host.</span><span class="sxs-lookup"><span data-stu-id="b4f05-183">The profiles respect PowerShell's per-host configuration.</span></span> <span data-ttu-id="b4f05-184">Dies bedeutet, dass hostspezifische Standardprofile in `Microsoft.PowerShell_profile.ps1` am gleichen Speicherort vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="b4f05-184">So the default host-specific profile exists at `Microsoft.PowerShell_profile.ps1` in the same locations.</span></span>

<span data-ttu-id="b4f05-185">PowerShell hält die [XDG Base Directory Specification (XDG Base Directory-Spezifikation)][xdg-bds] unter macOs ein.</span><span class="sxs-lookup"><span data-stu-id="b4f05-185">PowerShell respects the [XDG Base Directory Specification][xdg-bds] on macOS.</span></span>

<span data-ttu-id="b4f05-186">Da macOS eine Ableitung von BSD ist, wird das Präfix `/usr/local` anstelle von `/opt` verwendet.</span><span class="sxs-lookup"><span data-stu-id="b4f05-186">Because macOS is a derivation of BSD, the prefix `/usr/local` is used instead of `/opt`.</span></span> <span data-ttu-id="b4f05-187">Daher ist `$PSHOME` gleich `/usr/local/microsoft/powershell/7.1.0/`, und der symbolische Link wird unter `/usr/local/bin/pwsh` gespeichert.</span><span class="sxs-lookup"><span data-stu-id="b4f05-187">So, `$PSHOME` is `/usr/local/microsoft/powershell/7.1.0/`, and the symbolic link is placed at `/usr/local/bin/pwsh`.</span></span>

## <a name="installation-support"></a><span data-ttu-id="b4f05-188">Installationsunterstützung</span><span class="sxs-lookup"><span data-stu-id="b4f05-188">Installation support</span></span>

<span data-ttu-id="b4f05-189">Microsoft unterstützt die in diesem Dokument beschriebenen Installationsmethoden.</span><span class="sxs-lookup"><span data-stu-id="b4f05-189">Microsoft supports the installation methods in this document.</span></span> <span data-ttu-id="b4f05-190">Möglicherweise stehen andere Installationsmethoden aus anderen Quellen zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="b4f05-190">There may be other methods of installation available from other sources.</span></span> <span data-ttu-id="b4f05-191">Auch wenn diese Tools und Methoden funktionieren, kann Microsoft sie nicht unterstützen.</span><span class="sxs-lookup"><span data-stu-id="b4f05-191">While those tools and methods may work, Microsoft cannot support those methods.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b4f05-192">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="b4f05-192">Additional Resources</span></span>

- <span data-ttu-id="b4f05-193">[Homebrew-Website][brew]</span><span class="sxs-lookup"><span data-stu-id="b4f05-193">[Homebrew Web][brew]</span></span>
- <span data-ttu-id="b4f05-194">[Homebrew-GitHub-Repository][GitHub]</span><span class="sxs-lookup"><span data-stu-id="b4f05-194">[Homebrew Github Repository][GitHub]</span></span>
- <span data-ttu-id="b4f05-195">[Homebrew-Cask][cask]</span><span class="sxs-lookup"><span data-stu-id="b4f05-195">[Homebrew-Cask][cask]</span></span>

[brew]: http://brew.sh/
[Cask]: https://github.com/Homebrew/homebrew-cask
[cask-versions]: https://github.com/Homebrew/homebrew-cask-versions
[GitHub]: https://github.com/Homebrew
[Freigaben]: https://github.com/PowerShell/PowerShell/releases/latest
[releases]: https://github.com/PowerShell/PowerShell/releases/latest
[xdg-bds]: https://specifications.freedesktop.org/basedir-spec/basedir-spec-latest.html
