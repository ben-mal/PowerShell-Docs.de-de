---
title: Verwalten von Issues
description: In diesem Artikel wird erläutert, wie das PowerShell-Docs-Team Issues verwaltet.
ms.date: 12/09/2020
ms.topic: conceptual
ms.openlocfilehash: c6cb38bc37260b14e2a7c728879e2fa2a036133f
ms.sourcegitcommit: f6cc3752463b254f6ba7fc14c1e4532ad33f06bb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2021
ms.locfileid: "107216912"
---
# <a name="how-we-manage-issues"></a><span data-ttu-id="af79c-103">Verwalten von Issues</span><span class="sxs-lookup"><span data-stu-id="af79c-103">How we manage issues</span></span>

<span data-ttu-id="af79c-104">In diesem Artikel wird beschrieben, wie Issues im Repository „PowerShell-Docs“ verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="af79c-104">This article documents how we manage issues in the PowerShell-Docs repo.</span></span> <span data-ttu-id="af79c-105">Dieser Artikel ist als Arbeitshilfe für Mitglieder des PowerShell-Docs-Teams gedacht.</span><span class="sxs-lookup"><span data-stu-id="af79c-105">This article is designed to be a job aid for members of the PowerShell-Docs team.</span></span> <span data-ttu-id="af79c-106">Es wird hier veröffentlicht, um Prozesstransparenz für unsere öffentlichen Mitwirkenden bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="af79c-106">It's published here to provide process transparency for our public contributors.</span></span>

## <a name="sources-of-issues"></a><span data-ttu-id="af79c-107">Quellen von Issues</span><span class="sxs-lookup"><span data-stu-id="af79c-107">Sources of issues</span></span>

- <span data-ttu-id="af79c-108">Mitwirkende an der Community</span><span class="sxs-lookup"><span data-stu-id="af79c-108">Community contributors</span></span>
- <span data-ttu-id="af79c-109">Interne Mitwirkende</span><span class="sxs-lookup"><span data-stu-id="af79c-109">Internal contributors</span></span>
- <span data-ttu-id="af79c-110">Transkriptionen von Kommentaren aus Kanälen in sozialen Medien</span><span class="sxs-lookup"><span data-stu-id="af79c-110">Transcriptions of comments from social media channels</span></span>
- <span data-ttu-id="af79c-111">Feedback über das Docs-Feedbackformular</span><span class="sxs-lookup"><span data-stu-id="af79c-111">Feedback via the Docs feedback form</span></span>

## <a name="response-time-targets"></a><span data-ttu-id="af79c-112">Zielzeit für Antworten</span><span class="sxs-lookup"><span data-stu-id="af79c-112">Response time targets</span></span>

<span data-ttu-id="af79c-113">80% der neuen Probleme werden innerhalb von drei Werktagen geschlossen.</span><span class="sxs-lookup"><span data-stu-id="af79c-113">80% of new issues are closed within 3 business days.</span></span>

- <span data-ttu-id="af79c-114">Über einen Zeitraum von 1 Werktage</span><span class="sxs-lookup"><span data-stu-id="af79c-114">Triaged - 1 business days</span></span>
- <span data-ttu-id="af79c-115">Korrigieren oder ändern-10 Werktage</span><span class="sxs-lookup"><span data-stu-id="af79c-115">Fix or change - 10 business days</span></span>

### <a name="labeling--milestones"></a><span data-ttu-id="af79c-116">Bezeichnung und Meilensteine</span><span class="sxs-lookup"><span data-stu-id="af79c-116">Labeling & Milestones</span></span>

#### <a name="label-types"></a><span data-ttu-id="af79c-117">Bezeichnungstypen</span><span class="sxs-lookup"><span data-stu-id="af79c-117">Label Types</span></span>

