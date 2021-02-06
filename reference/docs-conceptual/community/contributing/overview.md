---
title: Mitwirkung an der PowerShell-Dokumentation
description: In diesem Artikel werden die Schritte beschrieben, die erforderlich sind, um zur PowerShell-Dokumentation beizutragen.
ms.date: 12/09/2020
ms.topic: conceptual
ms.openlocfilehash: 9fbdafa023eac80340437f30d2d6925a1a4ed3cb
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "99601688"
---
# <a name="contributing-to-powershell-documentation"></a><span data-ttu-id="ec6cc-103">Mitwirkung an der PowerShell-Dokumentation</span><span class="sxs-lookup"><span data-stu-id="ec6cc-103">Contributing to PowerShell documentation</span></span>

<span data-ttu-id="ec6cc-104">Vielen Dank für Ihre Unterstützung von PowerShell!</span><span class="sxs-lookup"><span data-stu-id="ec6cc-104">Thank you for your support of PowerShell!</span></span>

<span data-ttu-id="ec6cc-105">Der Leitfaden für Mitwirkende ist eine Auflistung von Artikeln, in denen die Tools und Prozesse beschrieben werden, die zum Erstellen der Dokumentation bei Microsoft verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ec6cc-105">The Contributor's Guide is a collection of articles that describe the tools and processes we use to create documentation at Microsoft.</span></span> <span data-ttu-id="ec6cc-106">Einige dieser Leitfäden enthalten Informationen, die für alle Dokumentationssätze gelten, die auf [docs.microsoft.com][docs] veröffentlicht werden.</span><span class="sxs-lookup"><span data-stu-id="ec6cc-106">Some of these guides cover information that is common to any documentation set published to [docs.microsoft.com][docs].</span></span> <span data-ttu-id="ec6cc-107">Einige der Leitfäden sind spezifisch für die Erstellung von Dokumentation für PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ec6cc-107">Some of the guides are specific to how we write documentation for PowerShell.</span></span>

