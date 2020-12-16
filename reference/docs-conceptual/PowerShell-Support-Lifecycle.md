---
title: Supportlebenszyklus von PowerShell Core
description: Führt die Richtlinien für die Unterstützung von PowerShell im Details aus.
ms.date: 11/11/2020
ms.openlocfilehash: f2a1df0fabdfb624db666d240172930dc60f1bfe
ms.sourcegitcommit: 2fc6ee49a70bda4c59135136bd5cc7782836a124
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94810384"
---
# <a name="powershell-support-lifecycle"></a>Supportlebenszyklus von PowerShell

PowerShell ist eine Zusammenstellung von Tools und Komponenten, die separat von Windows PowerShell bereitgestellt, installiert und konfiguriert wird. PowerShell wird nicht in den Windows-Lizenzverträgen aufgeführt.

PowerShell wird von herkömmlichen Microsoft-Supportvereinbarungen abgedeckt, darunter [kostenpflichtiger Support][], [Microsoft Enterprise Agreements][enterprise-agreement] und [Microsoft Software Assurance][assurance]. Sie können auch Hilfe bei der kostenpflichtigen [unterstützten Support][] für PowerShell anfordern.

## <a name="community-support"></a>Communitysupport

Auf GitHub wird Ihnen auch [Communitysupport][] geboten. Dort können Sie Tickets zu Problemen, Fehlern oder Funktionsanfragen stellen.
Außerdem finden Sie Unterstützung von anderen Mitgliedern der Community in der Microsoft [PowerShell Tech Community][] oder in einem der Foren, die im Communityabschnitt der [PowerShell][pshub]-Hubseite aufgeführt sind. Wir bieten keine Garantie, dass die Community Ihr Problem zügig behandelt oder behebt. Wenn Sie ein Problem haben, das unmittelbar Aufmerksamkeit erfordert, sollten Sie sich an die herkömmlichen kostenpflichtigen Supportoptionen wenden.

## <a name="lifecycle-of-powershell-7"></a>Lebenszyklus von PowerShell 7