|   <span data-ttu-id="af79c-118">type</span><span class="sxs-lookup"><span data-stu-id="af79c-118">Type</span></span>   | <span data-ttu-id="af79c-119">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="af79c-119">Description</span></span>                                                         |
| -------- | ------------------------------------------------------------------- |
| <span data-ttu-id="af79c-120">Bereich</span><span class="sxs-lookup"><span data-stu-id="af79c-120">Area</span></span>     | <span data-ttu-id="af79c-121">Dient zur Angabe des Teils von PowerShell oder der Dokumentation, der im Issue diskutiert wird.</span><span class="sxs-lookup"><span data-stu-id="af79c-121">Used to indicate what part of PowerShell or the docs that the issue is discussing.</span></span><br><span data-ttu-id="af79c-122">Nützlich für Zuständige für Features, um Issues für ihr Feature zu finden.</span><span class="sxs-lookup"><span data-stu-id="af79c-122">Useful for feature owners to find issues for their feature.</span></span> |
| <span data-ttu-id="af79c-123">Problem</span><span class="sxs-lookup"><span data-stu-id="af79c-123">Issue</span></span>    | <span data-ttu-id="af79c-124">Gibt den Typ des Problems an.</span><span class="sxs-lookup"><span data-stu-id="af79c-124">Indicates the type of issue</span></span>                                         |
| <span data-ttu-id="af79c-125">Priority</span><span class="sxs-lookup"><span data-stu-id="af79c-125">Priority</span></span> | <span data-ttu-id="af79c-126">Gibt die Priorität des Problems an.</span><span class="sxs-lookup"><span data-stu-id="af79c-126">Indicates the priority of the issue.</span></span> <span data-ttu-id="af79c-127">Wertebereich 0 (hoch)-4 (niedrig)</span><span class="sxs-lookup"><span data-stu-id="af79c-127">Value range 0 (high) -4 (low)</span></span>  |
| <span data-ttu-id="af79c-128">Status</span><span class="sxs-lookup"><span data-stu-id="af79c-128">Status</span></span>   | <span data-ttu-id="af79c-129">Gibt den Status des Arbeits Elements an oder warum es geschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="af79c-129">Indicates the status of the work item or why it was closed</span></span>          |
| <span data-ttu-id="af79c-130">Tag</span><span class="sxs-lookup"><span data-stu-id="af79c-130">Tag</span></span>      | <span data-ttu-id="af79c-131">Bezeichnungen, die für die weitere Klassifizierung verwendet werden</span><span class="sxs-lookup"><span data-stu-id="af79c-131">Labels used to for additional classification</span></span>                        |
| <span data-ttu-id="af79c-132">Warten</span><span class="sxs-lookup"><span data-stu-id="af79c-132">Waiting</span></span>  | <span data-ttu-id="af79c-133">Gibt an, dass wir auf ein oder mehrere andere Ereignisse warten.</span><span class="sxs-lookup"><span data-stu-id="af79c-133">Indicates that we're waiting on someone or some other event</span></span>         |

#### <a name="milestones"></a><span data-ttu-id="af79c-134">Meilensteine</span><span class="sxs-lookup"><span data-stu-id="af79c-134">Milestones</span></span>

<span data-ttu-id="af79c-135">Issues und Pull Requests (PRs) müssen mit dem entsprechenden Meilenstein gekennzeichnet sein.</span><span class="sxs-lookup"><span data-stu-id="af79c-135">Issues and PRs should be tagged with the appropriate milestone.</span></span> <span data-ttu-id="af79c-136">Wenn das Problem nicht für eine bestimmte Version gilt, wird kein Meilenstein verwendet.</span><span class="sxs-lookup"><span data-stu-id="af79c-136">If the issue doesn't apply to a specific version, then no milestone is used.</span></span> <span data-ttu-id="af79c-137">PRS und verwandte Probleme bei Änderungen, die noch in der PowerShell-Codebasis zusammengeführt werden müssen, sollten dem **zukünftigen** Meilenstein zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="af79c-137">PRs and related issues for changes that have yet to be merged into the PowerShell code base should be assigned to the **Future** milestone.</span></span> <span data-ttu-id="af79c-138">Nachdem die Codeänderung gemergt wurde, ändern Sie den Meilenstein in die entsprechende Version.</span><span class="sxs-lookup"><span data-stu-id="af79c-138">After the code change has been merged, change the milestone to the appropriate version.</span></span>

