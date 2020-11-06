---
ms.date: 07/08/2020
keywords: DSC,PowerShell,Konfiguration,Setup,Einrichtung
title: Erstellen von benutzerdefinierten Windows PowerShell DSC-Ressourcen
description: Dieser Artikel enthält einen Überblick über die Entwicklung von Ressourcen sowie Links zu Artikeln mit spezifischen Informationen und Beispielen.
ms.openlocfilehash: ff9a0c8ae10583155217fbeccc62e6e1c94f9a11
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92656396"
---
# <a name="build-custom-windows-powershell-desired-state-configuration-resources"></a><span data-ttu-id="e79cb-104">Erstellen von benutzerdefinierten Windows PowerShell DSC-Ressourcen</span><span class="sxs-lookup"><span data-stu-id="e79cb-104">Build Custom Windows PowerShell Desired State Configuration Resources</span></span>

> <span data-ttu-id="e79cb-105">Gilt für: Windows PowerShell 4.0, Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="e79cb-105">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

<span data-ttu-id="e79cb-106">Windows PowerShell DSC verfügt über integrierte Ressourcen, mit denen Sie Ihre Umgebung konfigurieren können</span><span class="sxs-lookup"><span data-stu-id="e79cb-106">Windows PowerShell Desired State Configuration (DSC) has built-in resources that you can use to configure your environment.</span></span> <span data-ttu-id="e79cb-107">Dieser Artikel enthält einen Überblick über die Entwicklung von Ressourcen sowie Links zu Artikeln mit spezifischen Informationen und Beispielen.</span><span class="sxs-lookup"><span data-stu-id="e79cb-107">This article provides an overview of developing resources and links to articles with specific information and examples.</span></span>

## <a name="dsc-resource-components"></a><span data-ttu-id="e79cb-108">Komponenten der DSC-Ressourcen</span><span class="sxs-lookup"><span data-stu-id="e79cb-108">DSC resource components</span></span>

<span data-ttu-id="e79cb-109">Eine DSC-Ressource ist ein Windows PowerShell-Modul.</span><span class="sxs-lookup"><span data-stu-id="e79cb-109">A DSC resource is a Windows PowerShell module.</span></span> <span data-ttu-id="e79cb-110">Das Modul enthält das Schema (die Definition der konfigurierbaren Eigenschaften) und die Implementierung (den Code, der die eigentliche durch eine Konfiguration angegebene Arbeit ausführt) für die Ressource.</span><span class="sxs-lookup"><span data-stu-id="e79cb-110">The module contains both the schema (the definition of the configurable properties) and the implementation (the code that does the actual work specified by a configuration) for the resource.</span></span> <span data-ttu-id="e79cb-111">Ein DSC-Ressourcenschema kann in einer MOF-Datei definiert werden, und die Implementierung erfolgt durch ein Skriptmodul.</span><span class="sxs-lookup"><span data-stu-id="e79cb-111">A DSC resource schema can be defined in a MOF file, and the implementation is performed by a script module.</span></span> <span data-ttu-id="e79cb-112">Beginnend mit der Unterstützung von PowerShell-Klassen in Version 5 können das Schema und die Implementierung in einer Klasse definiert werden.</span><span class="sxs-lookup"><span data-stu-id="e79cb-112">Beginning with the support of PowerShell classes in version 5, the schema and implementation can both be defined in a class.</span></span> <span data-ttu-id="e79cb-113">In den folgenden Artikeln wird die Erstellung von DSC-Ressourcen ausführlicher beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e79cb-113">The following articles describe in more detail how to create DSC resources.</span></span>

- [<span data-ttu-id="e79cb-114">Schreiben einer benutzerdefinierten DSC-Ressource mit MOF</span><span class="sxs-lookup"><span data-stu-id="e79cb-114">Writing a custom DSC resource with MOF</span></span>](authoringResourceMOF.md)
- [<span data-ttu-id="e79cb-115">Implementieren einer DSC-Ressource in C#</span><span class="sxs-lookup"><span data-stu-id="e79cb-115">Implementing a DSC resource in C#</span></span>](authoringResourceMofCS.md)
- [<span data-ttu-id="e79cb-116">Schreiben einer benutzerdefinierten DSC-Ressource mit PowerShell-Klassen</span><span class="sxs-lookup"><span data-stu-id="e79cb-116">Writing a custom DSC resource with PowerShell classes</span></span>](authoringResourceClass.md)
- [<span data-ttu-id="e79cb-117">Zusammengesetzte Ressourcen: Verwenden einer DSC-Konfiguration als Ressource</span><span class="sxs-lookup"><span data-stu-id="e79cb-117">Composite resources: Using a DSC configuration as a resource</span></span>](authoringResourceComposite.md)
- [<span data-ttu-id="e79cb-118">Verwenden des Ressourcen-Designers</span><span class="sxs-lookup"><span data-stu-id="e79cb-118">Using the Resource Designer tool</span></span>](authoringResourceMofDesigner.md)
