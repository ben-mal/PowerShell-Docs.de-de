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
# <a name="installing-powershell-on-linux"></a>Installieren von PowerShell unter Linux

Sämtliche Pakete sind auf der Seite [Freigaben][] über GitHub verfügbar. Nachdem Sie das Paket installiert haben, führen Sie `pwsh` über das Terminal aus. Führen Sie `pwsh-preview` aus, wenn Sie eine [Vorschauversion](#installing-preview-releases) installiert haben.

> [!NOTE]
> PowerShell 7 ist ein direktes Upgrade, mit dem PowerShell Core 6.x entfernt wird.
>
> Der Ordner `/usr/local/microsoft/powershell/6` wird durch `/usr/local/microsoft/powershell/7` ersetzt.
>
> Wenn Sie PowerShell 6 und PowerShell 7 parallel ausführen müssen, installieren Sie PowerShell 6 mithilfe der [binary archive](#binary-archives)-Methode neu.

Für nicht offiziell unterstützte Linux-Distributionen können Sie versuchen, PowerShell über das [Snap-Paket für PowerShell][snap] zu installieren. Stattdessen können Sie auch versuchen, PowerShell-Binärdateien über das [`tar.gz`-Archiv][tar] für Linux bereitzustellen. Dafür müssen Sie aber die für Ihr Betriebssystem erforderlichen Abhängigkeiten in zusätzlichen Schritten einrichten.

[snap]: #snap-package
[tar]: #binary-archives

<!-- TODO: Update for supported releases v7.0 & v7.1 -->

Offiziell unterstützte Plattformreleases für PowerShell 7.1

- Ubuntu 16.04/18.04/20.04 (einschließlich ARM64)
- Ubuntu 19.10 (über Snap-Pakete)
- Debian 9/10
- CentOS und RHEL 7/8
- Fedora 30
- Alpine ab 3.11 (einschließlich ARM64)

Offiziell unterstützte Plattformreleases für PowerShell 7.0

- Ubuntu 16.04
- Ubuntu 18.04 und 20.04
- Debian 8
- Debian 9
- Debian 10
- Alpine 3.9 und 3.10
- CentOS 7:
- Red Hat Enterprise Linux 7 (RHEL)
- Fedora 28
- Fedora 29
- Fedora 30
- openSUSE 42.3
- openSUSE Leap 15

Von der Community unterstützte Releases:

- Ubuntu 18.10
- Ubuntu 19.10 und 20.10
- Arch Linux
- Kali
- Raspbian (experimentell)

Alternative Installationsmethoden

- Snap-Paket
- Archive der Binärdateien
- Globales .NET-Tool

## <a name="ubuntu-1604"></a>Ubuntu 16.04

### <a name="installation-via-package-repository---ubuntu-1604"></a>Installation über das Paketrepository: Ubuntu 16.04

PowerShell für Linux wird in Paketrepositorys veröffentlicht, um die Installation und die Updates zu vereinfachen.

Folgende Methode wird bevorzugt:

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

Registrieren Sie das Microsoft-Repository einmal als Superuser. Nach der Registrierung können Sie PowerShell mit `sudo apt-get install powershell` aktualisieren.

### <a name="installation-via-direct-download---ubuntu-1604"></a>Installation über einen direkten Download: Ubuntu 16.04

Laden Sie das Debian-Paket `powershell_7.1.3-1.ubuntu.16.04_amd64.deb` über die Seite [Freigaben][] auf den Ubuntu-Computer herunter.

Führen Sie dann im Terminal folgenden Befehl aus:

```sh
sudo dpkg -i powershell_7.1.3-1.ubuntu.16.04_amd64.deb
sudo apt-get install -f
```

> [!NOTE]
> Der `dpkg -i`-Befehl schlägt mit nicht erfüllten Abhängigkeiten fehl. Über den Befehl `apt-get install -f` werden diese Probleme behoben und die Konfiguration des PowerShell-Pakets abgeschlossen.

### <a name="uninstallation---ubuntu-1604"></a>Deinstallation: Ubuntu 16.04

```sh
sudo apt-get remove powershell
```

## <a name="ubuntu-1804"></a>Ubuntu 18.04

### <a name="installation-via-package-repository---ubuntu-1804"></a>Installation über das Paketrepository: Ubuntu 18.04

PowerShell für Linux wird in Paketrepositorys veröffentlicht, um die Installation und die Updates zu vereinfachen.

Folgende Methode wird bevorzugt:

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

Registrieren Sie das Microsoft-Repository einmal als Superuser. Nach der Registrierung können Sie PowerShell mit `sudo apt-get install powershell` aktualisieren.

### <a name="installation-via-direct-download---ubuntu-1804"></a>Installation über einen direkten Download: Ubuntu 18.04

Laden Sie das Debian-Paket `powershell_7.1.3-1.ubuntu.18.04_amd64.deb` über die Seite [Freigaben][] auf den Ubuntu-Computer herunter.

Führen Sie dann im Terminal folgenden Befehl aus:

```sh
sudo dpkg -i powershell_7.1.3-1.ubuntu.18.04_amd64.deb
sudo apt-get install -f
```

> [!NOTE]
> Der `dpkg -i`-Befehl schlägt mit nicht erfüllten Abhängigkeiten fehl. Über den Befehl `apt-get install -f` werden diese Probleme behoben und die Konfiguration des PowerShell-Pakets abgeschlossen.

### <a name="uninstallation---ubuntu-1804"></a>Deinstallation: Ubuntu 18.04

```sh
sudo apt-get remove powershell
```

## <a name="ubuntu-2004"></a>Ubuntu 20.04

### <a name="installation-via-package-repository---ubuntu-2004"></a>Installation über das Paketrepository: Ubuntu 20.04

PowerShell für Linux wird in Paketrepositorys veröffentlicht, um die Installation und die Updates zu vereinfachen.

Folgende Methode wird bevorzugt:

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

Registrieren Sie das Microsoft-Repository einmal als Superuser. Nach der Registrierung können Sie PowerShell mit `sudo apt-get install powershell` aktualisieren.

### <a name="installation-via-direct-download---ubuntu-2004"></a>Installation über direkten Download: Ubuntu 20.04

Laden Sie das Debian-Paket `powershell_7.1.3-1.ubuntu.20.04_amd64.deb` über die Seite [Freigaben][] auf den Ubuntu-Computer herunter.

Führen Sie dann im Terminal folgenden Befehl aus:

```sh
sudo dpkg -i powershell_7.1.3-1.ubuntu.20.04_amd64.deb
sudo apt-get install -f
```

> [!NOTE]
> Der `dpkg -i`-Befehl schlägt mit nicht erfüllten Abhängigkeiten fehl. Über den Befehl `apt-get install -f` werden diese Probleme behoben und die Konfiguration des PowerShell-Pakets abgeschlossen.

### <a name="uninstallation---ubuntu-2004"></a>Deinstallation: Ubuntu 20.04

```sh
sudo apt-get remove powershell
```

## <a name="ubuntu-1810"></a>Ubuntu 18.10

Die Installation wird über `snapd` unterstützt. Anweisungen finden Sie unter [Snap-Paket][snap].

> [!NOTE]
> Ubuntu 18.10 ist ein [Zwischenrelease](https://www.ubuntu.com/about/release-cycle), das von der [Community unterstützt](../powershell-support-lifecycle.md) wird.

## <a name="ubuntu-1910-and-2010"></a>Ubuntu 19.10 und 20.10

Die Installation wird über `snapd` unterstützt. Anweisungen finden Sie unter [Snap-Paket][snap].

> [!NOTE]
> Ubuntu 19.10 ist ein [Zwischenrelease](https://www.ubuntu.com/about/release-cycle) mit [Support durch die Community](../powershell-support-lifecycle.md).

## <a name="debian-8"></a>Debian 8

### <a name="installation-via-package-repository---debian-8"></a>Installation über das Paketrepository: Debian 8

PowerShell für Linux wird in Paketrepositorys veröffentlicht, um die Installation und die Updates zu vereinfachen.

Folgende Methode wird bevorzugt:

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

Registrieren Sie das Microsoft-Repository einmal als Superuser. Nach der Registrierung können Sie PowerShell mit `sudo apt-get install powershell` aktualisieren.

## <a name="debian-9"></a>Debian 9

### <a name="installation-via-package-repository---debian-9"></a>Installation über das Paketrepository: Debian 9

PowerShell für Linux wird in Paketrepositorys veröffentlicht, um die Installation und die Updates zu vereinfachen.

Folgende Methode wird bevorzugt:

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

Registrieren Sie das Microsoft-Repository einmal als Superuser. Nach der Registrierung können Sie PowerShell mit `sudo apt-get install powershell` aktualisieren.

### <a name="installation-via-direct-download---debian-9"></a>Installation über einen direkten Download: Debian 9

Laden Sie das Debian-Paket `powershell_7.1.3-1.debian.9_amd64.deb` über die Seite [Freigaben][] auf den Debian-Computer herunter.

Führen Sie dann im Terminal folgenden Befehl aus:

```sh
sudo dpkg -i powershell_7.1.3-1.debian.9_amd64.deb
sudo apt-get install -f
```

### <a name="uninstallation---debian-9"></a>Deinstallation: Debian 9

```sh
sudo apt-get remove powershell
```

## <a name="debian-10"></a>Debian 10

> [!NOTE]
> Debian 10 wird nur in PowerShell 7.0 und höher unterstützt.

### <a name="installation-via-package-repository---debian-10"></a>Installation über das Paketrepository: Debian 10

PowerShell für Linux wird in Paketrepositorys veröffentlicht, um die Installation und die Updates zu vereinfachen.

Folgende Methode wird bevorzugt:

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

### <a name="installation-via-direct-download---debian-10"></a>Installation über direkten Download: Debian 10

Laden Sie das tar.gz-Paket `powershell-7.1.3-linux-x64.tar.gz` über die Seite [Freigaben][] auf den Debian-Computer herunter.

Führen Sie dann im Terminal folgenden Befehl aus:

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

## <a name="alpine-39-and-310"></a>Alpine 3.9 und 3.10

> [!NOTE]
> Alpine 3.9 und 3.10 werden nur in PowerShell 7.0 und höher unterstützt.

### <a name="installation-via-direct-download---alpine-39-and-310"></a>Installation über direkten Download: Alpine 3.9 und 3.10

Laden Sie das tar.gz-Paket `powershell-7.1.3-linux-alpine-x64.tar.gz` über die Seite [Freigaben][] auf den Alpine-Computer herunter.

Führen Sie dann im Terminal folgenden Befehl aus:

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

## <a name="centos-7"></a>CentOS 7:

> [!NOTE]
> Dieses Paket funktioniert unter Oracle Linux 7.

### <a name="installation-via-package-repository-preferred---centos-7"></a>Installation über das Paketrepository (bevorzugt): CentOS 7

PowerShell für Linux wird in offiziellen Microsoft-Repositorys veröffentlicht, um die Installation und die Updates zu vereinfachen.

```sh
# Register the Microsoft RedHat repository
curl https://packages.microsoft.com/config/rhel/7/prod.repo | sudo tee /etc/yum.repos.d/microsoft.repo

# Install PowerShell
sudo yum install -y powershell

# Start PowerShell
pwsh
```

Registrieren Sie das Microsoft-Repository einmal als Superuser. Nach der Registrierung können Sie PowerShell mit `sudo yum update powershell` aktualisieren.

### <a name="installation-via-direct-download---centos-7"></a>Installation über einen direkten Download: CentOS 7

Für [CentOS 7][]: Laden Sie das RPM-Paket `powershell-7.1.3-1.rhel.7.x86_64.rpm` über die Seite [Freigaben][] auf den CentOS-Computer herunter.

Führen Sie dann im Terminal folgenden Befehl aus:

```sh
sudo yum install powershell-7.1.3-1.rhel.7.x86_64.rpm
```

Sie können RPM ohne Download installieren:

```sh
sudo yum install https://github.com/PowerShell/PowerShell/releases/download/v7.1.3/powershell-7.1.3-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---centos-7"></a>Deinstallation: CentOS 7

```sh
sudo yum remove powershell
```

[CentOS 7]: https://www.centos.org/download/

## <a name="red-hat-enterprise-linux-rhel-7"></a>Red Hat Enterprise Linux 7 (RHEL)

### <a name="installation-via-package-repository-preferred---red-hat-enterprise-linux-rhel-7"></a>Installation über ein Paketrepository (bevorzugt): Red Hat Enterprise Linux 7 (RHEL)

PowerShell für Linux wird in offiziellen Microsoft-Repositorys veröffentlicht, um die Installation und die Updates zu vereinfachen.

```sh
# Register the Microsoft RedHat repository
curl https://packages.microsoft.com/config/rhel/7/prod.repo | sudo tee /etc/yum.repos.d/microsoft.repo

# Install PowerShell
sudo yum install -y powershell

# Start PowerShell
pwsh
```

Registrieren Sie das Microsoft-Repository einmal als Superuser. Nach der Registrierung können Sie PowerShell mit `sudo yum update powershell` aktualisieren.

### <a name="installation-via-direct-download---red-hat-enterprise-linux-rhel-7"></a>Installation über einen direkten Download: Red Hat Enterprise Linux 7 (RHEL)

Laden Sie das RPM-Paket `powershell-7.1.3-1.rhel.7.x86_64.rpm` über die Seite [Freigaben][] auf den Red Hat Enterprise Linux-Computer herunter.

Führen Sie dann im Terminal folgenden Befehl aus:

```sh
sudo yum install powershell-7.1.3-1.rhel.7.x86_64.rpm
```

Sie können RPM ohne Download installieren:

```sh
sudo yum install https://github.com/PowerShell/PowerShell/releases/download/v7.1.3/powershell-7.1.3-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---red-hat-enterprise-linux-rhel-7"></a>Deinstallation: Red Hat Enterprise Linux 7 (RHEL)

```sh
sudo yum remove powershell
```

## <a name="opensuse"></a>openSUSE

### <a name="installation---opensuse-423"></a>Installation: openSUSE 42.3

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

### <a name="installation---opensuse-leap-15"></a>Installation: openSUSE Leap 15

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

### <a name="uninstallation---opensuse-423-opensuse-leap-15"></a>Deinstallation: openSUSE 42.3, openSUSE Leap 15

```sh
rm -rf /usr/bin/pwsh /opt/microsoft/powershell
```

## <a name="fedora"></a>Fedora

> [!NOTE]
> Fedora 28 wird nur in PowerShell 6.1 und höher unterstützt.

> [!NOTE]
> Fedora 29 und 30 werden nur in PowerShell 7.0 und höher unterstützt.

### <a name="installation-via-package-repository-preferred---fedora-28-29-and-30"></a>Installation über das Paketrepository (bevorzugt): Fedora 28, 29 und 30

PowerShell für Linux wird in offiziellen Microsoft-Repositorys veröffentlicht, um die Installation und die Updates zu vereinfachen.

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

### <a name="installation-via-direct-download---fedora-28-29-and-30"></a>Installation über direkten Download: Fedora 28, 29 und 30

Laden Sie das RPM-Paket `powershell-7.1.3-1.rhel.7.x86_64.rpm` über die Seite [Freigaben][] auf den Fedora-Computer herunter.

Führen Sie dann im Terminal folgenden Befehl aus:

```sh
sudo dnf install compat-openssl10
sudo dnf install powershell-7.1.3-1.rhel.7.x86_64.rpm
```

Sie können RPM ohne Download installieren:

```sh
sudo dnf install compat-openssl10
sudo dnf install https://github.com/PowerShell/PowerShell/releases/download/v7.1.3/powershell-7.1.3-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---fedora-28-29-and-30"></a>Deinstallation: Fedora 28, 29 und 30

```sh
sudo dnf remove powershell
```

## <a name="arch-linux"></a>Arch Linux

> [!NOTE]
> Arch Linux wird offiziell nicht von Microsoft unterstützt und daher von der Community verwaltet.

PowerShell ist über das Benutzerrepository [Arch Linux][] verfügbar.

- Es kann gemeinsam mit dem [zuletzt markierten Release][arch-release] kompiliert werden.
- Es kann gemeinsam vom [letzten Commit für den Master][arch-git] aus kompiliert werden.
- Es kann mithilfe der [zuletzt zur Veröffentlichung bestimmten Binärdatei][arch-bin] installiert werden.

Pakete im Benutzerrepository „Arch Linux“ werden von der Community verwaltet. Es gibt keinen offiziellen Support.

Weitere Informationen zum Installieren von Paketen aus dem Benutzerrepository „Arch Linux“ finden Sie im [Arch Linux-Wiki](https://wiki.archlinux.org/index.php/Arch_User_Repository#Installing_packages) oder unter [Verwenden von PowerShell in Docker](powershell-in-docker.md).

[Arch Linux]: https://www.archlinux.org/download/
[arch-release]: https://aur.archlinux.org/packages/powershell/
[arch-git]: https://aur.archlinux.org/packages/powershell-git/
[arch-bin]: https://aur.archlinux.org/packages/powershell-bin/

## <a name="snap-package"></a>Snap-Paket

### <a name="getting-snapd"></a>Abrufen von snapd

`snapd` ist für das Ausführen von Snap-Paketen erforderlich. Halten Sie sich an [diese Anweisungen](https://docs.snapcraft.io/core/install), um sicherzustellen, dass `snapd` installiert ist.

### <a name="installation-via-snap"></a>Installation über Snap

PowerShell für Linux wird im [Snap-Store](https://snapcraft.io/store) veröffentlicht, um die Installation und die Updates zu vereinfachen.

Folgende Methode wird bevorzugt:

```sh
# Install PowerShell
sudo snap install powershell --classic

# Start PowerShell
pwsh
```

Gehen Sie folgendermaßen vor, wenn Sie eine Vorschauversion installieren möchten:

```sh
# Install PowerShell
sudo snap install powershell-preview --classic

# Start PowerShell
pwsh-preview
```

Nach der Installation wird für Snap automatisch ein Upgrade durchgeführt. Sie können ein Upgrade mit `sudo snap refresh powershell` oder `sudo snap refresh powershell-preview` auslösen.

### <a name="uninstallation"></a>Deinstallation

```sh
sudo snap remove powershell
```

oder

```sh
sudo snap remove powershell-preview
```

## <a name="kali"></a>Kali

> [!NOTE]
> Kali wird offiziell nicht von Microsoft unterstützt und daher von der Community verwaltet.

### <a name="installation---kali"></a>Installation: Kali

```sh
# Install PowerShell package
apt update && apt -y install powershell

# Start PowerShell
pwsh
```

### <a name="uninstallation---kali"></a>Deinstallation: Kali

```sh
# Uninstall PowerShell package
apt -y remove powershell
```

## <a name="support-for-arm-processors"></a>Unterstützung für ARM-Prozessoren

PowerShell kann unter einigen Linux-Distributionen installiert werden. PowerShell benötigt die .NET-Unterstützung von ARM. PowerShell wird unter den folgenden Distributionen unterstützt:

- Alpine Linux v3.11+: .NET unterstützt Arm64, aber zurzeit gibt es noch kein installierbares Paket für PowerShell.
- Raspbian: Die Installationsanweisungen finden Sie weiter unten.
- Debian v9+: Unterstützt Arm32 und Arm64 über die Installationsmethode [Archive der Binärdateien](#binary-archives).
- Ubuntu 20.10, 20.04, 18.04, 16.04: Unterstützt Arm32 und Arm64 über die Installationsmethode [Archive der Binärdateien](#binary-archives).

## <a name="raspbian"></a>Raspbian

> [!NOTE]
> Die Unterstützung von Raspbian wird noch getestet.

Derzeit wird PowerShell nur unter Raspbian Stretch unterstützt.

Außerdem funktionieren CoreCLR und PowerShell nur auf Geräten mit Pi 2 und Pi 3, da andere Geräte, wie z. B. [Pi Zero](https://github.com/dotnet/coreclr/issues/10605), einen nicht unterstützten Prozessor haben.

Laden Sie [Raspbian Stretch](https://www.raspberrypi.org/downloads/raspbian/) herunter, und folgen Sie den [Installationsanweisungen](https://www.raspberrypi.org/documentation/installation/installing-images/README.md), um es zu installieren.

### <a name="installation---raspbian"></a>Installation: Raspbian

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

Optional können Sie eine symbolische Verknüpfung erstellen, damit Sie PowerShell ohne Angabe des Pfads zur Binärdatei `pwsh` starten können.

```sh
# Start PowerShell from bash with sudo to create a symbolic link
sudo ~/powershell/pwsh -c New-Item -ItemType SymbolicLink -Path "/usr/bin/pwsh" -Target "$PSHOME/pwsh" -Force

# alternatively you can run following to create a symbolic link
# sudo ln -s ~/powershell/pwsh /usr/bin/pwsh

# Now to start PowerShell you can just run "pwsh"
```

### <a name="uninstallation---raspbian"></a>Deinstallation: Raspbian

```sh
rm -rf ~/powershell
```

## <a name="installing-preview-releases"></a>Installieren von Vorschauversionen

Wenn eine Vorschauversion von PowerShell für Linux über ein Paketrepository installiert wird, ändert sich der Paketname von `powershell` in `powershell-preview`.

Bei einer Installation über einen direkten Download wird nur der Dateiname geändert.

In der nachfolgenden Tabelle werden die Befehle aufgeführt, über die Sie Pakete stabiler Versionen und von Vorschauversionen mithilfe der verschiedenen Paket-Manager installieren können:

| Distribution(en) |            Befehl für die stabile Version            |               Befehl für die Vorschauversion                |
| --------------- | ------------------------------------ | -------------------------------------------- |
| Ubuntu, Debian  | `sudo apt-get install -y powershell` | `sudo apt-get install -y powershell-preview` |
| CentOS, RedHat  | `sudo yum install -y powershell`     | `sudo yum install -y powershell-preview`     |
| Fedora          | `sudo dnf install -y powershell`     | `sudo dnf install -y powershell-preview`     |

## <a name="install-as-a-net-global-tool"></a>Installieren als globales .NET-Tool

Wenn Sie das [.NET Core SDK](/dotnet/core/sdk) bereits installiert haben, können Sie PowerShell einfach als [globales .NET-Tool](/dotnet/core/tools/global-tools) installieren.

```
dotnet tool install --global PowerShell
```

Der .NET-Toolinstaller fügt `~/.dotnet/tools` Ihrer `PATH`-Umgebungsvariablen hinzu. Die aktuell ausgeführte Shell verfügt jedoch nicht über den aktualisierten `PATH`. Sie sollten PowerShell über eine neue Shell starten können, indem Sie `pwsh` eingeben.

## <a name="binary-archives"></a>Archive der Binärdateien

`tar.gz`-Archive der PowerShell-Binärdateien werden für Linux-Plattformen zur Verfügung gestellt, um erweiterte Bereitstellungsszenarios zu aktivieren.

> [!NOTE]
> Sie können diese Methode verwenden, um eine beliebige Version von PowerShell zu installieren, einschließlich der neuesten:
> - Stabiles Release: [https://aka.ms/powershell-release?tag=stable](https://aka.ms/powershell-release?tag=stable)
> - Vorschaurelease: [https://aka.ms/powershell-release?tag=preview](https://aka.ms/powershell-release?tag=preview)
> - LTS-Release: [https://aka.ms/powershell-release?tag=lts](https://aka.ms/powershell-release?tag=lts)

### <a name="dependencies"></a>Abhängigkeiten

PowerShell erstellt portierbare Binärdateien für alle Linux-Distributionen. Allerdings erfordern die .NET Core-Runtime und PowerShell verschiedene Abhängigkeiten für die verschiedenen Distributionen.

Im folgenden Diagramm werden die Abhängigkeiten von .NET Core 2.0 für die verschiedenen Linux-Distributionen dargestellt, die offiziell unterstützt werden.

| OS                 | Abhängigkeiten |
| ------------------ | ------------ |
| Ubuntu 16.04       | libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6, <br> libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu55 |
| Ubuntu 17.10       | libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6, <br> libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu57 |
| Ubuntu 18.04       | libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6, <br> libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu60 |
| Debian 8 (Jessie)  | libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6, <br> libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu52 |
| Debian 9 (Stretch) | libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6, <br> libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.2, libicu57 |
| CentOS 7: <br> Oracle Linux 7 <br> RHEL 7 | libunwind, libcurl, openssl-libs, libicu |
| openSUSE 42.3 | libcurl4, libopenssl1_0_0, libicu52_1 |
| openSUSE Leap 15 | libcurl4, libopenssl1_0_0, libicu60_2 |
| Fedora 27 <br> Fedora 28 | libunwind, libcurl, openssl-libs, libicu, compat-openssl10 |

Sie müssen zur Bereitstellung von PowerShell-Binärdateien für nicht offiziell unterstützte Linux-Distributionen die notwendigen Abhängigkeiten für das Zielbetriebssystem über zusätzliche Schritte installieren. Beispielsweise installiert die [Amazon Linux-Dockerfile][amazon-dockerfile] zuerst die Abhängigkeiten und extrahiert anschließend das `tar.gz`-Archiv für Linux.

[amazon-dockerfile]: https://github.com/PowerShell/PowerShell-Docker/blob/master/release/community-stable/amazonlinux/docker/Dockerfile

### <a name="installation---binary-archives"></a>Installation: Archive von Binärdateien

Das folgende Beispiel zeigt die Schritte zur Installation des Archivs der x64-Binärdateien. Sie müssen das richtige Binärdateienarchiv auswählen, das dem Prozessortyp Ihrer Plattform entspricht.

- powershell-7.1.3-linux-arm32.tar.gz
- powershell-7.1.3-linux-arm64.tar.gz
- powershell-7.1.3-linux-x64.tar.gz

#### <a name="linux"></a>Linux

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

### <a name="uninstalling-binary-archives"></a>Deinstallation: Archive von Binärdateien

```sh
sudo rm -rf /usr/bin/pwsh /opt/microsoft/powershell
```

## <a name="paths"></a>Paths

- `$PSHOME` ist `/opt/microsoft/powershell/7/`.
- Benutzerprofile werden aus `~/.config/powershell/profile.ps1` gelesen.
- Standardprofile werden aus `$PSHOME/profile.ps1` gelesen.
- Benutzermodule werden aus `~/.local/share/powershell/Modules` gelesen.
- Freigegebene Module werden aus `/usr/local/share/powershell/Modules` gelesen.
- Standardmodule werden aus `$PSHOME/Modules` gelesen.
- Der PSReadLine-Verlauf wird in `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt` protokolliert.

Die Profile beachten die Konfigurationen von PowerShell pro Host. Das bedeutet, die hostspezifischen Standardprofile sind an denselben Orten unter `Microsoft.PowerShell_profile.ps1` gespeichert.

PowerShell hält die [XDG Base Directory Specification (XDG Base Directory-Spezifikation)][xdg-bds] unter Linux ein.

## <a name="installation-support"></a>Installationsunterstützung

Microsoft unterstützt die in diesem Dokument beschriebenen Installationsmethoden. Möglicherweise stehen andere Installationsmethoden aus anderen Quellen zur Verfügung. Auch wenn diese Tools und Methoden funktionieren, kann Microsoft sie nicht unterstützen.

<!-- link references -->
[Freigaben]: https://aka.ms/PowerShell-Release?tag=stable
[xdg-bds]: https://specifications.freedesktop.org/basedir-spec/basedir-spec-latest.html
[distros]: https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md#linux
[Distribution Support Request]: https://github.com/PowerShell/PowerShell/issues/new?assignees=&labels=Distribution-Request&template=Distribution_Request.md&title=Distribution+Support+Request
