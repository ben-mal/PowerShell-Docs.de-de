---
title: Installieren von PowerShell unter macOS
description: Informationen zur Installation von PowerShell unter macOS
ms.date: 03/15/2021
ms.openlocfilehash: e69a757e761039799fe399c0e59c31c800a5094a
ms.sourcegitcommit: 080c8b05a1242348c365fe1684457e873325f11e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2021
ms.locfileid: "103483454"
---
# <a name="installing-powershell-on-macos"></a><span data-ttu-id="40b57-103">Installieren von PowerShell unter macOS</span><span class="sxs-lookup"><span data-stu-id="40b57-103">Installing PowerShell on macOS</span></span>

<span data-ttu-id="40b57-104">Ab PowerShell 7.0 ist mindestens macOS 10.13 erforderlich.</span><span class="sxs-lookup"><span data-stu-id="40b57-104">PowerShell 7.0 or higher require macOS 10.13 and higher.</span></span> <span data-ttu-id="40b57-105">Sämtliche Pakete sind auf der Seite [Freigaben][] über GitHub verfügbar.</span><span class="sxs-lookup"><span data-stu-id="40b57-105">All packages are available on our GitHub [releases][] page.</span></span> <span data-ttu-id="40b57-106">Nachdem Sie das Paket installiert haben, führen Sie `pwsh` über das Terminal aus.</span><span class="sxs-lookup"><span data-stu-id="40b57-106">After the package is installed, run `pwsh` from a terminal.</span></span>

