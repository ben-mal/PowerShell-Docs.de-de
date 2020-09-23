---
title: Installieren von PowerShell unter macOS
description: Informationen zur Installation von PowerShell unter macOS
ms.date: 08/24/2020
ms.openlocfilehash: 8f38d573d9d67276dbc95cfb70f1fde80af62bb6
ms.sourcegitcommit: ea9270bacee7dd1b9df2519384de277576357ce2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/25/2020
ms.locfileid: "88857909"
---
# <a name="installing-powershell-on-macos"></a>Installieren von PowerShell unter macOS

PowerShell unterstützt macOS 10.12 und höher. PowerShell 7.0.3 und höher sowie die PowerShell-Vorschauversionen 7.1.0 und höher erfordern macOS 10.13 und höher. Sämtliche Pakete sind auf der Seite [Freigaben][] über GitHub verfügbar. Nachdem Sie das Paket installiert haben, führen Sie `pwsh` über das Terminal aus.

> [!NOTE]
> PowerShell 7 ist ein direktes Upgrade, mit dem PowerShell Core 6.x entfernt wird.
>
> Der Ordner `/usr/local/microsoft/powershell/6` wird durch `/usr/local/microsoft/powershell/7` ersetzt.
>
> Wenn Sie PowerShell 6 und PowerShell 7 parallel ausführen müssen, installieren Sie PowerShell 6 mithilfe der [binary archive](#binary-archives)-Methode neu.

Es gibt mehrere Möglichkeiten, PowerShell unter macOS zu installieren. Wählen Sie eine der folgenden Methoden:

- Verwenden Sie für die Installation Homebrew. Bei Homebrew handelt es sich um den bevorzugten Paket-Manager für macOS.
- Installieren Sie PowerShell über einen [direkten Download](#installation-via-direct-download).
- Führen Sie die Installation über [Archive der Binärdateien](#binary-archives) aus.

Installieren Sie nach der Installation von PowerShell [OpenSSL](#installing-dependencies). OpenSSL ist für PowerShell-Remotingfunktionen und CIM-Vorgänge erforderlich.

## <a name="installation-of-latest-stable-release-via-homebrew-on-macos-1013-or-higher"></a>Installation des neuesten stabilen Releases über Homebrew unter macOS 10.13 oder höher

Wenn der Befehl `brew` nicht gefunden wird, müssen Sie Homebrew installieren, indem Sie [die entsprechenden Anweisungen][brew] ausführen.

Jetzt können Sie PowerShell installieren:

```sh
brew cask install powershell
```

Vergewissern Sie sich abschließend, dass Ihre Installation voll funktionsfähig ist:

```sh
pwsh
```

Wenn neue Versionen von PowerShell veröffentlicht werden, aktualisieren Sie die Formeln für Homebrew, und führen Sie ein Upgrade für PowerShell aus:

```sh
brew update
brew cask upgrade powershell
```

> [!NOTE]
> Die oben genannten Befehle können innerhalb eines PowerShell-Hosts (pwsh) aufgerufen werden. Allerdings muss dann die Shell von PowerShell beendet und neu gestartet werden, um das Upgrade abzuschließen und die in `$PSVersionTable` dargestellten Werte zu aktualisieren.

[brew]: https://brew.sh/

## <a name="installation-of-latest-preview-release-via-homebrew-on-macos-1013-or-higher"></a>Installation der neuesten Vorschauversion über Homebrew unter macOS 10.13 oder höher

Nachdem Sie Homebrew installiert haben, können Sie PowerShell installieren. Installieren Sie zunächst das Paket [Cask-Versions][cask-versions]. Dies ermöglicht Ihnen das Installieren alternativer Versionen von Cask-Paketen:

```sh
brew tap homebrew/cask-versions
```

Jetzt können Sie PowerShell installieren:

```sh
brew cask install powershell-preview
```

Vergewissern Sie sich abschließend, dass Ihre Installation voll funktionsfähig ist:

```sh
pwsh-preview
```

Wenn neue Versionen von PowerShell veröffentlicht werden, aktualisieren Sie die Formeln für Homebrew, und führen Sie ein Upgrade für PowerShell aus:

```sh
brew update
brew cask upgrade powershell-preview
```

> [!NOTE]
> Die oben genannten Befehle können innerhalb eines PowerShell-Hosts (pwsh) aufgerufen werden, die Shell von PowerShell muss dann jedoch beendet und neu angegeben werden, um das Upgrade abzuschließen
> und die in `$PSVersionTable` dargestellten Werte zu aktualisieren.

Die Installation von PowerShell über die TAP-Methode Homebrew wird auch für stabile und LTS-Versionen unterstützt.

```sh
brew install powershell/tap/powershell
```

Überprüfen Sie nun die Installation.

```sh
pwsh
```

Wurden bereits neue Versionen von PowerShell veröffentlicht, führen Sie einfach den folgenden Befehl aus:

```sh
brew upgrade powershell
```

> [!NOTE]
> Verwenden Sie bei einem Update auf eine neuere PowerShell-Version dieselbe Methode (CASK oder TAP), die Sie bei der Erstinstallation von PowerShell verwendet haben. Andernfalls wird beim Öffnen einer neuen pwsh-Sitzung weiterhin die ältere Version von PowerShell verwendet.
>
> Wenn Sie sich dennoch für unterschiedliche Methoden entscheiden, können Sie das Problem mithilfe der [LINK-Methode von Homebrew](https://docs.brew.sh/Manpage#link-ln-options-formula) beheben.

## <a name="installation-via-direct-download"></a>Installation über einen direkten Download

Laden Sie das PKG-Paket `powershell-lts-7.0.3-osx-x64.pkg` über die Seite [Releases][] auf den macOS-Computer herunter.

Doppelklicken Sie entweder auf die Datei, und befolgen Sie die Anweisungen, oder installieren Sie das Paket über das Terminal:

```sh
sudo installer -pkg powershell-lts-7.0.3-osx-x64.pkg -target /
```

Installieren Sie [OpenSSL](#installing-dependencies). OpenSSL ist für PowerShell-Remotingfunktionen und CIM-Vorgänge erforderlich.

## <a name="install-as-a-net-global-tool"></a>Installieren als globales .NET-Tool

Wenn Sie das [.NET Core SDK](/dotnet/core/sdk) bereits installiert haben, können Sie PowerShell einfach als [globales .NET-Tool](/dotnet/core/tools/global-tools) installieren.

```
dotnet tool install --global PowerShell
```

Der .NET-Toolinstaller fügt `~/.dotnet/tools` Ihrer `PATH`-Umgebungsvariablen hinzu. Die aktuell ausgeführte Shell verfügt jedoch nicht über den aktualisierten `PATH`. Sie sollten PowerShell über eine neue Shell starten können, indem Sie `pwsh` eingeben.

Installieren Sie [OpenSSL](#installing-dependencies). OpenSSL ist für PowerShell-Remotingfunktionen und CIM-Vorgänge erforderlich.

## <a name="binary-archives"></a>Archive der Binärdateien

`tar.gz`-Archive der PowerShell-Binärdateien werden für die macOS-Plattform zur Verfügung gestellt, um erweiterte Bereitstellungsszenarios zu ermöglichen. Wenn Sie die Installation mit dieser Methode durchführen, müssen Sie auch alle Abhängigkeiten manuell installieren.

Installieren Sie [OpenSSL](#installing-dependencies). OpenSSL ist für PowerShell-Remotingfunktionen und CIM-Vorgänge erforderlich.

### <a name="installing-binary-archives-on-macos"></a>Installieren von Archiven der Binärdateien unter macOS

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

## <a name="installing-dependencies"></a>Installieren von Abhängigkeiten

Für PowerShell-Remoting und CIM-Vorgänge ist OpenSSL erforderlich. Bei Bedarf können Sie OpenSSL über MacPorts installieren.

> [!NOTE]
> Werden MacPorts und Homebrew im selben System verwendet, können Probleme auftreten. Homebrew verfügt jedoch über kein Paket für OpenSSL 1.0. Weitere Informationen finden Sie in den [Häufig gestellten Fragen zu MacPorts](https://trac.macports.org/wiki/FAQ).

1. Installieren Sie die Xcode-Befehlszeilentools. Diese sind für MacPorts erforderlich.

   ```sh
   xcode-select --install
   ```

1. Installieren Sie MacPorts. Wenn Sie Anleitungen dazu benötigen, lesen Sie das [Installationshandbuch](https://www.macports.org/install.php).
1. Aktualisieren Sie MacPorts durch Ausführen von `sudo port selfupdate`.
1. Führen Sie eine Upgrade von MacPorts-Paketen durch Ausführen von `sudo port upgrade outdated` durch.
1. Installieren Sie OpenSSL durch Ausführen von `sudo port install openssl10`.
1. Verknüpfen Sie die Bibliotheken, um sie PowerShell zur Verfügung zu stellen:

   ```sh
   sudo mkdir -p /usr/local/opt/openssl
   sudo ln -s /opt/local/lib/openssl-1.0 /usr/local/opt/openssl/lib
   ```

## <a name="uninstalling-powershell"></a>Deinstallieren von PowerShell

Wenn Sie PowerShell mit Homebrew installiert haben, verwenden Sie den folgenden Befehl zum Deinstallieren:

```sh
brew cask uninstall powershell
```

Wenn Sie PowerShell über einen direkten Download installiert haben, muss PowerShell manuell entfernt werden:

```sh
sudo rm -rf /usr/local/bin/pwsh /usr/local/microsoft/powershell
```

Lesen Sie den Abschnitt [Pfade](#paths) in diesem Artikel, um zu erfahren, wie Sie zusätzliche PowerShell-Pfade deinstallieren können. Entfernen Sie die Pfade mithilfe von `sudo rm`.

> [!NOTE]
> Dies ist nicht notwendig, wenn Sie eine Installation mit Homebrew durchgeführt haben.

## <a name="paths"></a>Paths

- `$PSHOME` ist `/usr/local/microsoft/powershell/7.0.3/`.
- Benutzerprofile werden über `~/.config/powershell/profile.ps1` gelesen.
- Standardprofile werden über `$PSHOME/profile.ps1` gelesen.
- Benutzermodule werden über `~/.local/share/powershell/Modules` gelesen.
- Freigegebene Module werden über `/usr/local/share/powershell/Modules` gelesen.
- Standardmodule werden über `$PSHOME/Modules` gelesen.
- Der Verlauf von „PSReadline“ wird in `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt` aufgezeichnet.

Die Profile halten sich an die Konfiguration von PowerShell pro Host. Dies bedeutet, dass hostspezifische Standardprofile in `Microsoft.PowerShell_profile.ps1` am gleichen Speicherort vorhanden sind.

PowerShell hält die [XDG Base Directory Specification (XDG Base Directory-Spezifikation)][xdg-bds] unter macOs ein.

Da macOS eine Ableitung von BSD ist, wird das Präfix `/usr/local` anstelle von `/opt` verwendet. Daher ist `$PSHOME` gleich `/usr/local/microsoft/powershell/7.0.3/`, und der symbolische Link wird unter `/usr/local/bin/pwsh` gespeichert.

## <a name="installation-support"></a>Installationsunterstützung

Microsoft unterstützt die in diesem Dokument beschriebenen Installationsmethoden. Möglicherweise stehen andere Installationsmethoden aus anderen Quellen zur Verfügung. Auch wenn diese Tools und Methoden funktionieren, kann Microsoft sie nicht unterstützen.

## <a name="additional-resources"></a>Zusätzliche Ressourcen

- [Homebrew-Website][brew]
- [Homebrew-GitHub-Repository][GitHub]
- [Homebrew-Cask][cask]

[brew]: http://brew.sh/
[Cask]: https://github.com/Homebrew/homebrew-cask
[cask-versions]: https://github.com/Homebrew/homebrew-cask-versions
[GitHub]: https://github.com/Homebrew
[Freigaben]: https://github.com/PowerShell/PowerShell/releases/latest
[xdg-bds]: https://specifications.freedesktop.org/basedir-spec/basedir-spec-latest.html
