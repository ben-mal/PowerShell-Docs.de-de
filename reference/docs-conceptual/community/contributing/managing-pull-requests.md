---
title: Verwalten von Pull Requests
description: In diesem Artikel wird erläutert, wie das PowerShell-Docs-Team Pull Requests verwaltet.
ms.date: 03/05/2020
ms.topic: conceptual
ms.openlocfilehash: af5280e91aa3744b6172dc3555df6989cb0ce1a2
ms.sourcegitcommit: b0488ca6557501184f20c8343b0ed5147b09e3fe
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2020
ms.locfileid: "86158172"
---
# <a name="managing-pull-requests"></a><span data-ttu-id="3fd0c-103">Verwalten von Pull Requests</span><span class="sxs-lookup"><span data-stu-id="3fd0c-103">Managing pull requests</span></span>

<span data-ttu-id="3fd0c-104">In diesem Artikel wird beschrieben, wie Pull Requests im Repository „PowerShell-Docs“ verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="3fd0c-104">This article documents how we manage pull requests in the PowerShell-Docs repository.</span></span> <span data-ttu-id="3fd0c-105">Dieser Artikel ist als Arbeitshilfe für Mitglieder des PowerShell-Docs-Teams gedacht.</span><span class="sxs-lookup"><span data-stu-id="3fd0c-105">This article is designed to be a job aid for members of the PowerShell-Docs team.</span></span> <span data-ttu-id="3fd0c-106">Er wird hier veröffentlicht, um den Prozess für unsere externen Mitwirkenden transparent zu gestalten.</span><span class="sxs-lookup"><span data-stu-id="3fd0c-106">It is published here to provide process transparency for our public contributors.</span></span>

## <a name="best-practices"></a><span data-ttu-id="3fd0c-107">Bewährte Methoden</span><span class="sxs-lookup"><span data-stu-id="3fd0c-107">Best practices</span></span>

- <span data-ttu-id="3fd0c-108">Die Person, die den PR einreicht, darf den PR nicht ohne Peer Review mergen.</span><span class="sxs-lookup"><span data-stu-id="3fd0c-108">The person submitting the PR should not merge the PR without a peer review.</span></span>
- <span data-ttu-id="3fd0c-109">Weisen Sie den Peer Reviewer beim Einreichen des PR zu.</span><span class="sxs-lookup"><span data-stu-id="3fd0c-109">Assign the peer reviewer when the PR is submitted.</span></span> <span data-ttu-id="3fd0c-110">Eine frühzeitige Zuweisung ermöglicht es dem Reviewer, früher mit Anmerkungen zur Bearbeitung zu antworten.</span><span class="sxs-lookup"><span data-stu-id="3fd0c-110">Early assignment allows the reviewer to respond sooner with editorial remarks.</span></span>
- <span data-ttu-id="3fd0c-111">Verwenden Sie Kommentare, um die Art der Änderung oder des beantragten Reviews zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="3fd0c-111">Use comments to describe the nature of the change or the type of review being requested.</span></span> <span data-ttu-id="3fd0c-112">Vergessen Sie nicht, den Reviewer zu @mention.</span><span class="sxs-lookup"><span data-stu-id="3fd0c-112">Be sure to @mention the reviewer.</span></span> <span data-ttu-id="3fd0c-113">Wenn die Änderung z. B. geringfügig ist und Sie kein vollständiges technisches Review benötigen, erklären Sie dies in einem Kommentar.</span><span class="sxs-lookup"><span data-stu-id="3fd0c-113">For example, if the change is minor and you don't need a full technical review, explain this in a comment.</span></span>

## <a name="pr-process-steps"></a><span data-ttu-id="3fd0c-114">PR-Prozessschritte</span><span class="sxs-lookup"><span data-stu-id="3fd0c-114">PR Process steps</span></span>

