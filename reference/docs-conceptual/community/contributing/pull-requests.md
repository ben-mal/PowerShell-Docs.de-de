---
title: Übermitteln von Pull Requests
description: In diesem Artikel wird erläutert, wie Pull Requests an das PowerShell-Docs-Team übermittelt werden.
ms.date: 12/09/2020
ms.topic: conceptual
ms.openlocfilehash: 1a21c25e19189aec4f48ad034147b02f4f804f9d
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "99603911"
---
# <a name="how-to-submit-pull-requests"></a><span data-ttu-id="a8c77-103">Übermitteln von Pull Requests</span><span class="sxs-lookup"><span data-stu-id="a8c77-103">How to submit pull requests</span></span>

<span data-ttu-id="a8c77-104">Wenn Sie inhaltliche Änderungen vornehmen möchten, übermitteln Sie einen Pull Request (PR) aus Ihrer Fork.</span><span class="sxs-lookup"><span data-stu-id="a8c77-104">To make changes to content, submit a pull request (PR) from your fork.</span></span> <span data-ttu-id="a8c77-105">Eine Pull Request muss überprüft werden, bevor Sie zusammengeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="a8c77-105">A pull request must be reviewed before it can be merged.</span></span> <span data-ttu-id="a8c77-106">Um optimale Ergebnisse zu erzielen, überprüfen Sie die [Checkliste für die Bearbeitung](editorial-checklist.md), bevor Sie Ihren Pull Request einreichen.</span><span class="sxs-lookup"><span data-stu-id="a8c77-106">For best results, review the [editorial checklist](editorial-checklist.md) before submitting your pull request.</span></span>

## <a name="using-git-branches"></a><span data-ttu-id="a8c77-107">Verwenden von git-branches</span><span class="sxs-lookup"><span data-stu-id="a8c77-107">Using git branches</span></span>

<span data-ttu-id="a8c77-108">Der standardbranch für PowerShell-Docs ist die `staging` Verzweigung.</span><span class="sxs-lookup"><span data-stu-id="a8c77-108">The default branch for PowerShell-Docs is the `staging` branch.</span></span> <span data-ttu-id="a8c77-109">Änderungen, die an arbeitsbranches vorgenommen werden, werden in der `staging` Verzweigung zusammengeführt, bevor Sie veröffentlicht werden.</span><span class="sxs-lookup"><span data-stu-id="a8c77-109">Changes made in working branches are merged into the `staging` branch before then being published.</span></span> <span data-ttu-id="a8c77-110">Die `staging` Verzweigung wird `live` alle Wochentage um 3:00 Uhr (Pacific Time) in der Verzweigung zusammengeführt.</span><span class="sxs-lookup"><span data-stu-id="a8c77-110">The `staging` branch is merged into the `live` branch every weekday at 3:00 PM (Pacific Time).</span></span> <span data-ttu-id="a8c77-111">Der `live` Branch enthält den Inhalt, der in docs.Microsoft.com veröffentlicht wird.</span><span class="sxs-lookup"><span data-stu-id="a8c77-111">The `live` branch contains the content that is published to docs.microsoft.com.</span></span>

<span data-ttu-id="a8c77-112">Erstellen Sie vor dem Starten von Änderungen einen arbeitbranch in Ihrer lokalen Kopie des PowerShell-Docs Repository.</span><span class="sxs-lookup"><span data-stu-id="a8c77-112">Before starting any changes, create a working branch in your local copy of the PowerShell-Docs repository.</span></span> <span data-ttu-id="a8c77-113">Wenn Sie lokal arbeiten, achten Sie darauf, das lokale Repository zu synchronisieren, bevor Sie den arbeitsbranch erstellen.</span><span class="sxs-lookup"><span data-stu-id="a8c77-113">When working locally, be sure to synchronize your local repository before creating your working branch.</span></span> <span data-ttu-id="a8c77-114">Der arbeitbranch sollte aus einer Update-to-date-Kopie der `staging` Verzweigung erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="a8c77-114">The working branch should be created from an update-to-date copy of the `staging` branch.</span></span>

<span data-ttu-id="a8c77-115">Alle Pull Requests müssen den Branch `staging` als Ziel haben.</span><span class="sxs-lookup"><span data-stu-id="a8c77-115">All pull requests should target the `staging` branch.</span></span> <span data-ttu-id="a8c77-116">Senden Sie keine Änderungen an die `live` Verzweigung.</span><span class="sxs-lookup"><span data-stu-id="a8c77-116">Don't submit change to the `live` branch.</span></span>
<span data-ttu-id="a8c77-117">Änderungen, die im Branch `staging` vorgenommen werden, werden in den Branch `live` gemergt, wobei alle Änderungen an `live` überschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="a8c77-117">Changes made in the `staging` branch get merged into `live`, overwriting any changes made to `live`.</span></span>