|    <span data-ttu-id="af79c-139">Meilenstein</span><span class="sxs-lookup"><span data-stu-id="af79c-139">Milestone</span></span>     |                    <span data-ttu-id="af79c-140">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="af79c-140">Description</span></span>                     |
| ---------------- | -------------------------------------------------- |
| <span data-ttu-id="af79c-141">7.0.0</span><span class="sxs-lookup"><span data-stu-id="af79c-141">7.0.0</span></span>            | <span data-ttu-id="af79c-142">Mit PowerShell 7.0 verknüpfte Arbeitselemente</span><span class="sxs-lookup"><span data-stu-id="af79c-142">Work items related to PowerShell 7.0</span></span>               |
| <span data-ttu-id="af79c-143">7.1.0</span><span class="sxs-lookup"><span data-stu-id="af79c-143">7.1.0</span></span>            | <span data-ttu-id="af79c-144">Mit PowerShell 7.1 verknüpfte Arbeitselemente</span><span class="sxs-lookup"><span data-stu-id="af79c-144">Work items related to PowerShell 7.1</span></span>               |
| <span data-ttu-id="af79c-145">7.2.0</span><span class="sxs-lookup"><span data-stu-id="af79c-145">7.2.0</span></span>            | <span data-ttu-id="af79c-146">Mit PowerShell 7,2 verknüpfte Arbeitselemente</span><span class="sxs-lookup"><span data-stu-id="af79c-146">Work items related to PowerShell 7.2</span></span>               |
| <span data-ttu-id="af79c-147">Zukunft</span><span class="sxs-lookup"><span data-stu-id="af79c-147">Future</span></span>           | <span data-ttu-id="af79c-148">Arbeitselemente in einer zukünftigen Version von PowerShell</span><span class="sxs-lookup"><span data-stu-id="af79c-148">Work items a future version of PowerShell</span></span>          |

## <a name="triage-process"></a><span data-ttu-id="af79c-149">Sichtungsprozess</span><span class="sxs-lookup"><span data-stu-id="af79c-149">Triage process</span></span>

<span data-ttu-id="af79c-150">PowerShell docs Teammitglieder überprüfen die Probleme täglich und selektiert neue Probleme, sobald sie eintreffen.</span><span class="sxs-lookup"><span data-stu-id="af79c-150">PowerShell docs team members review the issues daily and triage new issues as they arrive.</span></span> <span data-ttu-id="af79c-151">Das Team tagt wöchentlich, um Probleme zu erörtern, die selektiert werden müssen oder nicht aufgelöst werden müssen.</span><span class="sxs-lookup"><span data-stu-id="af79c-151">The team meets weekly to discuss issues that need triage or remain unresolved.</span></span>

### <a name="misplaced-product-feedback"></a><span data-ttu-id="af79c-152">Falsch gemeldetes Produktfeedback</span><span class="sxs-lookup"><span data-stu-id="af79c-152">Misplaced product feedback</span></span>