1. <span data-ttu-id="3fd0c-115">Verfasser: PR erstellen</span><span class="sxs-lookup"><span data-stu-id="3fd0c-115">Writer: Create PR</span></span>
   - <span data-ttu-id="3fd0c-116">Alle durch den PR gelösten Issues verknüpfen</span><span class="sxs-lookup"><span data-stu-id="3fd0c-116">Link any issues resolved by the PR</span></span>
   - <span data-ttu-id="3fd0c-117">Das Feature [autoclose](https://help.github.com/en/articles/closing-issues-using-keywords) von GitHub verwenden, um das Issue zu schließen</span><span class="sxs-lookup"><span data-stu-id="3fd0c-117">Use GitHub's [autoclose](https://help.github.com/en/articles/closing-issues-using-keywords) feature to close the issue</span></span>
1. <span data-ttu-id="3fd0c-118">Verfasser: Peer Reviewer zuweisen</span><span class="sxs-lookup"><span data-stu-id="3fd0c-118">Writer: Assign peer reviewer</span></span>
1. <span data-ttu-id="3fd0c-119">Reviewer: lektoriert und kommentiert (nach Bedarf)</span><span class="sxs-lookup"><span data-stu-id="3fd0c-119">Reviewer: proofreads and comments (as necessary)</span></span>
1. <span data-ttu-id="3fd0c-120">Verfasser: Feedback aus dem Review einarbeiten</span><span class="sxs-lookup"><span data-stu-id="3fd0c-120">Writer: Incorporate review feedback</span></span>
1. <span data-ttu-id="3fd0c-121">Beide: Rendern der Vorschau prüfen</span><span class="sxs-lookup"><span data-stu-id="3fd0c-121">Both: Review preview rendering</span></span>
1. <span data-ttu-id="3fd0c-122">Beide: Validierungsbericht prüfen, Warnungen und Fehler beheben</span><span class="sxs-lookup"><span data-stu-id="3fd0c-122">Both: Review validation report - fix warnings and errors</span></span>
1. <span data-ttu-id="3fd0c-123">Verfasser: Freigabekommentar hinzufügen (Acrolinx-Info einschließen)</span><span class="sxs-lookup"><span data-stu-id="3fd0c-123">Writer: Add sign-off comment (include Acrolinx info)</span></span>
1. <span data-ttu-id="3fd0c-124">Reviewer: Review mit „Genehmigt“ markieren</span><span class="sxs-lookup"><span data-stu-id="3fd0c-124">Reviewer: Mark review "Approved"</span></span>
1. <span data-ttu-id="3fd0c-125">Repositoryadministrator: PR mergen (siehe Kriterien unten)</span><span class="sxs-lookup"><span data-stu-id="3fd0c-125">Repo Admin: Merge PR (see below for criteria)</span></span>

## <a name="content-reviewer-checklist"></a><span data-ttu-id="3fd0c-126">Checklist für Inhaltsreviewer</span><span class="sxs-lookup"><span data-stu-id="3fd0c-126">Content Reviewer Checklist</span></span>

<span data-ttu-id="3fd0c-127">Eine umfassendere Liste finden Sie in der [Checkliste für die Bearbeitung](editorial-checklist.md).</span><span class="sxs-lookup"><span data-stu-id="3fd0c-127">See the [editorial checklist](editorial-checklist.md) for a more comprehensive list.</span></span>

- <span data-ttu-id="3fd0c-128">Hinsichtlich Grammatik, Stil, Klarheit und technische Genauigkeit lektorieren</span><span class="sxs-lookup"><span data-stu-id="3fd0c-128">Proofread for grammar, style, concision, technical accuracy</span></span>
- <span data-ttu-id="3fd0c-129">Sicherstellen, dass Beispiele weiterhin für die Zielversion gelten</span><span class="sxs-lookup"><span data-stu-id="3fd0c-129">Ensure examples still apply for the target version</span></span>
- <span data-ttu-id="3fd0c-130">Rendern der Vorschau prüfen</span><span class="sxs-lookup"><span data-stu-id="3fd0c-130">Check Preview rendering</span></span>
- <span data-ttu-id="3fd0c-131">Metadaten prüfen: ms.date, ms.assetid entfernen, Pflichtfelder sicherstellen</span><span class="sxs-lookup"><span data-stu-id="3fd0c-131">Check metadata - ms.date, remove ms.assetid, ensure required fields</span></span>
- <span data-ttu-id="3fd0c-132">Richtigkeit des Markdowns überprüfen</span><span class="sxs-lookup"><span data-stu-id="3fd0c-132">Validate markdown correctness</span></span>
  - <span data-ttu-id="3fd0c-133">Informationen zum Formatieren bestimmter Inhalte finden Sie im Styleguide.</span><span class="sxs-lookup"><span data-stu-id="3fd0c-133">See style guide for formatting specific content</span></span>
- <span data-ttu-id="3fd0c-134">Organisieren Sie Beispiele wie folgt neu:</span><span class="sxs-lookup"><span data-stu-id="3fd0c-134">Reorganize examples as follows:</span></span>
  - <span data-ttu-id="3fd0c-135">Einleitungssätze</span><span class="sxs-lookup"><span data-stu-id="3fd0c-135">Intro sentence(s)</span></span>
  - <span data-ttu-id="3fd0c-136">Code und Ausgabe</span><span class="sxs-lookup"><span data-stu-id="3fd0c-136">Code and output</span></span>
  - <span data-ttu-id="3fd0c-137">Ausführliche Erläuterung des Codes (nach Bedarf)</span><span class="sxs-lookup"><span data-stu-id="3fd0c-137">Detailed explanation of code (as necessary)</span></span>
- <span data-ttu-id="3fd0c-138">Hyperlinks auf Genauigkeit überprüfen</span><span class="sxs-lookup"><span data-stu-id="3fd0c-138">Check hyperlinks for accuracy</span></span>
  - <span data-ttu-id="3fd0c-139">TechNet-/MSDN-Links ersetzen oder entfernen</span><span class="sxs-lookup"><span data-stu-id="3fd0c-139">Replace or remove TechNet/MSDN links</span></span>
  - <span data-ttu-id="3fd0c-140">Mindestanzahl von Umleitungen zum Ziel sicherstellen</span><span class="sxs-lookup"><span data-stu-id="3fd0c-140">Ensure minimum number of redirects to target</span></span>
  - <span data-ttu-id="3fd0c-141">HTTPS sicherstellen</span><span class="sxs-lookup"><span data-stu-id="3fd0c-141">Ensure HTTPS</span></span>
  - <span data-ttu-id="3fd0c-142">Ordnungsgemäßer Linktyp</span><span class="sxs-lookup"><span data-stu-id="3fd0c-142">Correct link type</span></span>
    - <span data-ttu-id="3fd0c-143">Dateilinks für lokale Dateien</span><span class="sxs-lookup"><span data-stu-id="3fd0c-143">File links for local files</span></span>
    - <span data-ttu-id="3fd0c-144">URL-Links für Dateien außerhalb des Docsets</span><span class="sxs-lookup"><span data-stu-id="3fd0c-144">URL links for files outside of the docset</span></span>
  - <span data-ttu-id="3fd0c-145">Gebietsschemas aus URLs entfernen</span><span class="sxs-lookup"><span data-stu-id="3fd0c-145">Remove locales from URLs</span></span>
  - <span data-ttu-id="3fd0c-146">URLs vereinfachen, die auf `docs.microsoft.com` zeigen</span><span class="sxs-lookup"><span data-stu-id="3fd0c-146">Simplify URLs pointing to `docs.microsoft.com`</span></span>

## <a name="branch-merge-process"></a><span data-ttu-id="3fd0c-147">Mergeprozess von Branches</span><span class="sxs-lookup"><span data-stu-id="3fd0c-147">Branch Merge Process</span></span>

<span data-ttu-id="3fd0c-148">Der Stagingbranch ist der einzige Branch, in den live gemergt werden darf.</span><span class="sxs-lookup"><span data-stu-id="3fd0c-148">The staging branch is the only branch that should ever be merged into live.</span></span> <span data-ttu-id="3fd0c-149">Für Merges aus kurzlebigen (funktionierenden) Branches muss ein Squash ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="3fd0c-149">Merges from short-lived (working) branches should be squashed.</span></span>

| <span data-ttu-id="3fd0c-150">*Mergen aus/in*</span><span class="sxs-lookup"><span data-stu-id="3fd0c-150">*Merge from/to*</span></span>  | <span data-ttu-id="3fd0c-151">*release-branch*</span><span class="sxs-lookup"><span data-stu-id="3fd0c-151">*release-branch*</span></span> | <span data-ttu-id="3fd0c-152">*staging*</span><span class="sxs-lookup"><span data-stu-id="3fd0c-152">*staging*</span></span>        | <span data-ttu-id="3fd0c-153">*live*</span><span class="sxs-lookup"><span data-stu-id="3fd0c-153">*live*</span></span>      |
| ---------------- |:----------------:|:----------------:|:-----------:|
| <span data-ttu-id="3fd0c-154">*working-branch*</span><span class="sxs-lookup"><span data-stu-id="3fd0c-154">*working-branch*</span></span> | <span data-ttu-id="3fd0c-155">Squash und Merge</span><span class="sxs-lookup"><span data-stu-id="3fd0c-155">squash and merge</span></span> | <span data-ttu-id="3fd0c-156">Squash und Merge</span><span class="sxs-lookup"><span data-stu-id="3fd0c-156">squash and merge</span></span> | <span data-ttu-id="3fd0c-157">Nicht zulässig</span><span class="sxs-lookup"><span data-stu-id="3fd0c-157">Not allowed</span></span> |
| <span data-ttu-id="3fd0c-158">*release-branch*</span><span class="sxs-lookup"><span data-stu-id="3fd0c-158">*release-branch*</span></span> | &mdash;          | <span data-ttu-id="3fd0c-159">merge</span><span class="sxs-lookup"><span data-stu-id="3fd0c-159">merge</span></span>            | <span data-ttu-id="3fd0c-160">Nicht zulässig</span><span class="sxs-lookup"><span data-stu-id="3fd0c-160">Not allowed</span></span> |
| <span data-ttu-id="3fd0c-161">*staging*</span><span class="sxs-lookup"><span data-stu-id="3fd0c-161">*staging*</span></span>        | <span data-ttu-id="3fd0c-162">Rebase ausführen</span><span class="sxs-lookup"><span data-stu-id="3fd0c-162">rebase</span></span>           | &mdash;          | <span data-ttu-id="3fd0c-163">merge</span><span class="sxs-lookup"><span data-stu-id="3fd0c-163">merge</span></span>       |

### <a name="pr-merger-checklist"></a><span data-ttu-id="3fd0c-164">Checkliste für PR-Merge</span><span class="sxs-lookup"><span data-stu-id="3fd0c-164">PR Merger checklist</span></span>

- <span data-ttu-id="3fd0c-165">Inhaltsüberprüfung beendet</span><span class="sxs-lookup"><span data-stu-id="3fd0c-165">Content review complete</span></span>
- <span data-ttu-id="3fd0c-166">Richtiger Zielbranch für die Änderung</span><span class="sxs-lookup"><span data-stu-id="3fd0c-166">Correct target branch for the change</span></span>
- <span data-ttu-id="3fd0c-167">Keine Mergingkonflikte</span><span class="sxs-lookup"><span data-stu-id="3fd0c-167">No merge conflicts</span></span>
- <span data-ttu-id="3fd0c-168">Alle Validierungs- und Buildschritte bestanden</span><span class="sxs-lookup"><span data-stu-id="3fd0c-168">All validation and build step pass</span></span>
  - <span data-ttu-id="3fd0c-169">Warnungen und Vorschläge müssen korrigiert werden (unter [Hinweise](#notes) finden Sie weitere Informationen zu Ausnahmen).</span><span class="sxs-lookup"><span data-stu-id="3fd0c-169">Warnings and suggestions should be fixed (see [Notes](#notes) for exceptions)</span></span>
  - <span data-ttu-id="3fd0c-170">Keine unterbrochenen Links</span><span class="sxs-lookup"><span data-stu-id="3fd0c-170">No broken links</span></span>
- <span data-ttu-id="3fd0c-171">Entsprechend der Tabelle mergen</span><span class="sxs-lookup"><span data-stu-id="3fd0c-171">Merge according to table</span></span>

### <a name="notes"></a><span data-ttu-id="3fd0c-172">Notizen</span><span class="sxs-lookup"><span data-stu-id="3fd0c-172">Notes</span></span>

<span data-ttu-id="3fd0c-173">Die folgenden Warnungen können ignoriert werden:</span><span class="sxs-lookup"><span data-stu-id="3fd0c-173">The following warnings can be ignored:</span></span>

```
Can't find service name for `<version>/<modulepath>/About/About.md`
```

```
Metadata with following name(s) are not allowed to be set in Yaml header, or as file level
metadata in docfx.json, or as global metadata in docfx.json: `locale`. They are generated by
Docs platform, so the values set in these 3 places will be ignored. Please remove them from all
3 places to resolve the warning.
```

<span data-ttu-id="3fd0c-174">Wenn ein PR gemergt wird, wird der HEAD des Zielbranches geändert.</span><span class="sxs-lookup"><span data-stu-id="3fd0c-174">When a PR is merged, the HEAD of the target branch is changed.</span></span> <span data-ttu-id="3fd0c-175">Alle offenen PRs, die auf dem vorherigen HEAD basierten, sind nun veraltet.</span><span class="sxs-lookup"><span data-stu-id="3fd0c-175">Any open PRs that were based on the previous HEAD are now outdated.</span></span> <span data-ttu-id="3fd0c-176">Der veraltete PR kann mit Administratorrechten gemergt werden, um die Mergewarnungen in GitHub zu überschreiben.</span><span class="sxs-lookup"><span data-stu-id="3fd0c-176">The outdated PR can be merged using Admin rights to override the merge warnings in GitHub.</span></span> <span data-ttu-id="3fd0c-177">Dieser Schritt ist sicher, wenn die zuvor gemergten PR(s) nicht dieselben Dateien betroffen haben.</span><span class="sxs-lookup"><span data-stu-id="3fd0c-177">This is safe to do if the previously merged PR(s) have not touched the same files.</span></span> <span data-ttu-id="3fd0c-178">Das Klicken auf die Schaltfläche **Update Branch** ist jedoch die sicherste Option.</span><span class="sxs-lookup"><span data-stu-id="3fd0c-178">However, clicking the **Update Branch** button is the safest option.</span></span> <span data-ttu-id="3fd0c-179">Möglicherweise gibt es ungelöste Konflikte, die gelöst werden müssen.</span><span class="sxs-lookup"><span data-stu-id="3fd0c-179">You may have unresolved conflicts that need to be fixed.</span></span>

## <a name="publishing-to-live"></a><span data-ttu-id="3fd0c-180">Veröffentlichen auf der aktiven Website</span><span class="sxs-lookup"><span data-stu-id="3fd0c-180">Publishing to Live</span></span>

<span data-ttu-id="3fd0c-181">In regelmäßigen Abständen müssen die im Branch `staging` gesammelten Änderungen auf der aktiven Website veröffentlicht werden.</span><span class="sxs-lookup"><span data-stu-id="3fd0c-181">Periodically, the changes accumulated in the `staging` branch need to be published to the live website.</span></span> <span data-ttu-id="3fd0c-182">Dies erfordert das Mergen von Branch `staging` in Branch `live`.</span><span class="sxs-lookup"><span data-stu-id="3fd0c-182">This require merging the `staging` branch into the `live` branch.</span></span>

- <span data-ttu-id="3fd0c-183">Der Branch `staging` sollte mindestens einmal pro Woche in `live` gemergt werden.</span><span class="sxs-lookup"><span data-stu-id="3fd0c-183">The `staging` branch should be merged to `live` at least once per week.</span></span>
- <span data-ttu-id="3fd0c-184">Der Branch `staging` sollte nach jeder signifikanten Änderung in `live` gemergt werden.</span><span class="sxs-lookup"><span data-stu-id="3fd0c-184">The `staging` branch should be merged to `live` after any significant change.</span></span>
  - <span data-ttu-id="3fd0c-185">Änderungen an 50 oder mehr Dateien</span><span class="sxs-lookup"><span data-stu-id="3fd0c-185">Changes to 50 or more files</span></span>
  - <span data-ttu-id="3fd0c-186">Nach Mergen eines Releasebranches</span><span class="sxs-lookup"><span data-stu-id="3fd0c-186">After merging a release branch</span></span>
  - <span data-ttu-id="3fd0c-187">Änderungen an der Repository- oder Docset-Konfiguration (docfx.json, OPS-Konfigurationen, Buildskripts usw.)</span><span class="sxs-lookup"><span data-stu-id="3fd0c-187">Changes to repo or docset configurations (docfx.json, OPS configs, build scripts, etc.)</span></span>
  - <span data-ttu-id="3fd0c-188">Änderungen an der Umleitungsdatei</span><span class="sxs-lookup"><span data-stu-id="3fd0c-188">Changes to the redirection file</span></span>
  - <span data-ttu-id="3fd0c-189">Änderungen am Inhaltsverzeichnis</span><span class="sxs-lookup"><span data-stu-id="3fd0c-189">Changes to the TOC</span></span>
  - <span data-ttu-id="3fd0c-190">Nach Mergen eines Branches des Typs „Projekt“ (Neuorganisation des Inhalts, Massenaktualisierung usw.)</span><span class="sxs-lookup"><span data-stu-id="3fd0c-190">After merging a "project" branch (content reorg, bulk update, etc.)</span></span>