## <a name="make-the-pull-request-process-work-better-for-everyone"></a><span data-ttu-id="a8c77-118">Verbessern des Pull Request-Prozesses für alle Beteiligten</span><span class="sxs-lookup"><span data-stu-id="a8c77-118">Make the pull request process work better for everyone</span></span>

<span data-ttu-id="a8c77-119">Je einfacher und zielgerichteter Sie Ihren PR gestalten, desto schneller kann er überprüft und gemergt werden.</span><span class="sxs-lookup"><span data-stu-id="a8c77-119">The simpler and more focused you can make your PR, the faster it can be reviewed and merged.</span></span>

### <a name="avoid-pull-requests-that-update-large-numbers-of-files-or-contain-unrelated-changes"></a><span data-ttu-id="a8c77-120">Vermeiden von Pull Requests, die eine große Anzahl von Dateien aktualisieren oder nicht verknüpfte Änderungen enthalten</span><span class="sxs-lookup"><span data-stu-id="a8c77-120">Avoid pull requests that update large numbers of files or contain unrelated changes</span></span>

<span data-ttu-id="a8c77-121">Vermeiden Sie das Erstellen von PRs mit unzusammenhängenden Änderungen.</span><span class="sxs-lookup"><span data-stu-id="a8c77-121">Avoid creating PRs that contain unrelated changes.</span></span> <span data-ttu-id="a8c77-122">Trennen Sie kleinere Updates bestehender Artikel von neuen Artikeln oder größeren Neufassungen.</span><span class="sxs-lookup"><span data-stu-id="a8c77-122">Separate minor updates to existing articles from new articles or major rewrites.</span></span> <span data-ttu-id="a8c77-123">Arbeiten Sie an diesen Änderungen in separaten Bearbeitungsbranches.</span><span class="sxs-lookup"><span data-stu-id="a8c77-123">Work on these changes in separate working branches.</span></span>

<span data-ttu-id="a8c77-124">Bei Massenänderungen werden PRs mit einer großen Anzahl geänderter Dateien erstellt.</span><span class="sxs-lookup"><span data-stu-id="a8c77-124">Bulk changes create PRs with large numbers of changed files.</span></span> <span data-ttu-id="a8c77-125">Beschränken Sie Ihre PRs auf maximal 50 geänderte Dateien.</span><span class="sxs-lookup"><span data-stu-id="a8c77-125">Limit your PRs to a maximum of 50 changed files.</span></span> <span data-ttu-id="a8c77-126">Große PRs sind schwer zu überprüfen und anfälliger für Fehler.</span><span class="sxs-lookup"><span data-stu-id="a8c77-126">Large PRs are difficult to review and are more prone to contain errors.</span></span>

### <a name="renaming-or-deleting-files"></a><span data-ttu-id="a8c77-127">Umbenennen oder Löschen von Dateien</span><span class="sxs-lookup"><span data-stu-id="a8c77-127">Renaming or deleting files</span></span>

<span data-ttu-id="a8c77-128">Beim Umbenennen oder Löschen von Dateien muss ein Problem mit dem PR bestehen.</span><span class="sxs-lookup"><span data-stu-id="a8c77-128">When renaming or deleting files, there must be an issue associated with the PR.</span></span> <span data-ttu-id="a8c77-129">In diesem Issue muss die Notwendigkeit des Umbenennens oder Löschens der Dateien diskutiert werden.</span><span class="sxs-lookup"><span data-stu-id="a8c77-129">That issue must discuss the need to rename or delete the files.</span></span>

<span data-ttu-id="a8c77-130">Vermeiden Sie die Vermischung von Inhaltsergänzungen oder -änderungen mit Dateiumbenennungen und -löschungen.</span><span class="sxs-lookup"><span data-stu-id="a8c77-130">Avoid mixing content additions or change with file renames and deletes.</span></span> <span data-ttu-id="a8c77-131">Alle Dateien, die umbenannt oder gelöscht werden, müssen der globalen Umleitungs Datei hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="a8c77-131">Any file that is renamed or deleted must be added to the global redirection file.</span></span> <span data-ttu-id="a8c77-132">Aktualisieren Sie nach Möglichkeit alle Dateien, die mit dem umbenannten oder gelöschten Inhalt verknüpft sind, einschließlich aller Inhaltsverzeichnis Dateien.</span><span class="sxs-lookup"><span data-stu-id="a8c77-132">When possible, update any files that link to the renamed or deleted content, including any TOC files.</span></span>

## <a name="docs-pr-validation-service"></a><span data-ttu-id="a8c77-133">Validierungsdienst für auf die Dokumentation bezogene PRs</span><span class="sxs-lookup"><span data-stu-id="a8c77-133">Docs PR validation service</span></span>