- <span data-ttu-id="af79c-153">Geben Sie einen Kommentar ein, der den Kunden zum richtigen Feedback Kanal umleitet.</span><span class="sxs-lookup"><span data-stu-id="af79c-153">Enter a comment redirecting the customer to the correct feedback channel.</span></span>
- <span data-ttu-id="af79c-154">Optional: Kopieren Sie das Issue an die entsprechende Stelle für Produktfeedback, fügen Sie einen Link zu dem kopierten Element hinzu, und schließen Sie das Issue.</span><span class="sxs-lookup"><span data-stu-id="af79c-154">Optional: Copy the issue to the appropriate product feedback location, add a link to the copied item, and close the issue.</span></span> <span data-ttu-id="af79c-155">Kopieren Sie Issues NICHT in UserVoice.</span><span class="sxs-lookup"><span data-stu-id="af79c-155">DO NOT copy issues to UserVoice.</span></span>

  <span data-ttu-id="af79c-156">Der Standard Speicherort für PowerShell-Probleme ist [https://github.com/PowerShell/PowerShell/issues/new/choose](https://github.com/PowerShell/PowerShell/issues/new/choose) .</span><span class="sxs-lookup"><span data-stu-id="af79c-156">The default location for PowerShell issues is [https://github.com/PowerShell/PowerShell/issues/new/choose](https://github.com/PowerShell/PowerShell/issues/new/choose).</span></span>

  <span data-ttu-id="af79c-157">Die folgenden Themenbereiche haben unterschiedliche Speicherorte für Probleme:</span><span class="sxs-lookup"><span data-stu-id="af79c-157">The following subject areas have different locations for issues:</span></span>

  | <span data-ttu-id="af79c-158">Themen</span><span class="sxs-lookup"><span data-stu-id="af79c-158">Subjects</span></span> |                                                     <span data-ttu-id="af79c-159">Produktfeedback-URL</span><span class="sxs-lookup"><span data-stu-id="af79c-159">Product Feedback URL</span></span>                                                     |
  | -------- | ---------------------------------------------------------------------------------------------------------------------------- |
  | <span data-ttu-id="af79c-160">DSC</span><span class="sxs-lookup"><span data-stu-id="af79c-160">dsc</span></span>      | [https://windowsserver.uservoice.com/forums/301869-powershell](https://windowsserver.uservoice.com/forums/301869-powershell) |
  | <span data-ttu-id="af79c-161">Katalog</span><span class="sxs-lookup"><span data-stu-id="af79c-161">gallery</span></span>  | [https://github.com/powershell/powershellgallery/issues/new](https://github.com/powershell/powershellgallery/issues/new)     |
  | <span data-ttu-id="af79c-162">wmf</span><span class="sxs-lookup"><span data-stu-id="af79c-162">wmf</span></span>      | [https://windowsserver.uservoice.com/forums/301869-powershell](https://windowsserver.uservoice.com/forums/301869-powershell) |

### <a name="support-requests"></a><span data-ttu-id="af79c-163">Supportanfragen</span><span class="sxs-lookup"><span data-stu-id="af79c-163">Support requests</span></span>

- <span data-ttu-id="af79c-164">Wenn die Supportfrage einfach ist, beantworten Sie sie höflich, und schließen Sie das Issue.</span><span class="sxs-lookup"><span data-stu-id="af79c-164">If the support question is simple, answer it politely and close the issue.</span></span>
- <span data-ttu-id="af79c-165">Wenn die Frage komplizierter ist oder der Fragensteller mit weiteren Fragen antwortet, leiten Sie ihn an Foren und Supportkanäle weiter.</span><span class="sxs-lookup"><span data-stu-id="af79c-165">If the question is more complicated, or the submitter replies with more questions, redirect them to forums and support channels.</span></span> <span data-ttu-id="af79c-166">Vorgeschlagener Text für die Umleitung zu Foren:</span><span class="sxs-lookup"><span data-stu-id="af79c-166">Suggested text for redirecting to forums:</span></span>

  ```Markdown
  > This is not the right forum for these kinds of questions. Try posting your question in a
  > community support forum. For a list of community forums see:
  > https://docs.microsoft.com/powershell/scripting/community/community-support
  ```

### <a name="code-of-conduct-violations"></a><span data-ttu-id="af79c-167">Verstöße gegen Verhaltensregeln</span><span class="sxs-lookup"><span data-stu-id="af79c-167">Code of conduct violations</span></span>

- <span data-ttu-id="af79c-168">Bearbeiten Sie das Issue, um ggf. anstößige Inhalte zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="af79c-168">Edit the issue to remove any offensive content, if necessary.</span></span>
- <span data-ttu-id="af79c-169">Geben Sie einen Kommentar ein, dass es sich bei dem Issue um Spam handelt, schließen Sie das Issue, und sperren Sie es anschließend, um weitere Kommentare zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="af79c-169">Enter a comment indicating the issue is spam, close the issue, and then lock it to prevent further comments.</span></span>
- <span data-ttu-id="af79c-170">Jede Verletzung sollte in der wöchentlichen Selektion erläutert werden, um den Bedarf an weiteren Maßnahmen zu ermitteln (melden Sie GitHub oder Microsoft legal).</span><span class="sxs-lookup"><span data-stu-id="af79c-170">Each violation should be discussed in the weekly triage to determine the need for further action (report to GitHub or Microsoft Legal).</span></span>
