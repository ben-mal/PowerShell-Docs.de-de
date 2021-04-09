---
ms.date: 03/22/2021
keywords: powershell,cmdlet
title: Was ist PowerShell?
description: Dieser Artikel stellt eine Einführung in die PowerShell-Skriptumgebung und ihre Features dar.
ms.openlocfilehash: 3e1c2cae4b8d6507057ee8136265710a8dfe74f3
ms.sourcegitcommit: 719debaed3cc32ba463b1d4cc56a491d8ecbce26
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "105029688"
---
# <a name="what-is-powershell"></a>Was ist PowerShell?

PowerShell ist ein plattformübergreifendes Framework zur Aufgabenautomatisierung und Konfigurationsverwaltung, das aus einer Befehlszeilenshell und einer Skriptsprache besteht. PowerShell kann unter Windows, Linux und macOS ausgeführt werden.

## <a name="shell"></a>Shell

PowerShell ist eine moderne Befehlsshell, die die besten Features anderer beliebter Shells umfasst. Anders als die meisten Shells, die nur Text akzeptieren und zurückgeben, kann PowerShell auch .NET-Objekte akzeptieren und zurückgeben. Die Shell umfasst die folgenden Funktionen:

- Stabiler [Verlauf][] der Befehlszeile
- Vervollständigung mit der TAB-TASTE und Befehlsvorhersage (siehe [about_PSReadLine][])
- Unterstützung für [Aliase][] für Befehle und Parameter
- [Pipeline][] zum Verketten von Befehlen
- In die Konsole integriertes [Hilfesystem][], vergleichbar mit Manpages (`man`) unter Unix

## <a name="scripting-language"></a>"Skriptsprache"

Als Skriptsprache wird PowerShell häufig zum Automatisieren der Verwaltung von Systemen verwendet. Sie wird auch zum Erstellen, Testen und Bereitstellen von Lösungen verwendet – insbesondere in CI/CD-Umgebungen. PowerShell basiert auf der .NET Common Language Runtime (CLR). Alle Ein- und Ausgaben sind .NET-Objekte. Die Textausgabe muss nicht analysiert werden, um Informationen aus der Ausgabe zu extrahieren. Die Skriptsprache von PowerShell bietet die folgenden Funktionen:

- Erweiterbar durch [Funktionen][], [Klassen][], [Skripts][] und [Module][]
- Erweiterbares [Formatierungssystem][formatting] für einfache Ausgaben
- Erweiterbares [Typsystem][types] zum Erstellen dynamischer Typen
- Integrierte Unterstützung für gängige Datenformate wie [CSV][], [JSON][] und [XML][]

## <a name="configuration-management"></a>Konfigurationsverwaltung

Desired State Configuration ([DSC][]) ist ein Verwaltungsframework in PowerShell, das Ihnen das Verwalten Ihrer Unternehmensinfrastruktur per Konfiguration als Code ermöglicht. Sie können mit DSC folgende Aufgaben durchführen:

- Erstellen von deklarativen [Konfigurationen][] und benutzerdefinierten Skripts für wiederholbare Bereitstellungen
- Erzwingen von Konfigurationseinstellungen und Melden von Konfigurationsabweichungen
- Bereitstellen von Konfigurationen mithilfe von [Push- oder Pullmodellen][push-pull]

## <a name="next-steps"></a>Nächste Schritte

### <a name="getting-started"></a>Erste Schritte

Sind Sie neu bei PowerShell und wissen nicht, wo Sie anfangen sollen? Sehen Sie sich die folgenden Ressourcen an:

- [Installieren von PowerShell][install]
- [PowerShell 101][PS101]
- [Tutorials zu PowerShell][tutorials]
- [Learn-Module zu PowerShell][learn]

### <a name="powershell-in-action"></a>PowerShell in Aktion

Sehen Sie sich an, wie PowerShell in verschiedenen Szenarien und auf unterschiedlichen Plattformen verwendet wird.

- [PowerShell-Remoting über SSH][remoting]
- [Erste Schritte mit Azure PowerShell][azure]
- [Erstellen einer CI/CD-Pipeline mit DSC][devops]
- [Verwalten von Microsoft Exchange][exchange]

<!-- link references -->

[Verlauf]: /powershell/module/microsoft.powershell.core/about/about_history
[about_PSReadLine]: /powershell/module/psreadline/about/about_psreadline
[Aliase]: /powershell/module/microsoft.powershell.core/about/about_aliases
[Pipeline]: /powershell/module/microsoft.powershell.core/about/about_pipelines
[help]: /powershell/module/microsoft.powershell.core/get-help
[modules]: /powershell/module/microsoft.powershell.core/about/about_modules
[functions]: /powershell/module/microsoft.powershell.core/about/about_functions_advanced
[Klassen]: /powershell/module/microsoft.powershell.core/about/about_classes
[Skripts]: /powershell/module/microsoft.powershell.core/about/about_scripts
[formatting]: /powershell/module/microsoft.powershell.core/about/about_format.ps1xml
[types]: /powershell/module/microsoft.powershell.core/about/about_types.ps1xml
[CSV]: /powershell/module/microsoft.powershell.utility/convertfrom-csv
[JSON]: /powershell/module/microsoft.powershell.utility/convertfrom-json
[XML]: /powershell/module/microsoft.powershell.utility/convertto-xml
[configurations]: /powershell/scripting/dsc/configurations/configurations
[DSC]: /powershell/scripting/dsc/overview/dscforengineers
[push-pull]: /powershell/scripting/dsc/pull-server/enactingconfigurations
[install]: /powershell/scripting/install/installing-powershell
[PS101]: /powershell/scripting/learn/ps101/00-introduction
[tutorials]: /powershell/scripting/learn/tutorials/00-introduction
[learn]: /learn/browse/?terms=PowerShell
[azure]: /powershell/azure/get-started-azureps
[devops]: /azure/devops/pipelines/release/dsc-cicd
[exchange]: /powershell/exchange/exchange-management-shell
[remoting]: /powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core
