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
# <a name="what-is-powershell"></a><span data-ttu-id="c50ed-104">Was ist PowerShell?</span><span class="sxs-lookup"><span data-stu-id="c50ed-104">What is PowerShell?</span></span>

<span data-ttu-id="c50ed-105">PowerShell ist ein plattformübergreifendes Framework zur Aufgabenautomatisierung und Konfigurationsverwaltung, das aus einer Befehlszeilenshell und einer Skriptsprache besteht.</span><span class="sxs-lookup"><span data-stu-id="c50ed-105">PowerShell is a cross-platform task automation solution made up of a command-line shell, a scripting language, and a configuration management framework.</span></span> <span data-ttu-id="c50ed-106">PowerShell kann unter Windows, Linux und macOS ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="c50ed-106">PowerShell runs on Windows, Linux, and macOS.</span></span>

## <a name="shell"></a><span data-ttu-id="c50ed-107">Shell</span><span class="sxs-lookup"><span data-stu-id="c50ed-107">Shell</span></span>

<span data-ttu-id="c50ed-108">PowerShell ist eine moderne Befehlsshell, die die besten Features anderer beliebter Shells umfasst.</span><span class="sxs-lookup"><span data-stu-id="c50ed-108">PowerShell is modern command shell that includes the best features of other popular shells.</span></span> <span data-ttu-id="c50ed-109">Anders als die meisten Shells, die nur Text akzeptieren und zurückgeben, kann PowerShell auch .NET-Objekte akzeptieren und zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="c50ed-109">Unlike most shells that only accept and return text, PowerShell accepts and returns .NET objects.</span></span> <span data-ttu-id="c50ed-110">Die Shell umfasst die folgenden Funktionen:</span><span class="sxs-lookup"><span data-stu-id="c50ed-110">The shell includes the following features:</span></span>

- <span data-ttu-id="c50ed-111">Stabiler [Verlauf][] der Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="c50ed-111">Robust command-line [history][]</span></span>
- <span data-ttu-id="c50ed-112">Vervollständigung mit der TAB-TASTE und Befehlsvorhersage (siehe [about_PSReadLine][])</span><span class="sxs-lookup"><span data-stu-id="c50ed-112">Tab completion and command prediction (See [about_PSReadLine][])</span></span>
- <span data-ttu-id="c50ed-113">Unterstützung für [Aliase][] für Befehle und Parameter</span><span class="sxs-lookup"><span data-stu-id="c50ed-113">Supports command and parameter [aliases][]</span></span>
- <span data-ttu-id="c50ed-114">[Pipeline][] zum Verketten von Befehlen</span><span class="sxs-lookup"><span data-stu-id="c50ed-114">[Pipeline][] for chaining commands</span></span>
- <span data-ttu-id="c50ed-115">In die Konsole integriertes [Hilfesystem][], vergleichbar mit Manpages (`man`) unter Unix</span><span class="sxs-lookup"><span data-stu-id="c50ed-115">In-console [help][] system, similar to Unix `man` pages</span></span>

## <a name="scripting-language"></a><span data-ttu-id="c50ed-116">"Skriptsprache"</span><span class="sxs-lookup"><span data-stu-id="c50ed-116">Scripting language</span></span>