<span data-ttu-id="a8c77-134">Der Validierungs Dienst von docs PR ist eine GitHub-APP, die Validierungsregeln für Ihre Änderungen ausführt.</span><span class="sxs-lookup"><span data-stu-id="a8c77-134">The Docs PR validation service is a GitHub app that runs validation rules on your changes.</span></span> <span data-ttu-id="a8c77-135">Sie müssen alle Fehler oder Warnungen beheben, die vom Validierungs Dienst gemeldet werden.</span><span class="sxs-lookup"><span data-stu-id="a8c77-135">You must fix any errors or warnings reported by the validation service.</span></span>

<span data-ttu-id="a8c77-136">Sie erkennen das folgende Verhalten:</span><span class="sxs-lookup"><span data-stu-id="a8c77-136">You'll see the following behavior:</span></span>

1. <span data-ttu-id="a8c77-137">Sie übermitteln einen PR.</span><span class="sxs-lookup"><span data-stu-id="a8c77-137">You submit a PR.</span></span>
1. <span data-ttu-id="a8c77-138">Im GitHub-Kommentar, der den Status Ihres Pull Requests anzeigt, sehen Sie den für das Repository aktivierten Zustand „Überprüfungen“.</span><span class="sxs-lookup"><span data-stu-id="a8c77-138">In the GitHub comment that indicates the status of your PR, you'll see the status of "checks" enabled on the repository.</span></span> <span data-ttu-id="a8c77-139">In diesem Beispiel sind zwei Überprüfungen aktiviert: "Commit Validation" und "openpublishing. Build":</span><span class="sxs-lookup"><span data-stu-id="a8c77-139">In this example, there are two checks enabled, "Commit Validation" and "OpenPublishing.Build":</span></span>

   ![Überprüfungszustand: einige Überprüfungen sind fehlgeschlagen](media/pull-requests/validation-failed.png)

   <span data-ttu-id="a8c77-141">Der Build kann fortgesetzt werden, auch wenn die Überprüfung des Commits fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="a8c77-141">The build can pass even if commit validation fails.</span></span>

1. <span data-ttu-id="a8c77-142">Klicken Sie auf **Details**, um weitere Informationen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="a8c77-142">Click **Details** for more information.</span></span>
1. <span data-ttu-id="a8c77-143">Auf der Seite „Details“ werden alle fehlgeschlagenen Validierungsprüfungen angezeigt, und zwar mit Informationen zur Behebung der Issues.</span><span class="sxs-lookup"><span data-stu-id="a8c77-143">On the Details page, you'll see all the validation checks that failed, with information about how to fix the issues.</span></span>
1. <span data-ttu-id="a8c77-144">Wenn die Validierung erfolgreich ist, wird dem PR der folgende Kommentar hinzugefügt:</span><span class="sxs-lookup"><span data-stu-id="a8c77-144">When validation succeeds, the following comment is added to the PR:</span></span>

   ![Überprüfungszustand: Erfolg](media/pull-requests/build-validation.png)

> [!NOTE]
> <span data-ttu-id="a8c77-146">Wenn Sie ein externer Mitwirkender (kein Mitarbeiter von Microsoft) sind, haben Sie keinen Zugriff auf die detaillierten Buildberichte oder Vorschaulinks.</span><span class="sxs-lookup"><span data-stu-id="a8c77-146">If you are an external (not a Microsoft employee) contributor you do not have access to the detailed build reports or preview links.</span></span>

<span data-ttu-id="a8c77-147">Wenn der PR überprüft wird, werden Sie möglicherweise aufgefordert, Änderungen vorzunehmen oder Validierungs Warnmeldungen zu beheben.</span><span class="sxs-lookup"><span data-stu-id="a8c77-147">When the PR is reviewed, you may be asked to make changes or fix validation warning messages.</span></span> <span data-ttu-id="a8c77-148">Das PowerShell-Docs Team kann Ihnen helfen, Validierungs Fehler und redaktionelle Anforderungen zu verstehen.</span><span class="sxs-lookup"><span data-stu-id="a8c77-148">The PowerShell-Docs team can help you understand validation errors and editorial requirements.</span></span>

## <a name="next-steps"></a><span data-ttu-id="a8c77-149">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="a8c77-149">Next steps</span></span>

[<span data-ttu-id="a8c77-150">Styleguide für die PowerShell-Dokumentation</span><span class="sxs-lookup"><span data-stu-id="a8c77-150">PowerShell-Docs style guide</span></span>](powershell-style-guide.md)

## <a name="additional-resources"></a><span data-ttu-id="a8c77-151">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="a8c77-151">Additional resources</span></span>

[<span data-ttu-id="a8c77-152">Verwalten von Pull Requests</span><span class="sxs-lookup"><span data-stu-id="a8c77-152">How we manage pull requests</span></span>](managing-pull-requests.md)

<!--link refs-->
[fork]: /contribute/get-started-setup-local#fork-the-repository
