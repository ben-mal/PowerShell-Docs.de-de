---
ms.date: 12/01/2020
title: Der PowerShell-Katalog | MSDN
description: Der PowerShell-Katalog ist das zentrale Repository für PowerShell-Module, Skripts und DSC-Ressourcen.
ms.openlocfilehash: f1ce6a8e2d5d72ac14cf3e4854626ef612d27891
ms.sourcegitcommit: 62282bb9c36fea3b4290b9263c1cd8e9ac216e29
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/01/2020
ms.locfileid: "96470314"
---
# <a name="the-powershell-gallery"></a><span data-ttu-id="1b327-103">Der PowerShell-Katalog | MSDN</span><span class="sxs-lookup"><span data-stu-id="1b327-103">The PowerShell Gallery</span></span>

<span data-ttu-id="1b327-104">Der PowerShell-Katalog ist das zentrale Repository für PowerShell-Inhalte.</span><span class="sxs-lookup"><span data-stu-id="1b327-104">The PowerShell Gallery is the central repository for PowerShell content.</span></span> <span data-ttu-id="1b327-105">Sie finden darin nützliche PowerShell-Module, die PowerShell-Befehle und Desired State Configuration-Ressourcen (DSC) enthalten.</span><span class="sxs-lookup"><span data-stu-id="1b327-105">In it, you can find useful PowerShell modules containing PowerShell commands and Desired State Configuration (DSC) resources.</span></span>
<span data-ttu-id="1b327-106">Sie finden dort auch PowerShell-Skripts, von denen einige PowerShell-Workflows enthalten, eine Reihe von Aufgaben umreißen und Sequenzierungen für diese Aufgaben bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="1b327-106">You can also find PowerShell scripts, some of which may contain PowerShell workflows, and which outline a set of tasks and provide sequencing for those tasks.</span></span> <span data-ttu-id="1b327-107">Einige dieser Pakete wurden von Microsoft erstellt, andere stammen aus der PowerShell-Community.</span><span class="sxs-lookup"><span data-stu-id="1b327-107">Some of these packages are authored by Microsoft, and others are authored by the PowerShell community.</span></span>

## <a name="powershellget-overview"></a><span data-ttu-id="1b327-108">Übersicht über PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="1b327-108">PowerShellGet Overview</span></span>