Mit der Veröffentlichung von PowerShell 7 wird PowerShell weiterhin im Rahmen der [Microsoft Modern Lifecycle-Richtlinie][modern]unterstützt, die Datumsfestlegungen für den Support sind jedoch an den [.NET Core][Long-Term]-Supportlebenszyklus geknüpft. Bei diesem Serviceansatz können Kunden zwischen LTS-Releases (Long-Term Support) und aktuellen Releases auswählen. PowerShell 7.0 ist ein LTS-Release. Der Support endet mit dem Support von .NET Core 3.1. Das nächste LTS-Release folgt dem nächsten LTS-Release von .NET Core. Aktuelle Datumsangaben für das Supportende finden Sie in der [Tabelle zum Ende der Lebensdauer von PowerShell-Releases](#powershell-releases-end-of-life). Updates für LTS-Releases enthalten nur kritische Sicherheits- und Wartungsupdates sowie Korrekturen, die entwickelt wurden, um Auswirkungen auf vorhandene Workloads zu vermeiden oder auf ein Mindestmaß zu beschränken.

Ein aktuelles Release ist ein Release, das zwischen LTS-Releases erfolgt. Aktuelle Releases können wichtige Korrekturen, Neuerungen und neue Features enthalten. Ein aktuelles Release wird nach nachfolgenden aktuellen oder LTS-Releases für drei Monate unterstützt.

> [!IMPORTANT]
> Sie müssen das neueste Patchupdate installiert haben, um Anspruch auf Support zu erhalten. Wenn Sie z. B. PowerShell 7.0 ausführen und 7.0.1 veröffentlicht wurde, müssen Sie auf 7.0.1 aktualisieren, um Support beanspruchen zu können.

## <a name="supported-platforms"></a>Unterstützte Plattformen

Um zu bestätigen, ob Ihre Plattform und Ihre Version von PowerShell Core offiziell unterstützt werden, lesen Sie die folgende Tabelle.

Unsere Community hat außerdem Pakete für einige Plattformen beigesteuert, die jedoch nicht offiziell unterstützt werden. Diese Pakete sind in der Tabelle mit `Community` gekennzeichnet.

Plattformen, die als `Experimental` gekennzeichnet sind, werden nicht offiziell unterstützt, stehen aber zu Test- und Feedbackzwecken zur Verfügung.

<!-- TODO: update OS list -->

|                     Plattform                      |      7.0      |      7.1      |
| ------------------------------------------------- | :-----------: | :-----------: |
| Windows 8.1 und 10                               |   Unterstützt   |   Unterstützt   |
| Windows Server 2012 R2, 2016, 2019                |   Unterstützt   |   Unterstützt   |
| [Halbjährlicher Kanal von Windows Server][semi-annual] |   Unterstützt   |   Unterstützt   |
| Ubuntu 16.04, 18.04                               |   Unterstützt   |   Unterstützt   |
| Ubuntu 20.04                                      | Nicht unterstützt |   Unterstützt   |
| Ubuntu 19.10, 20.10 (über Snap-Pakete)            |   Community   |   Unterstützt   |
| Debian 9                                          |   Unterstützt   |   Unterstützt   |
| Debian 10                                         |   Unterstützt   |   Unterstützt   |
| CentOS 7:                                          |   Unterstützt   |   Unterstützt   |
| CentOS 8                                          |   Unterstützt   |   Unterstützt   |
| Red Hat Enterprise Linux 7                        |   Unterstützt   |   Unterstützt   |
| Red Hat Enterprise Linux 8                        |   Unterstützt   |   Unterstützt   |
| Ab Fedora 31                                        |   Unterstützt   | Nicht unterstützt |
| Alpine 3.10                                       |   Siehe Hinweis 1  | Nicht unterstützt |
| Ab Alpine 3.11                                      |   Siehe Hinweis 1  |   Siehe Hinweis 1  |
| macOS ab 10.13                                      |   Unterstützt   |   Unterstützt   |
| Arch                                              |   Community   |   Community   |
| Raspbian                                          |   Community   |   Community   |
| Kali                                              |   Community   |   Community   |
| AppImage (funktioniert auf verschiedenen Linux-Plattformen)      |   Community   |   Community   |
| [Snap-Paket](https://snapcraft.io/powershell)   |   Siehe Hinweis 2  |   Siehe Hinweis    |

> [!NOTE]
> - 1: CIM, PowerShell-Remoting und DSC werden in Alpine nicht unterstützt.
> - 2: Snap-Pakete werden genauso wie die Distribution unterstützt, in der Sie das Paket ausführen.

## <a name="powershell-releases-end-of-life"></a>Ende der Lebensdauer von PowerShell-Releases

Basierend auf dem [Lebenszyklus von PowerShell](#lifecycle-of-powershell-7) wird in der folgenden Tabelle für verschiedene Releases das Datum angegeben, ab dem sie nicht mehr unterstützt werden.

| Version |          Ende der Lebensdauer           |
| :-----: | ------------------------------ |
|   7.1   | Mitte Februar 2022 (geplant) |
|   7.0   | 3\. Dezember 2022               |
|   6.2   | 4\. September 2020              |
|   6.1   | 28. September 2019             |
|   6.0   | 13. Februar 2019              |

> [!NOTE]
> In diesem Dokument geht es um Support für PowerShell Core. Windows PowerShell (1.0-5.1) ist eine Komponente des Windows-Betriebssystems. Komponenten erhalten dieselbe Unterstützung wie das übergeordnete Produkt oder die übergeordnete Plattform. Weitere Informationen finden Sie unter [Informationen zum Lebenszyklus von Produkten und Diensten](/lifecycle/products/).

## <a name="unsupported-platforms"></a>Nicht unterstützte Plattformen

Wenn eine Plattformversion das Ende ihrer Lebensdauer (wie vom Plattformbesitzer festgelegt) erreicht, endet auch die Unterstützung von PowerShell Core für diese Plattformversion. Bereits veröffentlichte Pakete bleiben weiterhin für Kunden verfügbar, die Zugriff benötigen. Die formelle Unterstützung und reguläre Updates jeglicher Art werden nicht mehr veröffentlicht.

Deshalb haben die Distributionsbesitzer die Unterstützung für die folgenden Versionen beendet.

<!-- TODO: Update this table Jason-->

|    Plattform    | Version |                                                         Ende der Lebensdauer                                                          |
| -------------- | :-----: | ---------------------------------------------------------------------------------------------------------------------------- |
| Debian         |    8    | [Juni 2018](https://lists.debian.org/debian-security-announce/2018/msg00132.html)                                            |
| Fedora         |   24    | [August 2017](https://fedoramagazine.org/fedora-24-eol/)                                                                     |
| Fedora         |   25    | [Dezember 2017](https://fedoramagazine.org/fedora-25-end-life/)                                                              |
| Fedora         |   26    | [Mai 2018](https://fedoramagazine.org/fedora-26-end-life/)                                                                   |
| Fedora         |   27    | [November 2018](https://fedoramagazine.org/fedora-27-end-of-life/)                                                           |
| Fedora         |   28    | [Mai 2019](https://fedoramagazine.org/fedora-28-end-of-life/)                                                                |
| openSUSE       |  42.1   | [Mai 2017](https://lists.opensuse.org/opensuse-security-announce/2017-05/msg00053.html)                                      |
| openSUSE       |  42.2   | [Januar 2018](https://lists.opensuse.org/opensuse-security-announce/2017-11/msg00066.html)                                  |
| openSUSE       |  42.3   | [Juli 2019](https://lists.opensuse.org/opensuse-security-announce/2019-07/msg00000.html)                                     |
| Ubuntu         |  14.04  | [April 2019](https://wiki.ubuntu.com/Releases)                                                                               |
| Ubuntu         |  16.10  | [Juli 2017](https://lists.ubuntu.com/archives/ubuntu-announce/2017-July/000223.html)                                         |
| Ubuntu         |  17.04  | [Januar 2018](https://lists.ubuntu.com/archives/ubuntu-announce/2018-January.txt)                                           |
| Ubuntu         |  17.10  | [Juli 2018](https://lists.ubuntu.com/archives/ubuntu-announce/2018-July/000232.html)                                         |
| Windows        |    7    | [Januar 2020](https://support.microsoft.com/help/4057281/windows-7-support-ended-on-january-14-2020)                        |
| Windows Server | 2008 R2 | [Januar 2020](https://support.microsoft.com/help/4456235/end-of-support-for-windows-server-2008-and-windows-server-2008-r2) |

## <a name="notes-on-licensing"></a>Hinweise zur Lizenzierung

PowerShell Core wird unter der [MIT-Lizenz][] veröffentlicht. Unter dieser Lizenz und ohne kostenpflichtige Supportvereinbarung gibt es für die Benutzer nur den [Communitysupport][]. Beim Support durch die Community gibt Microsoft keine Garantien zur Schnelligkeit der Reaktion auf Ihre Tickets oder der Problembehandlung.

## <a name="windows-powershell-compatibility"></a>Windows PowerShell-Kompatibilität

Der Supportlebenszyklus für PowerShell deckt keine Module ab, die außerhalb des PowerShell 7-Releasepakets bereitgestellt werden. Zum Beispiel wird das Modul `ActiveDirectory`, das als Teil von Windows Server bereitgestellt wird, nicht im Rahmen des [Windows-Supportlebenszyklus][] unterstützt.

PowerShell 7 verbessert die Kompatibilität mit vorhandenen PowerShell-Modulen, die für Windows PowerShell geschrieben wurden.
Weitere Informationen finden Sie im Artikel [about_Windows_Compatibility][] und in der [Modulkompatibilitätsliste][].

> [!NOTE]
> Das Modul [**WindowsPSModulePath**](https://www.powershellgallery.com/packages/WindowsPSModulePath) ist in PowerShell 7 nicht mehr erforderlich und wird nicht unterstützt.

## <a name="experimental-features"></a>Experimentelle Features

[Experimentelle Features][] sind auf [Communitysupport](#community-support) begrenzt.

## <a name="security-servicing-criteria"></a>Kriterien für die Sicherheitswartung

PowerShell folgt den [Microsoft-Kriterien für die Sicherheitswartung für Windows][].
In der folgenden Tabelle sind die Features aufgeführt, die die Kriterien für die Sicherheitswartung erfüllen, und diejenigen, die dies nicht tun.

| Funktion                          | type             |
|----------------------------------|------------------|
| Ausführungsrichtlinie                 | Tiefgehende Verteidigung |
| Systemsperrung mit AppLocker | Tiefgehende Verteidigung |
| Systemsperrung mit WDAC      | Sicherheitsfeature |

## <a name="release-history"></a>Releaseverlauf

Die folgende Tabelle enthält die Hauptversionen von PowerShell im Zeitverlauf. Diese Tabelle wird als historische Referenz bereitgestellt. Sie eignet sich nicht zur Bestimmung des Supportlebenszyklus.

|         Version          | Veröffentlichungsdatum |                                                                     Hinweis                                                                      |
| ------------------------ | :----------: | --------------------------------------------------------------------------------------------------------------------------------------------- |
| PowerShell 7.1 (aktuell) |   Nov. 2020   | Basiert auf .NET Core 5.0 (aktuell)                                                                                                              |
| PowerShell 7.0 (LTS)     |   März 2020   | Basiert auf .NET Core 3.1 (LTS).                                                                                                                  |
| PowerShell 6.0           |   Januar 2018   | Erstes Release, basiert auf .NET Core 2.1. Installierbar unter Windows, Linux und macOS.                                                              |
| PowerShell 5.1           |   August 2016   | Veröffentlicht in Windows 10 Anniversary Update und Windows Server 2016.                                                                             |
| PowerShell 5.0           |   Februar 2016   | Veröffentlicht in Windows Management Framework (WMF) 5.0.                                                                                            |
| PowerShell 4.0           |   Oktober 2013   | Integriert in Windows 8.1 und Windows Server 2012 R2. Installierbar unter Windows 7 SP1, Windows Server 2008 R2 SP1 und Windows Server 2012. |
| PowerShell 3.0           |   Oktober 2012   | Integriert in Windows 8 und Windows Server 2012. Installierbar unter Windows 7 SP1, Windows Server 2008 SP1 und Windows Server 2008 R2 SP1.  |
| PowerShell 2.0           |   Juli 2009   | Integriert in Windows 7 und Windows Server 2008 R2. Installierbar unter Windows XP SP3, Windows Server 2003 SP2 und Windows Vista SP1.            |
| PowerShell 1.0           |   November 2006   | Installierbar unter Windows XP SP2, Windows Server 2003 SP1 und Windows Vista. Optionale Komponente von Windows Server 2008.                          |

<!-- hyperlink references -->
[Kostenpflichtiger Support]: https://support.microsoft.com/hub/4343728/support-for-business
[enterprise-agreement]: https://www.microsoft.com/licensing/licensing-programs/enterprise.aspx
[assurance]: https://www.microsoft.com/licensing/licensing-programs/software-assurance-default.aspx
[Communitysupport]: /powershell/scripting/community/community-support
[pshub]: /powershell
[PowerShell Tech Community]: https://techcommunity.microsoft.com/t5/PowerShell/ct-p/WindowsPowerShell
[unterstützten Support]: https://support.microsoft.com/assistedsupportproducts
[modern]: https://support.microsoft.com/help/30881/modern-lifecycle-policy
[Long-Term]: https://dotnet.microsoft.com/platform/support/policy/dotnet-core
[lifecycle-chart]: ./images/modern-lifecycle.png
[semi-annual]: /windows-server/get-started/semi-annual-channel-overview
[MIT-Lizenz]: https://github.com/PowerShell/PowerShell/blob/master/LICENSE.txt
[about_Windows_Compatibility]: /powershell/module/microsoft.powershell.core/about/about_windows_powershell_compatibility
[Windows-Supportlebenszyklus]: https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet
[Modulkompatibilitätsliste]: /powershell/scripting/whats-new/module-compatibility
[WindowsPSModulePath]: https://www.powershellgallery.com/packages/WindowsPSModulePath/
[Experimentelle Features]: /powershell/module/microsoft.powershell.core/about/about_powershell_config#experimentalfeatures
[Microsoft-Kriterien für die Sicherheitswartung für Windows]: https://www.microsoft.com/msrc/windows-security-servicing-criteria.