<span data-ttu-id="ec6cc-108">Die allgemeinen Artikel finden Sie in unserer zentralen [Handbuch für Mitwirkende][contribute].</span><span class="sxs-lookup"><span data-stu-id="ec6cc-108">The common articles are available in our centralized [Contributor's Guide][contribute].</span></span> <span data-ttu-id="ec6cc-109">Die PowerShell-spezifischen Anleitungen sind hier verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ec6cc-109">The PowerShell-specific guides are available here.</span></span>

## <a name="ways-to-contribute"></a><span data-ttu-id="ec6cc-110">Möglichkeiten zur Mitwirkung</span><span class="sxs-lookup"><span data-stu-id="ec6cc-110">Ways to contribute</span></span>

<span data-ttu-id="ec6cc-111">Es gibt zwei Möglichkeiten zur Mitwirkung.</span><span class="sxs-lookup"><span data-stu-id="ec6cc-111">There are two ways to contribute.</span></span> <span data-ttu-id="ec6cc-112">Beide Formen sind für uns hilfreich.</span><span class="sxs-lookup"><span data-stu-id="ec6cc-112">Both contributions are valuable to us.</span></span>

- <span data-ttu-id="ec6cc-113">Das [Einreichen von Problemen][file-an-issue] hilft uns, Probleme und Lücken in unserer Dokumentation zu erkennen.</span><span class="sxs-lookup"><span data-stu-id="ec6cc-113">[Filing issues][file-an-issue] helps us identify problems and gaps in our documentation.</span></span> <span data-ttu-id="ec6cc-114">Manchmal sind die Probleme schwierig zu beheben und erfordern weitere Untersuchungen und Recherchen.</span><span class="sxs-lookup"><span data-stu-id="ec6cc-114">Sometimes the issues are difficult to resolve, requiring more investigation and research.</span></span> <span data-ttu-id="ec6cc-115">Der Issueprozess ermöglicht es uns, eine Unterhaltung über das Problem zu führen und eine befriedigende Lösung zu entwickeln.</span><span class="sxs-lookup"><span data-stu-id="ec6cc-115">The issue process allows us to have a conversation about the problem and develop a satisfactory resolution.</span></span>

- <span data-ttu-id="ec6cc-116">Das [Senden eines Pull Request](pull-requests.md) zum Hinzufügen oder Ändern von Inhalten ist ein ausführlichere Prozess.</span><span class="sxs-lookup"><span data-stu-id="ec6cc-116">[Submitting a pull request](pull-requests.md) to add or change content is a more involved process.</span></span>
  <span data-ttu-id="ec6cc-117">Die folgenden Informationen beschreiben die Tools, Prozesse und Standards für das Einreichen von Inhalten für die Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="ec6cc-117">The following information outlines the tools, processes, and standards for submitting content to the documentation.</span></span>

## <a name="prepare-to-make-a-contribution"></a><span data-ttu-id="ec6cc-118">Vorbereiten der Mitwirkung</span><span class="sxs-lookup"><span data-stu-id="ec6cc-118">Prepare to make a contribution</span></span>

<span data-ttu-id="ec6cc-119">Für die Mitwirkung an der Dokumentation ist ein GitHub-Konto erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ec6cc-119">Contributing to the documentation requires a GitHub account.</span></span> <span data-ttu-id="ec6cc-120">Verwenden Sie die folgende Checkliste, um die Tools zu installieren und zu konfigurieren, die Sie zum Erstellen von Beiträgen benötigen</span><span class="sxs-lookup"><span data-stu-id="ec6cc-120">Use the following checklist to install and configure the tools you need to make contributions.</span></span>

1. [<span data-ttu-id="ec6cc-121">Registrieren Sie sich für GitHub</span><span class="sxs-lookup"><span data-stu-id="ec6cc-121">Sign up for GitHub</span></span>](/contribute/get-started-setup-github)
1. [<span data-ttu-id="ec6cc-122">Installieren Sie die Git- und Markdown-Tools</span><span class="sxs-lookup"><span data-stu-id="ec6cc-122">Install Git and Markdown tools</span></span>](/contribute/get-started-setup-tools)
1. <span data-ttu-id="ec6cc-123">[Installieren Sie das Docs Authoring Pack](/contribute/how-to-write-docs-auth-pack) (Paket zur Dokumenterstellung)</span><span class="sxs-lookup"><span data-stu-id="ec6cc-123">[Install the Docs Authoring Pack](/contribute/how-to-write-docs-auth-pack)</span></span>
1. <span data-ttu-id="ec6cc-124">[Installieren Sie Posh-Git][posh-git] – nicht erforderlich, aber empfehlenswert</span><span class="sxs-lookup"><span data-stu-id="ec6cc-124">[Install Posh-Git][posh-git] - not required but recommended</span></span>
1. [<span data-ttu-id="ec6cc-125">Richten Sie ein lokales Git-Repository ein</span><span class="sxs-lookup"><span data-stu-id="ec6cc-125">Set up a local Git repository</span></span>](/contribute/get-started-setup-local)
1. [<span data-ttu-id="ec6cc-126">Arbeiten Sie die Grundlagen von Git und GitHub durch</span><span class="sxs-lookup"><span data-stu-id="ec6cc-126">Review Git and GitHub fundamentals</span></span>](/contribute/git-github-fundamentals)

## <a name="get-started-writing-docs"></a><span data-ttu-id="ec6cc-127">Erste Schritte mit dem Schreiben von Dokumentation</span><span class="sxs-lookup"><span data-stu-id="ec6cc-127">Get started writing docs</span></span>

<span data-ttu-id="ec6cc-128">Es gibt zwei Möglichkeiten, Änderungen an der-Dokumentation beizutragen:</span><span class="sxs-lookup"><span data-stu-id="ec6cc-128">There are two ways to contribute changes to the documentation:</span></span>

1. [<span data-ttu-id="ec6cc-129">Schnelle Bearbeitung vorhandener Dokumente</span><span class="sxs-lookup"><span data-stu-id="ec6cc-129">Quick edits to existing docs</span></span>](/contribute/#quick-edits-to-existing-documents)
   - <span data-ttu-id="ec6cc-130">Kleinere Korrekturen, Korrektur von Tippfehlern oder kleine Ergänzungen</span><span class="sxs-lookup"><span data-stu-id="ec6cc-130">Minor corrections, fixing typos, or small additions</span></span>
1. [<span data-ttu-id="ec6cc-131">Vollständiger GitHub-Workflow für Dokumente</span><span class="sxs-lookup"><span data-stu-id="ec6cc-131">Full GitHub workflow for docs</span></span>](/contribute/how-to-write-workflows-major)
   - <span data-ttu-id="ec6cc-132">Große Änderungen, mehrere Versionen, Hinzufügen oder Ändern von Bildern oder Einreichung neuer Artikel</span><span class="sxs-lookup"><span data-stu-id="ec6cc-132">large changes, multiple versions, adding or changing images, or contributing new articles</span></span>

<span data-ttu-id="ec6cc-133">Lesen Sie darüber hinaus den Abschnitt [Writing essentials](/contribute/style-quick-start) (Grundlagen des Schreibens) des zentralen Handbuchs für Mitwirkende.</span><span class="sxs-lookup"><span data-stu-id="ec6cc-133">Also, read the [Writing essentials](/contribute/style-quick-start) section of the centralized Contributor's Guide.</span></span> <span data-ttu-id="ec6cc-134">Eine weitere hervorragende Ressource stellt der [Microsoft Writing Style Guide][style-guide] dar.</span><span class="sxs-lookup"><span data-stu-id="ec6cc-134">Another excellent resource is the [Microsoft Writing Style Guide][style-guide].</span></span> <span data-ttu-id="ec6cc-135">Das Ziel des Microsoft Writing Style Guide besteht darin, Redakteure, technische Autoren, Entwickler, Marketingfachleute und alle anderen Personen in der IT beim Schreiben besserer Inhalte zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="ec6cc-135">The goal of the Microsoft Writing Style Guide is to help editors, technical writers, developers, marketers, and anyone else in IT write better content.</span></span>

<span data-ttu-id="ec6cc-136">Kleinere Korrekturen oder Klarstellungen an Dokumentation und Codebeispielen in öffentlichen Repositorys werden durch die [Nutzungsbedingungen][terms-of-use] von docs.microsoft.com abgedeckt.</span><span class="sxs-lookup"><span data-stu-id="ec6cc-136">Minor corrections or clarifications to documentation and code examples in public repositories are covered by the docs.microsoft.com [Terms of Use][terms-of-use].</span></span>

<span data-ttu-id="ec6cc-137">Verwenden Sie den vollständigen GitHub-Workflow, wenn Sie erhebliche Änderungen vornehmen.</span><span class="sxs-lookup"><span data-stu-id="ec6cc-137">Use the full GitHub workflow when you're making significant changes.</span></span> <span data-ttu-id="ec6cc-138">Wenn Sie kein Microsoft-Mitarbeiter sind, führen erhebliche Änderungen zur Generierung eines Pull Requests, in dem Sie aufgefordert werden, online eine [Contribution Licensing Agreement (CLA)][cla] zu übermitteln.</span><span class="sxs-lookup"><span data-stu-id="ec6cc-138">If you're not an employee of Microsoft, significant changes generate a comment in the pull request that asks you to submit an online [Contribution Licensing Agreement (CLA)][cla].</span></span> <span data-ttu-id="ec6cc-139">Sie müssen das Onlineformular ausfüllen, damit wir Ihren Pull Request überprüfen oder akzeptieren können.</span><span class="sxs-lookup"><span data-stu-id="ec6cc-139">We need you to complete the online form before we can review or accept your pull request.</span></span>

## <a name="code-of-conduct"></a><span data-ttu-id="ec6cc-140">Verhaltensregeln</span><span class="sxs-lookup"><span data-stu-id="ec6cc-140">Code of conduct</span></span>

<span data-ttu-id="ec6cc-141">Für alle Repositorys, die auf docs.microsoft.com- veröffentlichen, gilt der [Microsoft Open Source-Verhaltenskodex](https://opensource.microsoft.com/codeofconduct/) oder der [.NET Foundation-Verhaltenskodex](https://dotnetfoundation.org/code-of-conduct).</span><span class="sxs-lookup"><span data-stu-id="ec6cc-141">All repositories that publish to docs.microsoft.com have adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/) or the [.NET Foundation Code of Conduct](https://dotnetfoundation.org/code-of-conduct).</span></span> <span data-ttu-id="ec6cc-142">Weitere Informationen finden Sie unter [Häufig gestellte Fragen zum Verhaltenskodex](https://opensource.microsoft.com/codeofconduct/faq/).</span><span class="sxs-lookup"><span data-stu-id="ec6cc-142">For more information, see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/).</span></span>

## <a name="next-steps"></a><span data-ttu-id="ec6cc-143">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="ec6cc-143">Next steps</span></span>

<span data-ttu-id="ec6cc-144">In den folgenden Artikeln werden spezifische Informationen zur PowerShell-Dokumentation behandelt.</span><span class="sxs-lookup"><span data-stu-id="ec6cc-144">The following articles cover information specific to PowerShell documentation.</span></span> <span data-ttu-id="ec6cc-145">Wenn es Überschneidungen mit den allgemeinen Anleitungen im zentralen Handbuch für Mitwirkende gibt, weisen wir darauf hin, wie sich diese Regeln für PowerShell-Inhalte unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="ec6cc-145">Where there's overlap with the guidance in the centralized Contributor's Guide, we call out how those rules differ for the PowerShell content.</span></span>

<span data-ttu-id="ec6cc-146">Lesen Sie die folgenden Dokumente:</span><span class="sxs-lookup"><span data-stu-id="ec6cc-146">Review the following documents:</span></span>

- [<span data-ttu-id="ec6cc-147">Anlegen eines Eintrags</span><span class="sxs-lookup"><span data-stu-id="ec6cc-147">How to file an issue</span></span>](file-an-issue.md)
- [<span data-ttu-id="ec6cc-148">Erste Schritte mit dem Schreiben von Dokumentation</span><span class="sxs-lookup"><span data-stu-id="ec6cc-148">Get started writing docs</span></span>](get-started-writing.md)
- [<span data-ttu-id="ec6cc-149">Übermitteln eines Pull Requests</span><span class="sxs-lookup"><span data-stu-id="ec6cc-149">Submitting a pull request</span></span>](pull-requests.md)
- [<span data-ttu-id="ec6cc-150">Styleguide für die PowerShell-Dokumentation</span><span class="sxs-lookup"><span data-stu-id="ec6cc-150">PowerShell-Docs style guide</span></span>](powershell-style-guide.md)

<span data-ttu-id="ec6cc-151">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="ec6cc-151">Additional resources</span></span>

- [<span data-ttu-id="ec6cc-152">Checkliste für Redakteure</span><span class="sxs-lookup"><span data-stu-id="ec6cc-152">Editorial checklist</span></span>](editorial-checklist.md)
- [<span data-ttu-id="ec6cc-153">Verwalten von Issues</span><span class="sxs-lookup"><span data-stu-id="ec6cc-153">How we manage issues</span></span>](managing-issues.md)
- [<span data-ttu-id="ec6cc-154">Verwalten von Pull Requests</span><span class="sxs-lookup"><span data-stu-id="ec6cc-154">How we manage pull requests</span></span>](managing-pull-requests.md)

<!--link refs-->
[cla]: https://cla.microsoft.com/
[contribute]: /contribute/
[docs]: https://docs.microsoft.com/
[file-an-issue]: file-an-issue.md
[posh-git]: https://www.powershellgallery.com/packages/posh-git
[psdocs]: /powershell
[style-guide]: /style-guide/welcome/
[terms-of-use]: /legal/termsofuse