<span data-ttu-id="c50ed-117">Als Skriptsprache wird PowerShell häufig zum Automatisieren der Verwaltung von Systemen verwendet.</span><span class="sxs-lookup"><span data-stu-id="c50ed-117">As a scripting language, PowerShell is commonly used for automating the management of systems.</span></span> <span data-ttu-id="c50ed-118">Sie wird auch zum Erstellen, Testen und Bereitstellen von Lösungen verwendet – insbesondere in CI/CD-Umgebungen.</span><span class="sxs-lookup"><span data-stu-id="c50ed-118">It is also used to build, test, and deploy solutions, often in CI/CD environments.</span></span> <span data-ttu-id="c50ed-119">PowerShell basiert auf der .NET Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="c50ed-119">PowerShell is built on the .NET Common Language Runtime (CLR).</span></span> <span data-ttu-id="c50ed-120">Alle Ein- und Ausgaben sind .NET-Objekte.</span><span class="sxs-lookup"><span data-stu-id="c50ed-120">All inputs and outputs are .NET objects.</span></span> <span data-ttu-id="c50ed-121">Die Textausgabe muss nicht analysiert werden, um Informationen aus der Ausgabe zu extrahieren.</span><span class="sxs-lookup"><span data-stu-id="c50ed-121">No need to parse text output to extract information from output.</span></span> <span data-ttu-id="c50ed-122">Die Skriptsprache von PowerShell bietet die folgenden Funktionen:</span><span class="sxs-lookup"><span data-stu-id="c50ed-122">The PowerShell scripting language includes the following features:</span></span>

- <span data-ttu-id="c50ed-123">Erweiterbar durch [Funktionen][], [Klassen][], [Skripts][] und [Module][]</span><span class="sxs-lookup"><span data-stu-id="c50ed-123">Extensible through [functions][], [classes][], [scripts][], and [modules][]</span></span>
- <span data-ttu-id="c50ed-124">Erweiterbares [Formatierungssystem][formatting] für einfache Ausgaben</span><span class="sxs-lookup"><span data-stu-id="c50ed-124">Extensible [formatting system][formatting] for easy output</span></span>
- <span data-ttu-id="c50ed-125">Erweiterbares [Typsystem][types] zum Erstellen dynamischer Typen</span><span class="sxs-lookup"><span data-stu-id="c50ed-125">Extensible [type system][types] for creating dynamic types</span></span>
- <span data-ttu-id="c50ed-126">Integrierte Unterstützung für gängige Datenformate wie [CSV][], [JSON][] und [XML][]</span><span class="sxs-lookup"><span data-stu-id="c50ed-126">Built-in support for common data formats like [CSV][], [JSON][], and [XML][]</span></span>

## <a name="configuration-management"></a><span data-ttu-id="c50ed-127">Konfigurationsverwaltung</span><span class="sxs-lookup"><span data-stu-id="c50ed-127">Configuration management</span></span>

<span data-ttu-id="c50ed-128">Desired State Configuration ([DSC][]) ist ein Verwaltungsframework in PowerShell, das Ihnen das Verwalten Ihrer Unternehmensinfrastruktur per Konfiguration als Code ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="c50ed-128">PowerShell Desired State Configuration ([DSC][]) is a management framework in PowerShell that enables you to manage your enterprise infrastructure with configuration as code.</span></span> <span data-ttu-id="c50ed-129">Sie können mit DSC folgende Aufgaben durchführen:</span><span class="sxs-lookup"><span data-stu-id="c50ed-129">With DSC, you can:</span></span>

- <span data-ttu-id="c50ed-130">Erstellen von deklarativen [Konfigurationen][] und benutzerdefinierten Skripts für wiederholbare Bereitstellungen</span><span class="sxs-lookup"><span data-stu-id="c50ed-130">Create declarative [configurations][] and custom scripts for repeatable deployments</span></span>
- <span data-ttu-id="c50ed-131">Erzwingen von Konfigurationseinstellungen und Melden von Konfigurationsabweichungen</span><span class="sxs-lookup"><span data-stu-id="c50ed-131">Enforce configuration settings and report on configuration drift</span></span>
- <span data-ttu-id="c50ed-132">Bereitstellen von Konfigurationen mithilfe von [Push- oder Pullmodellen][push-pull]</span><span class="sxs-lookup"><span data-stu-id="c50ed-132">Deploy configuration using [push or pull][push-pull] models</span></span>

## <a name="next-steps"></a><span data-ttu-id="c50ed-133">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="c50ed-133">Next steps</span></span>

