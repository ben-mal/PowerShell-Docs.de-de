---
title: Installieren von PowerShell Core unter ARM
description: Installieren von PowerShell Core auf ARM-basierten Systemen
ms.date: 11/11/2020
ms.openlocfilehash: 85a2cccb18341ffee8c81430bc8490e5d3e97b41
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/19/2020
ms.locfileid: "94892071"
---
# <a name="powershell-core-on-arm"></a>PowerShell Core unter ARM

Unterstützung von PowerShell in ARM basiert auf den **Lebenszyklusrichtlinien unter „.NET Core 3.1 – Supported OS versions“** .

PowerShell 7.1 basiert auf den [Lebenszyklusrichtlinien unter „.NET Core 3.1 – Supported OS versions“](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md) und unterstützt die folgenden Plattformen:

|         Betriebssystem          |          Version           | Architekturen |          Lebenszyklus           |
| ------------------- | -------------------------- | ------------- | ---------------------------- |
| Windows Nano Server | Version 1803 oder höher              | ARM32         | [Windows][Windows-lifecycle] |
| Alpine Linux        | 3.10 oder höher                      | ARM64         | [Alpine][Alpine-lifecycle]   |
| Debian              | 9 und höher                         | ARM32, ARM64  | [Debian][Debian-lifecycle]   |
| Ubuntu              | 20.10, 20.04, 18.04, 16.04 | ARM32, ARM64  | [Ubuntu][Ubuntu-lifecycle]   |

PowerShell 7.0 basiert auf den [Lebenszyklusrichtlinien unter „.NET Core 5.0 – Supported OS versions“](https://github.com/dotnet/core/blob/master/release-notes/5.0/5.0-supported-os.md) und unterstützt die folgenden Plattformen:

|        Betriebssystem         |          Version           | Architekturen |          Lebenszyklus           |
| ----------------- | -------------------------- | ------------- | ---------------------------- |
| Windows 10-Client | Version 1607 oder höher              | ARM64         | [Windows][Windows-lifecycle] |
| Alpine Linux      | Ab 3.11                      | ARM64         | [Alpine][Alpine-lifecycle]   |
| Debian            | 9 und höher                         | ARM32, ARM64  | [Debian][Debian-lifecycle]   |
| Ubuntu            | 20.10, 20.04, 18.04, 16.04 | ARM32, ARM64  | [Ubuntu][Ubuntu-lifecycle]   |

[Windows-lifecycle]: https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet
[Alpine-lifecycle]: https://wiki.alpinelinux.org/wiki/Alpine_Linux:Releases
[Debian-lifecycle]: https://wiki.debian.org/DebianReleases
[Ubuntu-lifecycle]: https://wiki.ubuntu.com/Releases

Installationsanweisungen finden Sie in den folgenden Artikeln:

- [Windows 10 in ARM](installing-powershell-core-on-windows.md#installing-the-zip-package)
- [Windows 10 IoT Enterprise](installing-powershell-core-on-windows.md#deploying-on-windows-10-iot-enterprise)
- [Windows 10 IoT Core](installing-powershell-core-on-windows.md#deploying-on-windows-10-iot-core)
- [Raspbian](installing-powershell-core-on-linux.md#raspbian)