> [!NOTE]
> <span data-ttu-id="40b57-107">PowerShell 7.1 ist ein direktes Upgrade, das PowerShell Core 6.x und 7.0 ersetzt.</span><span class="sxs-lookup"><span data-stu-id="40b57-107">PowerShell 7.1 is an in-place upgrade that removes PowerShell Core 6.x and 7.0.</span></span>
>
> <span data-ttu-id="40b57-108">Der Ordner `/usr/local/microsoft/powershell/6` wird durch `/usr/local/microsoft/powershell/7` ersetzt.</span><span class="sxs-lookup"><span data-stu-id="40b57-108">The `/usr/local/microsoft/powershell/6` folder is replaced by `/usr/local/microsoft/powershell/7`.</span></span>
>
> <span data-ttu-id="40b57-109">Wenn Sie eine ältere Version von PowerShell Core parallel zu PowerShell 7.1 ausführen möchten, installieren Sie die gewünschte Version mithilfe der Methode unter [Archive der Binärdateien](#binary-archives).</span><span class="sxs-lookup"><span data-stu-id="40b57-109">If you need to run and older version of PowerShell core side-by-side with PowerShell 7.1, install the version you want using the [binary archive](#binary-archives) method.</span></span>

<span data-ttu-id="40b57-110">Es gibt mehrere Möglichkeiten, PowerShell unter macOS zu installieren.</span><span class="sxs-lookup"><span data-stu-id="40b57-110">There are several ways to install PowerShell on macOS.</span></span> <span data-ttu-id="40b57-111">Wählen Sie eine der folgenden Methoden:</span><span class="sxs-lookup"><span data-stu-id="40b57-111">Choose one of the following methods:</span></span>

- <span data-ttu-id="40b57-112">Verwenden Sie für die Installation Homebrew.</span><span class="sxs-lookup"><span data-stu-id="40b57-112">Install using Homebrew.</span></span> <span data-ttu-id="40b57-113">Bei Homebrew handelt es sich um den bevorzugten Paket-Manager für macOS.</span><span class="sxs-lookup"><span data-stu-id="40b57-113">Homebrew is the preferred package manager for macOS.</span></span>
- <span data-ttu-id="40b57-114">Installieren Sie PowerShell über einen [direkten Download](#installation-via-direct-download).</span><span class="sxs-lookup"><span data-stu-id="40b57-114">Install PowerShell via [Direct Download](#installation-via-direct-download)</span></span>
- <span data-ttu-id="40b57-115">Führen Sie die Installation über [Archive der Binärdateien](#binary-archives) aus.</span><span class="sxs-lookup"><span data-stu-id="40b57-115">Install from [binary archives](#binary-archives).</span></span>

<span data-ttu-id="40b57-116">Installieren Sie nach der Installation von PowerShell [OpenSSL](#installing-dependencies).</span><span class="sxs-lookup"><span data-stu-id="40b57-116">After installing PowerShell, you should install [OpenSSL](#installing-dependencies).</span></span> <span data-ttu-id="40b57-117">OpenSSL ist für PowerShell-Remotingfunktionen und CIM-Vorgänge erforderlich.</span><span class="sxs-lookup"><span data-stu-id="40b57-117">OpenSSL is needed for PowerShell remoting and CIM operations.</span></span>

## <a name="installation-of-latest-stable-release-via-homebrew-on-macos-1013-or-higher"></a><span data-ttu-id="40b57-118">Installation des neuesten stabilen Releases über Homebrew unter macOS 10.13 oder höher</span><span class="sxs-lookup"><span data-stu-id="40b57-118">Installation of latest stable release via Homebrew on macOS 10.13 or higher</span></span>

<span data-ttu-id="40b57-119">Wenn der Befehl `brew` nicht gefunden wird, müssen Sie Homebrew installieren, indem Sie [die entsprechenden Anweisungen][brew] ausführen.</span><span class="sxs-lookup"><span data-stu-id="40b57-119">If the `brew` command is not found, you need to install Homebrew following [their instructions][brew].</span></span>

<span data-ttu-id="40b57-120">Jetzt können Sie PowerShell installieren:</span><span class="sxs-lookup"><span data-stu-id="40b57-120">Now, you can install PowerShell:</span></span>

```sh
brew install --cask powershell
```

<span data-ttu-id="40b57-121">Vergewissern Sie sich abschließend, dass Ihre Installation voll funktionsfähig ist:</span><span class="sxs-lookup"><span data-stu-id="40b57-121">Finally, verify that your install is working properly:</span></span>

```sh
pwsh
```

<span data-ttu-id="40b57-122">Wenn neue Versionen von PowerShell veröffentlicht werden, aktualisieren Sie die Formeln für Homebrew, und führen Sie ein Upgrade für PowerShell aus:</span><span class="sxs-lookup"><span data-stu-id="40b57-122">When new versions of PowerShell are released, update Homebrew's formulae and upgrade PowerShell:</span></span>

```sh
brew update
brew upgrade powershell --cask
```

> [!NOTE]
> <span data-ttu-id="40b57-123">Die oben genannten Befehle können innerhalb eines PowerShell-Hosts (pwsh) aufgerufen werden. Allerdings muss dann die Shell von PowerShell beendet und neu gestartet werden, um das Upgrade abzuschließen und die in `$PSVersionTable` dargestellten Werte zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="40b57-123">The commands above can be called from within a PowerShell (pwsh) host, but then the PowerShell shell must be exited and restarted to complete the upgrade and refresh the values shown in `$PSVersionTable`.</span></span>

[brew]: https://brew.sh/

## <a name="installation-of-latest-preview-release-via-homebrew-on-macos-1013-or-higher"></a><span data-ttu-id="40b57-124">Installation der neuesten Vorschauversion über Homebrew unter macOS 10.13 oder höher</span><span class="sxs-lookup"><span data-stu-id="40b57-124">Installation of latest preview release via Homebrew on macOS 10.13 or higher</span></span>

<span data-ttu-id="40b57-125">Nachdem Sie Homebrew installiert haben, können Sie PowerShell installieren.</span><span class="sxs-lookup"><span data-stu-id="40b57-125">After you've installed Homebrew, you can install PowerShell.</span></span> <span data-ttu-id="40b57-126">Installieren Sie zunächst das Paket [Cask-Versions][cask-versions]. Dies ermöglicht Ihnen das Installieren alternativer Versionen von Cask-Paketen:</span><span class="sxs-lookup"><span data-stu-id="40b57-126">First, install the [Cask-Versions][cask-versions] package that lets you install alternative versions of cask packages:</span></span>

```sh
brew tap homebrew/cask-versions
```

<span data-ttu-id="40b57-127">Jetzt können Sie PowerShell installieren:</span><span class="sxs-lookup"><span data-stu-id="40b57-127">Now, you can install PowerShell:</span></span>

```sh
brew install --cask powershell-preview
```

<span data-ttu-id="40b57-128">Vergewissern Sie sich abschließend, dass Ihre Installation voll funktionsfähig ist:</span><span class="sxs-lookup"><span data-stu-id="40b57-128">Finally, verify that your install is working properly:</span></span>

```sh
pwsh-preview
```

<span data-ttu-id="40b57-129">Wenn neue Versionen von PowerShell veröffentlicht werden, aktualisieren Sie die Formeln für Homebrew, und führen Sie ein Upgrade für PowerShell aus:</span><span class="sxs-lookup"><span data-stu-id="40b57-129">When new versions of PowerShell are released, update Homebrew's formulae and upgrade PowerShell:</span></span>

```sh
brew update
brew upgrade powershell-preview --cask
```

> [!NOTE]
> <span data-ttu-id="40b57-130">Die oben genannten Befehle können innerhalb eines PowerShell-Hosts (pwsh) aufgerufen werden, die Shell von PowerShell muss dann jedoch beendet und neu angegeben werden, um das Upgrade abzuschließen</span><span class="sxs-lookup"><span data-stu-id="40b57-130">The commands above can be called from within a PowerShell (pwsh) host, but then the PowerShell shell must be exited and restarted to complete the upgrade.</span></span>
> <span data-ttu-id="40b57-131">und die in `$PSVersionTable` dargestellten Werte zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="40b57-131">and refresh the values shown in `$PSVersionTable`.</span></span>

<span data-ttu-id="40b57-132">Die Installation von PowerShell über die TAP-Methode Homebrew wird auch für stabile und LTS-Versionen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="40b57-132">Installing PowerShell using the Homebrew tap method is also supported for stable and LTS versions.</span></span>

```sh
brew install powershell/tap/powershell
```

<span data-ttu-id="40b57-133">Überprüfen Sie nun die Installation.</span><span class="sxs-lookup"><span data-stu-id="40b57-133">You can now verify your install</span></span>

```sh
pwsh
```

<span data-ttu-id="40b57-134">Wurden bereits neue Versionen von PowerShell veröffentlicht, führen Sie einfach den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="40b57-134">When new versions of PowerShell are released, simply run the following command.</span></span>

```sh
brew upgrade powershell
```

> [!NOTE]
> <span data-ttu-id="40b57-135">Verwenden Sie bei einem Update auf eine neuere PowerShell-Version dieselbe Methode (CASK oder TAP), die Sie bei der Erstinstallation von PowerShell verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="40b57-135">Whether you use the cask or the tap method, when updating to a newer version of PowerShell, use the same method you used to initially install PowerShell.</span></span> <span data-ttu-id="40b57-136">Andernfalls wird beim Öffnen einer neuen pwsh-Sitzung weiterhin die ältere Version von PowerShell verwendet.</span><span class="sxs-lookup"><span data-stu-id="40b57-136">If you use a different method, opening a new pwsh session will continue to use the older version of PowerShell.</span></span>
>
> <span data-ttu-id="40b57-137">Wenn Sie sich dennoch für unterschiedliche Methoden entscheiden, können Sie das Problem mithilfe der [LINK-Methode von Homebrew](https://docs.brew.sh/Manpage#link-ln-options-formula) beheben.</span><span class="sxs-lookup"><span data-stu-id="40b57-137">If you do decide to use different methods, there are ways to correct the issue using the [Homebrew link method](https://docs.brew.sh/Manpage#link-ln-options-formula).</span></span>

## <a name="installation-via-direct-download"></a><span data-ttu-id="40b57-138">Installation über einen direkten Download</span><span class="sxs-lookup"><span data-stu-id="40b57-138">Installation via Direct Download</span></span>

<span data-ttu-id="40b57-139">Laden Sie das PKG-Paket `powershell-7.1.3-osx-x64.pkg` über die Seite [Releases][] auf den macOS-Computer herunter.</span><span class="sxs-lookup"><span data-stu-id="40b57-139">Download the PKG package `powershell-7.1.3-osx-x64.pkg` from the [releases][] page onto your macOS machine.</span></span>

<span data-ttu-id="40b57-140">Doppelklicken Sie entweder auf die Datei, und befolgen Sie die Anweisungen, oder installieren Sie das Paket über das Terminal:</span><span class="sxs-lookup"><span data-stu-id="40b57-140">You can double-click the file and follow the prompts, or install it from the terminal:</span></span>

```sh
sudo installer -pkg powershell-7.1.3-osx-x64.pkg -target /
```

<span data-ttu-id="40b57-141">Installieren Sie [OpenSSL](#installing-dependencies).</span><span class="sxs-lookup"><span data-stu-id="40b57-141">Install [OpenSSL](#installing-dependencies).</span></span> <span data-ttu-id="40b57-142">OpenSSL ist für PowerShell-Remotingfunktionen und CIM-Vorgänge erforderlich.</span><span class="sxs-lookup"><span data-stu-id="40b57-142">OpenSSL is needed for PowerShell remoting and CIM operations.</span></span>

## <a name="install-as-a-net-global-tool"></a><span data-ttu-id="40b57-143">Installieren als globales .NET-Tool</span><span class="sxs-lookup"><span data-stu-id="40b57-143">Install as a .NET Global tool</span></span>

<span data-ttu-id="40b57-144">Wenn Sie das [.NET Core SDK](/dotnet/core/sdk) bereits installiert haben, können Sie PowerShell einfach als [globales .NET-Tool](/dotnet/core/tools/global-tools) installieren.</span><span class="sxs-lookup"><span data-stu-id="40b57-144">If you already have the [.NET Core SDK](/dotnet/core/sdk) installed, it's easy to install PowerShell as a [.NET Global tool](/dotnet/core/tools/global-tools).</span></span>

```
dotnet tool install --global PowerShell
```

<span data-ttu-id="40b57-145">Der .NET-Toolinstaller fügt `~/.dotnet/tools` Ihrer `PATH`-Umgebungsvariablen hinzu.</span><span class="sxs-lookup"><span data-stu-id="40b57-145">The dotnet tool installer adds `~/.dotnet/tools` to your `PATH` environment variable.</span></span> <span data-ttu-id="40b57-146">Die aktuell ausgeführte Shell verfügt jedoch nicht über den aktualisierten `PATH`.</span><span class="sxs-lookup"><span data-stu-id="40b57-146">However, the currently running shell does not have the updated `PATH`.</span></span> <span data-ttu-id="40b57-147">Sie sollten PowerShell über eine neue Shell starten können, indem Sie `pwsh` eingeben.</span><span class="sxs-lookup"><span data-stu-id="40b57-147">You should be able to start PowerShell from a new shell by typing `pwsh`.</span></span>

<span data-ttu-id="40b57-148">Installieren Sie [OpenSSL](#installing-dependencies).</span><span class="sxs-lookup"><span data-stu-id="40b57-148">Install [OpenSSL](#installing-dependencies).</span></span> <span data-ttu-id="40b57-149">OpenSSL ist für PowerShell-Remotingfunktionen und CIM-Vorgänge erforderlich.</span><span class="sxs-lookup"><span data-stu-id="40b57-149">OpenSSL is needed for PowerShell remoting and CIM operations.</span></span>

## <a name="binary-archives"></a><span data-ttu-id="40b57-150">Archive der Binärdateien</span><span class="sxs-lookup"><span data-stu-id="40b57-150">Binary Archives</span></span>

<span data-ttu-id="40b57-151">`tar.gz`-Archive der PowerShell-Binärdateien werden für die macOS-Plattform zur Verfügung gestellt, um erweiterte Bereitstellungsszenarios zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="40b57-151">PowerShell binary `tar.gz` archives are provided for the macOS platform to enable advanced deployment scenarios.</span></span> <span data-ttu-id="40b57-152">Wenn Sie die Installation mit dieser Methode durchführen, müssen Sie auch alle Abhängigkeiten manuell installieren.</span><span class="sxs-lookup"><span data-stu-id="40b57-152">When you install using this method you must also manually install any dependencies.</span></span>

<span data-ttu-id="40b57-153">Installieren Sie [OpenSSL](#installing-dependencies).</span><span class="sxs-lookup"><span data-stu-id="40b57-153">Install [OpenSSL](#installing-dependencies).</span></span> <span data-ttu-id="40b57-154">OpenSSL ist für PowerShell-Remotingfunktionen und CIM-Vorgänge erforderlich.</span><span class="sxs-lookup"><span data-stu-id="40b57-154">OpenSSL is needed for PowerShell remoting and CIM operations.</span></span>

> [!NOTE]
> <span data-ttu-id="40b57-155">Sie können diese Methode verwenden, um eine beliebige Version von PowerShell zu installieren, einschließlich der neuesten:</span><span class="sxs-lookup"><span data-stu-id="40b57-155">You can use this method to install any version of PowerShell including the latest:</span></span>
> - <span data-ttu-id="40b57-156">Stabiles Release: [https://aka.ms/powershell-release?tag=stable](https://aka.ms/powershell-release?tag=stable)</span><span class="sxs-lookup"><span data-stu-id="40b57-156">Stable release: [https://aka.ms/powershell-release?tag=stable](https://aka.ms/powershell-release?tag=stable)</span></span>
> - <span data-ttu-id="40b57-157">Vorschaurelease: [https://aka.ms/powershell-release?tag=preview](https://aka.ms/powershell-release?tag=preview)</span><span class="sxs-lookup"><span data-stu-id="40b57-157">Preview release: [https://aka.ms/powershell-release?tag=preview](https://aka.ms/powershell-release?tag=preview)</span></span>
> - <span data-ttu-id="40b57-158">LTS-Release: [https://aka.ms/powershell-release?tag=lts](https://aka.ms/powershell-release?tag=lts)</span><span class="sxs-lookup"><span data-stu-id="40b57-158">LTS release: [https://aka.ms/powershell-release?tag=lts](https://aka.ms/powershell-release?tag=lts)</span></span>

### <a name="installing-binary-archives-on-macos"></a><span data-ttu-id="40b57-159">Installieren von Archiven der Binärdateien unter macOS</span><span class="sxs-lookup"><span data-stu-id="40b57-159">Installing binary archives on macOS</span></span>

```sh
# Download the powershell '.tar.gz' archive
curl -L -o /tmp/powershell.tar.gz https://github.com/PowerShell/PowerShell/releases/download/v7.1.3/powershell-7.1.3-osx-x64.tar.gz

# Create the target folder where powershell will be placed
sudo mkdir -p /usr/local/microsoft/powershell/7.1.3

# Expand powershell to the target folder
sudo tar zxf /tmp/powershell.tar.gz -C /usr/local/microsoft/powershell/7.1.3

# Set execute permissions
sudo chmod +x /usr/local/microsoft/powershell/7.1.3/pwsh

# Create the symbolic link that points to pwsh
sudo ln -s /usr/local/microsoft/powershell/7.1.3/pwsh /usr/local/bin/pwsh
```

## <a name="installing-dependencies"></a><span data-ttu-id="40b57-160">Installieren von Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="40b57-160">Installing dependencies</span></span>

<span data-ttu-id="40b57-161">Für PowerShell-Remoting und CIM-Vorgänge ist OpenSSL erforderlich.</span><span class="sxs-lookup"><span data-stu-id="40b57-161">OpenSSL is required for PowerShell remoting and CIM operations.</span></span> <span data-ttu-id="40b57-162">Bei Bedarf können Sie OpenSSL über MacPorts installieren.</span><span class="sxs-lookup"><span data-stu-id="40b57-162">You can install OpenSSL via MacPorts if needed.</span></span>

> [!NOTE]
> <span data-ttu-id="40b57-163">Werden MacPorts und Homebrew im selben System verwendet, können Probleme auftreten.</span><span class="sxs-lookup"><span data-stu-id="40b57-163">MacPorts and Homebrew can have problems when used to together on the same system.</span></span> <span data-ttu-id="40b57-164">Homebrew verfügt jedoch über kein Paket für OpenSSL 1.0.</span><span class="sxs-lookup"><span data-stu-id="40b57-164">However, Homebrew does not have a package for OpenSSL 1.0.</span></span> <span data-ttu-id="40b57-165">Weitere Informationen finden Sie in den [Häufig gestellten Fragen zu MacPorts](https://trac.macports.org/wiki/FAQ).</span><span class="sxs-lookup"><span data-stu-id="40b57-165">For more information, see the [MacPorts FAQ](https://trac.macports.org/wiki/FAQ).</span></span>

1. <span data-ttu-id="40b57-166">Installieren Sie die Xcode-Befehlszeilentools.</span><span class="sxs-lookup"><span data-stu-id="40b57-166">Install the Xcode command-line tools.</span></span> <span data-ttu-id="40b57-167">Diese sind für MacPorts erforderlich.</span><span class="sxs-lookup"><span data-stu-id="40b57-167">The Xcode tools are required by MacPorts.</span></span>

   ```sh
   xcode-select --install
   ```

1. <span data-ttu-id="40b57-168">Installieren Sie MacPorts.</span><span class="sxs-lookup"><span data-stu-id="40b57-168">Install MacPorts.</span></span> <span data-ttu-id="40b57-169">Wenn Sie Anleitungen dazu benötigen, lesen Sie das [Installationshandbuch](https://www.macports.org/install.php).</span><span class="sxs-lookup"><span data-stu-id="40b57-169">If you need instructions, refer to the [installation guide](https://www.macports.org/install.php).</span></span>
1. <span data-ttu-id="40b57-170">Aktualisieren Sie MacPorts durch Ausführen von `sudo port selfupdate`.</span><span class="sxs-lookup"><span data-stu-id="40b57-170">Update MacPorts by running `sudo port selfupdate`.</span></span>
1. <span data-ttu-id="40b57-171">Führen Sie eine Upgrade von MacPorts-Paketen durch Ausführen von `sudo port upgrade outdated` durch.</span><span class="sxs-lookup"><span data-stu-id="40b57-171">Upgrade MacPorts packages by running `sudo port upgrade outdated`.</span></span>
1. <span data-ttu-id="40b57-172">Installieren Sie OpenSSL durch Ausführen von `sudo port install openssl10`.</span><span class="sxs-lookup"><span data-stu-id="40b57-172">Install OpenSSL by running `sudo port install openssl10`.</span></span>
1. <span data-ttu-id="40b57-173">Verknüpfen Sie die Bibliotheken, um sie PowerShell zur Verfügung zu stellen:</span><span class="sxs-lookup"><span data-stu-id="40b57-173">Link the libraries to make them available to PowerShell:</span></span>

   ```sh
   sudo mkdir -p /usr/local/opt/openssl
   sudo ln -s /opt/local/lib/openssl-1.0 /usr/local/opt/openssl/lib
   ```

## <a name="uninstalling-powershell"></a><span data-ttu-id="40b57-174">Deinstallieren von PowerShell</span><span class="sxs-lookup"><span data-stu-id="40b57-174">Uninstalling PowerShell</span></span>

<span data-ttu-id="40b57-175">Wenn Sie PowerShell mit Homebrew installiert haben, verwenden Sie den folgenden Befehl zum Deinstallieren:</span><span class="sxs-lookup"><span data-stu-id="40b57-175">If you installed PowerShell with Homebrew, use the following command to uninstall:</span></span>

```sh
brew cask uninstall powershell
```

<span data-ttu-id="40b57-176">Wenn Sie PowerShell über einen direkten Download installiert haben, muss PowerShell manuell entfernt werden:</span><span class="sxs-lookup"><span data-stu-id="40b57-176">If you installed PowerShell via direct download, PowerShell must be removed manually:</span></span>

```sh
sudo rm -rf /usr/local/bin/pwsh /usr/local/microsoft/powershell
```

<span data-ttu-id="40b57-177">Lesen Sie den Abschnitt [Pfade](#paths) in diesem Artikel, um zu erfahren, wie Sie zusätzliche PowerShell-Pfade deinstallieren können. Entfernen Sie die Pfade mithilfe von `sudo rm`.</span><span class="sxs-lookup"><span data-stu-id="40b57-177">To remove the additional PowerShell paths, refer to the [paths](#paths) section in this document and remove the paths using `sudo rm`.</span></span>

> [!NOTE]
> <span data-ttu-id="40b57-178">Dies ist nicht notwendig, wenn Sie eine Installation mit Homebrew durchgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="40b57-178">This is not necessary if you installed with Homebrew.</span></span>

## <a name="paths"></a><span data-ttu-id="40b57-179">Paths</span><span class="sxs-lookup"><span data-stu-id="40b57-179">Paths</span></span>

- <span data-ttu-id="40b57-180">`$PSHOME` ist `/usr/local/microsoft/powershell/7.1.3/`.</span><span class="sxs-lookup"><span data-stu-id="40b57-180">`$PSHOME` is `/usr/local/microsoft/powershell/7.1.3/`</span></span>
- <span data-ttu-id="40b57-181">Benutzerprofile werden über `~/.config/powershell/profile.ps1` gelesen.</span><span class="sxs-lookup"><span data-stu-id="40b57-181">User profiles will be read from `~/.config/powershell/profile.ps1`</span></span>
- <span data-ttu-id="40b57-182">Standardprofile werden über `$PSHOME/profile.ps1` gelesen.</span><span class="sxs-lookup"><span data-stu-id="40b57-182">Default profiles will be read from `$PSHOME/profile.ps1`</span></span>
- <span data-ttu-id="40b57-183">Benutzermodule werden über `~/.local/share/powershell/Modules` gelesen.</span><span class="sxs-lookup"><span data-stu-id="40b57-183">User modules will be read from `~/.local/share/powershell/Modules`</span></span>
- <span data-ttu-id="40b57-184">Freigegebene Module werden über `/usr/local/share/powershell/Modules` gelesen.</span><span class="sxs-lookup"><span data-stu-id="40b57-184">Shared modules will be read from `/usr/local/share/powershell/Modules`</span></span>
- <span data-ttu-id="40b57-185">Standardmodule werden über `$PSHOME/Modules` gelesen.</span><span class="sxs-lookup"><span data-stu-id="40b57-185">Default modules will be read from `$PSHOME/Modules`</span></span>
- <span data-ttu-id="40b57-186">Der Verlauf von „PSReadline“ wird in `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt` aufgezeichnet.</span><span class="sxs-lookup"><span data-stu-id="40b57-186">PSReadline history will be recorded to `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt`</span></span>

<span data-ttu-id="40b57-187">Die Profile halten sich an die Konfiguration von PowerShell pro Host.</span><span class="sxs-lookup"><span data-stu-id="40b57-187">The profiles respect PowerShell's per-host configuration.</span></span> <span data-ttu-id="40b57-188">Dies bedeutet, dass hostspezifische Standardprofile in `Microsoft.PowerShell_profile.ps1` am gleichen Speicherort vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="40b57-188">So the default host-specific profile exists at `Microsoft.PowerShell_profile.ps1` in the same locations.</span></span>

<span data-ttu-id="40b57-189">PowerShell hält die [XDG Base Directory Specification (XDG Base Directory-Spezifikation)][xdg-bds] unter macOs ein.</span><span class="sxs-lookup"><span data-stu-id="40b57-189">PowerShell respects the [XDG Base Directory Specification][xdg-bds] on macOS.</span></span>

<span data-ttu-id="40b57-190">Da macOS eine Ableitung von BSD ist, wird das Präfix `/usr/local` anstelle von `/opt` verwendet.</span><span class="sxs-lookup"><span data-stu-id="40b57-190">Because macOS is a derivation of BSD, the prefix `/usr/local` is used instead of `/opt`.</span></span> <span data-ttu-id="40b57-191">Daher ist `$PSHOME` gleich `/usr/local/microsoft/powershell/7.1.3/`, und der symbolische Link wird unter `/usr/local/bin/pwsh` gespeichert.</span><span class="sxs-lookup"><span data-stu-id="40b57-191">So, `$PSHOME` is `/usr/local/microsoft/powershell/7.1.3/`, and the symbolic link is placed at `/usr/local/bin/pwsh`.</span></span>

## <a name="installation-support"></a><span data-ttu-id="40b57-192">Installationsunterstützung</span><span class="sxs-lookup"><span data-stu-id="40b57-192">Installation support</span></span>

<span data-ttu-id="40b57-193">Microsoft unterstützt die in diesem Dokument beschriebenen Installationsmethoden.</span><span class="sxs-lookup"><span data-stu-id="40b57-193">Microsoft supports the installation methods in this document.</span></span> <span data-ttu-id="40b57-194">Möglicherweise stehen andere Installationsmethoden aus anderen Quellen zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="40b57-194">There may be other methods of installation available from other sources.</span></span> <span data-ttu-id="40b57-195">Auch wenn diese Tools und Methoden funktionieren, kann Microsoft sie nicht unterstützen.</span><span class="sxs-lookup"><span data-stu-id="40b57-195">While those tools and methods may work, Microsoft cannot support those methods.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="40b57-196">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="40b57-196">Additional Resources</span></span>

- <span data-ttu-id="40b57-197">[Homebrew-Website][brew]</span><span class="sxs-lookup"><span data-stu-id="40b57-197">[Homebrew Web][brew]</span></span>
- <span data-ttu-id="40b57-198">[Homebrew-GitHub-Repository][GitHub]</span><span class="sxs-lookup"><span data-stu-id="40b57-198">[Homebrew Github Repository][GitHub]</span></span>
- <span data-ttu-id="40b57-199">[Homebrew-Cask][cask]</span><span class="sxs-lookup"><span data-stu-id="40b57-199">[Homebrew-Cask][cask]</span></span>

[brew]: http://brew.sh/
[Cask]: https://github.com/Homebrew/homebrew-cask
[cask-versions]: https://github.com/Homebrew/homebrew-cask-versions
[GitHub]: https://github.com/Homebrew
[Freigaben]: https://aka.ms/powershell-release?tag=stable
[releases]: https://aka.ms/powershell-release?tag=stable
[xdg-bds]: https://specifications.freedesktop.org/basedir-spec/basedir-spec-latest.html