### <a name="getting-started"></a><span data-ttu-id="c50ed-134">Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="c50ed-134">Getting started</span></span>

<span data-ttu-id="c50ed-135">Sind Sie neu bei PowerShell und wissen nicht, wo Sie anfangen sollen?</span><span class="sxs-lookup"><span data-stu-id="c50ed-135">Are you new to PowerShell and don't know where to start?</span></span> <span data-ttu-id="c50ed-136">Sehen Sie sich die folgenden Ressourcen an:</span><span class="sxs-lookup"><span data-stu-id="c50ed-136">Take a look at these resources.</span></span>

- <span data-ttu-id="c50ed-137">[Installieren von PowerShell][install]</span><span class="sxs-lookup"><span data-stu-id="c50ed-137">[Installing PowerShell][install]</span></span>
- <span data-ttu-id="c50ed-138">[PowerShell 101][PS101]</span><span class="sxs-lookup"><span data-stu-id="c50ed-138">[PowerShell 101][PS101]</span></span>
- <span data-ttu-id="c50ed-139">[Tutorials zu PowerShell][tutorials]</span><span class="sxs-lookup"><span data-stu-id="c50ed-139">[PowerShell Bits tutorials][tutorials]</span></span>
- <span data-ttu-id="c50ed-140">[Learn-Module zu PowerShell][learn]</span><span class="sxs-lookup"><span data-stu-id="c50ed-140">[PowerShell Learn modules][learn]</span></span>

### <a name="powershell-in-action"></a><span data-ttu-id="c50ed-141">PowerShell in Aktion</span><span class="sxs-lookup"><span data-stu-id="c50ed-141">PowerShell in action</span></span>

<span data-ttu-id="c50ed-142">Sehen Sie sich an, wie PowerShell in verschiedenen Szenarien und auf unterschiedlichen Plattformen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c50ed-142">Take a look at how PowerShell is being used in different scenarios and on different platforms.</span></span>

- <span data-ttu-id="c50ed-143">[PowerShell-Remoting über SSH][remoting]</span><span class="sxs-lookup"><span data-stu-id="c50ed-143">[PowerShell remoting over SSH][remoting]</span></span>
- <span data-ttu-id="c50ed-144">[Erste Schritte mit Azure PowerShell][azure]</span><span class="sxs-lookup"><span data-stu-id="c50ed-144">[Getting started with Azure PowerShell][azure]</span></span>
- <span data-ttu-id="c50ed-145">[Erstellen einer CI/CD-Pipeline mit DSC][devops]</span><span class="sxs-lookup"><span data-stu-id="c50ed-145">[Building a CI/CD pipeline with DSC][devops]</span></span>
- <span data-ttu-id="c50ed-146">[Verwalten von Microsoft Exchange][exchange]</span><span class="sxs-lookup"><span data-stu-id="c50ed-146">[Managing Microsoft Exchange][exchange]</span></span>

<!-- link references -->

[Verlauf]: /powershell/module/microsoft.powershell.core/about/about_history
[history]: /powershell/module/microsoft.powershell.core/about/about_history
[about_PSReadLine]: /powershell/module/psreadline/about/about_psreadline
[Aliase]: /powershell/module/microsoft.powershell.core/about/about_aliases
[aliases]: /powershell/module/microsoft.powershell.core/about/about_aliases
[Pipeline]: /powershell/module/microsoft.powershell.core/about/about_pipelines
[help]: /powershell/module/microsoft.powershell.core/get-help
[modules]: /powershell/module/microsoft.powershell.core/about/about_modules
[functions]: /powershell/module/microsoft.powershell.core/about/about_functions_advanced
[Klassen]: /powershell/module/microsoft.powershell.core/about/about_classes
[classes]: /powershell/module/microsoft.powershell.core/about/about_classes
[Skripts]: /powershell/module/microsoft.powershell.core/about/about_scripts
[scripts]: /powershell/module/microsoft.powershell.core/about/about_scripts
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