<span data-ttu-id="1b327-109">Das PowerShellGet-Modul enthält Cmdlets zum Ermitteln, Installieren, Aktualisieren und Veröffentlichen von PowerShell-Paketen mit Artefakten wie Modulen, DSC-Ressourcen, Rollenfunktionen und Skripts über den [PowerShell-Katalog](https://www.PowerShellGallery.com) und andere private Repositorys.</span><span class="sxs-lookup"><span data-stu-id="1b327-109">The PowerShellGet module contains cmdlets for discovering, installing, updating and publishing PowerShell packages which contain artifacts such as Modules, DSC Resources, Role Capabilities and Scripts from the [PowerShell Gallery](https://www.PowerShellGallery.com) and other private repositories.</span></span>

## <a name="getting-started-with-the-gallery"></a><span data-ttu-id="1b327-110">Erste Schritte mit dem Katalog</span><span class="sxs-lookup"><span data-stu-id="1b327-110">Getting Started with the Gallery</span></span>

<span data-ttu-id="1b327-111">Zur Installation von Paketen aus dem Katalog wird die neueste Version des PowerShellGet-Moduls benötigt.</span><span class="sxs-lookup"><span data-stu-id="1b327-111">Installing packages from the Gallery requires the latest version of the PowerShellGet module.</span></span> <span data-ttu-id="1b327-112">Eine vollständige Anleitung finden Sie unter [Installieren von PowerShellGet](installing-psget.md).</span><span class="sxs-lookup"><span data-stu-id="1b327-112">See [Installing PowerShellGet](installing-psget.md) for complete instructions.</span></span>

<span data-ttu-id="1b327-113">Sehen Sie sich die Seite [Erste Schritte](getting-started.md) an, um weitere Informationen zur Verwendung von PowerShellGet-Befehlen mit dem Katalog zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="1b327-113">Check out the [Getting Started](getting-started.md) page for more information on how to use PowerShellGet commands with the Gallery.</span></span> <span data-ttu-id="1b327-114">Sie können auch *Update-Help -Module PowerShellGet* ausführen, um die lokale Hilfe für diese Befehle zu installieren.</span><span class="sxs-lookup"><span data-stu-id="1b327-114">You can also run *Update-Help -Module PowerShellGet* to install local help for these commands.</span></span>

## <a name="supported-operating-systems"></a><span data-ttu-id="1b327-115">Unterstützte Betriebssysteme</span><span class="sxs-lookup"><span data-stu-id="1b327-115">Supported Operating Systems</span></span>

<span data-ttu-id="1b327-116">Für das **PowerShellGet**-Modul ist **PowerShell 3.0 oder neuer** erforderlich.</span><span class="sxs-lookup"><span data-stu-id="1b327-116">The **PowerShellGet** module requires **PowerShell 3.0 or newer**.</span></span>

<span data-ttu-id="1b327-117">Für **PowerShellGet** ist .NET Framework 4.5 oder höher erforderlich.</span><span class="sxs-lookup"><span data-stu-id="1b327-117">**PowerShellGet** requires .NET Framework 4.5 or above.</span></span> <span data-ttu-id="1b327-118">Weitere Informationen finden Sie unter [Installieren von .NET Framework für Entwickler](/dotnet/framework/install/guide-for-developers).</span><span class="sxs-lookup"><span data-stu-id="1b327-118">For more information, see [Install the .NET Framework for developers](/dotnet/framework/install/guide-for-developers).</span></span>

<span data-ttu-id="1b327-119">Da **PowerShell Core** plattformübergreifend ist – was bedeutet, dass es unter Windows, Linux und macOS funktioniert –, ist auch **PowerShellGet** auf diesen Systemen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="1b327-119">Since **PowerShell Core** is cross-platform and that means it works on Windows, Linux and MacOS, that also makes **PowerShellGet** available on those systems.</span></span> <span data-ttu-id="1b327-120">Eine vollständige Liste der von **PowerShell Core** unterstützten Systeme finden Sie unter [Installieren von PowerShell](/powershell/scripting/install/installing-powershell).</span><span class="sxs-lookup"><span data-stu-id="1b327-120">For a full list of systems supported by **PowerShell Core** see [Installing PowerShell](/powershell/scripting/install/installing-powershell).</span></span>

<span data-ttu-id="1b327-121">Viele Module, die im Katalog aufgeführt sind, unterstützen andere Betriebssysteme und haben zusätzliche Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="1b327-121">Many modules hosted in the gallery will support different OSes and have additional requirements.</span></span>
<span data-ttu-id="1b327-122">Weitere Informationen finden Sie in der Dokumentation der jeweiligen Module.</span><span class="sxs-lookup"><span data-stu-id="1b327-122">Please refer to the documentation for the modules for more information.</span></span>

## <a name="got-a-question-have-feedback"></a><span data-ttu-id="1b327-123">Sie haben eine Frage?</span><span class="sxs-lookup"><span data-stu-id="1b327-123">Got a question?</span></span> <span data-ttu-id="1b327-124">Feedback?</span><span class="sxs-lookup"><span data-stu-id="1b327-124">Have feedback?</span></span>

<span data-ttu-id="1b327-125">Weitere Informationen zum PowerShell-Katalog und zu PowerShellGet finden Sie auf der Seite [Erste Schritte](getting-started.md).</span><span class="sxs-lookup"><span data-stu-id="1b327-125">More information about the PowerShell Gallery and PowerShellGet can be found in the [Getting Started](getting-started.md) page.</span></span>

<span data-ttu-id="1b327-126">Informationen zum aktuellen Status der Dienste des PowerShell-Katalogs finden Sie auf der GitHub-Seite [PowerShell Gallery Status](https://github.com/PowerShell/PowerShellGallery/blob/master/psgallery_status.md).</span><span class="sxs-lookup"><span data-stu-id="1b327-126">To see the current status of the PowerShell Gallery services, see the [PowerShell Gallery Status](https://github.com/PowerShell/PowerShellGallery/blob/master/psgallery_status.md) page on GitHub.</span></span>

<span data-ttu-id="1b327-127">Geben Sie Feedback, und melden Sie Issues im [GitHub-Repository](https://github.com/PowerShell/PowerShellGallery/issues).</span><span class="sxs-lookup"><span data-stu-id="1b327-127">Please provide feedback and report issues the [GitHub repository](https://github.com/PowerShell/PowerShellGallery/issues).</span></span>
