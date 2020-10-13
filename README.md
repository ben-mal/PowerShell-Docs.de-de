---
ms.openlocfilehash: f46b14e44c32ce31b4da1a14580fe03564bf9946
ms.sourcegitcommit: 0e18be0a2869beaa711ba3eca7a8a15514e5e962
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/09/2020
ms.locfileid: "91899265"
---
# <a name="microsoft-open-source-code-of-conduct"></a>Microsoft Open-Source-Verhaltenskodex

Für dieses Projekt gelten die Microsoft-Verhaltensregeln für Open Source ([Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/)). Weitere Informationen finden Sie unter [Code of Conduct FAQ (FAQ zum Verhaltenskodex)](https://opensource.microsoft.com/codeofconduct/faq/). Alternativ können Sie sich mit weiteren Fragen und Kommentaren an [opencode@microsoft.com](mailto:opencode@microsoft.com) wenden.

[live-badge]: https://powershell.visualstudio.com/PowerShell-Docs/_apis/build/status/PowerShell-Docs-CI?branchName=live
[staging-badge]: https://powershell.visualstudio.com/PowerShell-Docs/_apis/build/status/PowerShell-Docs-CI?branchName=staging

## <a name="build-status"></a>Buildstatus

|          Live-Branch          |           Staging-Branch            |
| :---------------------------- | :---------------------------------- |
| [![live-badge][]][live-badge] | [![staging-badge][]][staging-badge] |

## <a name="powershell-documentation"></a>PowerShell-Dokumentation

Willkommen im Repository „PowerShell-Docs“, der offiziellen PowerShell-Dokumentation.

## <a name="repository-structure"></a>Repository-Struktur

Nachfolgend werden die Hauptordner dieses Repositorys beschrieben.

- `.github`: enthält Konfigurationseinstellungen, die von GitHub für dieses Repository verwendet werden
- `.vscode`: enthält Konfigurationseinstellungen und empfohlene Erweiterungen für Visual Studio Code (VS Code)
- `assets`: enthält in der Dokumentation verlinkte Dateien, die heruntergeladen werden können
- `reference`: enthält die Dokumentation, die in [docs.microsoft.com]([https://docs.microsoft.com/powershell/scripting/) veröffentlicht wurde, einschließlich Referenzinhalten und konzeptionellen Inhalten
  - `5.1`: enthält die Cmdlet-Referenz und Hilfeartikel zu PowerShell 5.1
  - `6`: enthält die Cmdlet-Referenz und Hilfeartikel zu PowerShell 6
  - `7.0`: enthält die Cmdlet-Referenz und Hilfeartikel zu PowerShell 7.0
  - `7.1`: enthält die Cmdlet-Referenz und Hilfeartikel zu PowerShell 7.1
  - `bread`: enthält das Inhaltsverzeichnis, das für die Brotkrümelnavigation verwendet wird
  - `docs-conceptual`: enthält die konzeptionellen Artikel, die auf der Docs-Website veröffentlicht werden. In der Regel spiegelt die Ordnerstruktur das Inhaltsverzeichnis wider.
  - `mapping`: enthält die vom Buildsystem verwendete Konfiguration der Versionszuordnung
  - `media`: enthält Imagedateien, die in der Dokumentation verwendet werden. Die `docs-conceptual`-Inhalte enthalten häufig Medienordner. Weitere Informationen zur Verwendung von Images in der Dokumentation finden Sie im Leitfaden für Mitwirkende.
  - `module`: enthält die Markdownquelle für die Seite „Modulbrowser“
- `tests`: enthält die Pester-Tests, die vom Buildsystem verwendet werden
- `tools`: enthält andere Tools, die vom Buildsystem verwendet werden

> HINWEIS: Die Referenzinhalte (in den nummerierten Ordnern) werden verwendet, um die Webseiten auf der Dokumentationswebsite sowie die aktualisierbare Hilfe zu erstellen, die von PowerShell verwendet wird.
> Die Artikel im Ordner `docs-conceptual` werden nur auf der Docs-Website veröffentlicht.

## <a name="contributing"></a>Mitwirken

Wir freuen uns über öffentliche Beiträge zu diesem Repository. Verwenden Sie hierfür [Pullanforderungen](https://help.github.com/articles/using-pull-requests/) im _Staging_-Branch.
Hinweis: Sie müssen unsere [Lizenzvereinbarung für Mitwirkende](https://cla.microsoft.com/) unterschreiben, damit wir Ihre Pull Requests annehmen können. Dies ist eine einmalige Anforderung.

Weitere Informationen zu Beiträgen finden Sie in unserem [Handbuch für Mitwirkende](https://aka.ms/PSDocsContributor). Das Handbuch für Mitwirkende enthält ausführliche Informationen zum Erstellen von Beiträgen zur Dokumentation, Stil- und Formatierungsvorgaben sowie Vorschlagen von Tools. Verwenden Sie die Vorlagen für Probleme und Pullanforderungen, um die Dokumentation über Versionen hinweg konsistent zu halten.

## <a name="licenses"></a>Lizenzen

Es gibt zwei Lizenzdateien für dieses Projekt. Die MIT-Lizenz gilt für den Code, der in diesem Repository enthalten ist. Die Creative Commons-Lizenz gilt für die Dokumentation.
