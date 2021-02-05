---
title: Checkliste für die Bearbeitung
description: Dies ist eine zusammengefasste Liste mit Regeln für die Bearbeitung der PowerShell-Dokumentation.
ms.date: 03/05/2020
ms.topic: conceptual
ms.openlocfilehash: b5baf7366239084779d34e23f218e5e6222ed1a3
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "81624736"
---
# <a name="editors-checklist"></a><span data-ttu-id="f4285-103">Checkliste für die Bearbeitung</span><span class="sxs-lookup"><span data-stu-id="f4285-103">Editor's checklist</span></span>

<span data-ttu-id="f4285-104">Dies ist eine Zusammenfassung der Regeln, die beim Schreiben neuer oder Aktualisieren bestehender Artikel gelten.</span><span class="sxs-lookup"><span data-stu-id="f4285-104">This is a summary of rules to apply when writing new or updating existing articles.</span></span> <span data-ttu-id="f4285-105">Ausführliche Erläuterungen und Beispiele zu diesen Regeln finden Sie in anderen Artikeln des Leitfadens für Mitwirkende.</span><span class="sxs-lookup"><span data-stu-id="f4285-105">See other articles in the Contributor's Guide for detailed explanations and examples of these rules.</span></span>

## <a name="metadata"></a><span data-ttu-id="f4285-106">Metadaten</span><span class="sxs-lookup"><span data-stu-id="f4285-106">Metadata</span></span>

- <span data-ttu-id="f4285-107">`ms.date`: muss das Format **MM/TT/JJJJ** haben</span><span class="sxs-lookup"><span data-stu-id="f4285-107">`ms.date`: must be in the format **MM/DD/YYYY**</span></span>
  - <span data-ttu-id="f4285-108">Datum ändern, sobald eine signifikante oder sachliche Aktualisierung vorliegt</span><span class="sxs-lookup"><span data-stu-id="f4285-108">Change the date when there is a significant or factual update</span></span>
    - <span data-ttu-id="f4285-109">Neuorganisieren des Artikels</span><span class="sxs-lookup"><span data-stu-id="f4285-109">Reorganizing the article</span></span>
    - <span data-ttu-id="f4285-110">Beheben sachlicher Fehler</span><span class="sxs-lookup"><span data-stu-id="f4285-110">Fixing factual errors</span></span>
    - <span data-ttu-id="f4285-111">Hinzufügen neuer Informationen</span><span class="sxs-lookup"><span data-stu-id="f4285-111">Adding new information</span></span>
  - <span data-ttu-id="f4285-112">Das Datum nicht ändern, wenn die Aktualisierung unerheblich ist</span><span class="sxs-lookup"><span data-stu-id="f4285-112">Do not change the date if the update is insignificant</span></span>
    - <span data-ttu-id="f4285-113">Korrigieren von Rechtschreibfehlern und Formatierung</span><span class="sxs-lookup"><span data-stu-id="f4285-113">Fixing typos and formatting</span></span>
- <span data-ttu-id="f4285-114">`title`: eindeutige Zeichenfolge mit 43-59 Zeichen einschließlich Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="f4285-114">`title`: unique string of 43-59 chars including spaces</span></span>
  - <span data-ttu-id="f4285-115">Standortbezeichner nicht einschließen (wird automatisch generiert)</span><span class="sxs-lookup"><span data-stu-id="f4285-115">Do not include site identifier (it is auto-generated)</span></span>
  - <span data-ttu-id="f4285-116">Nur ersten Buchstaben des Satzes und von Eigennamen großschreiben</span><span class="sxs-lookup"><span data-stu-id="f4285-116">Use sentence case - capitalize only the first word and any proper nouns</span></span>
- <span data-ttu-id="f4285-117">`description`: 115-145 Zeichen einschließlich Leerzeichen. Diese Zusammenfassung wird im Suchergebnis angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f4285-117">`description`: 115-145 characters including spaces - this abstract displays in the search result</span></span>

## <a name="formatting"></a><span data-ttu-id="f4285-118">Formatierung</span><span class="sxs-lookup"><span data-stu-id="f4285-118">Formatting</span></span>

- <span data-ttu-id="f4285-119">Elemente, die inline in einem Absatz angezeigt werden, in Hochkommas setzen</span><span class="sxs-lookup"><span data-stu-id="f4285-119">Backtick syntax elements that appear, inline, within a paragraph</span></span>
  - <span data-ttu-id="f4285-120">Cmdlet-Namen: `Verb-Noun`</span><span class="sxs-lookup"><span data-stu-id="f4285-120">Cmdlet names `Verb-Noun`</span></span>
  - <span data-ttu-id="f4285-121">Variable: `$counter`</span><span class="sxs-lookup"><span data-stu-id="f4285-121">Variable `$counter`</span></span>
  - <span data-ttu-id="f4285-122">Syntaktische Beispiele: `Verb-Noun -Parameter`</span><span class="sxs-lookup"><span data-stu-id="f4285-122">Syntactic examples `Verb-Noun -Parameter`</span></span>
  - <span data-ttu-id="f4285-123">Dateipfade: `C:\Program Files\PowerShell`, `/usr/bin/pwsh`</span><span class="sxs-lookup"><span data-stu-id="f4285-123">File paths `C:\Program Files\PowerShell`, `/usr/bin/pwsh`</span></span>
  - <span data-ttu-id="f4285-124">URLs, auf die im Dokument nicht geklickt werden soll</span><span class="sxs-lookup"><span data-stu-id="f4285-124">URLs that are not meant to be clickable in the document</span></span>
  - <span data-ttu-id="f4285-125">Eigenschafts- oder Parameterwerte</span><span class="sxs-lookup"><span data-stu-id="f4285-125">Property or parameter values</span></span>
- <span data-ttu-id="f4285-126">Formatieren Sie Eigenschaftsnamen, Parameternamen, Klassennamen, Modulnamen, Entitätsnamen sowie Objekt- oder Typnamen fett</span><span class="sxs-lookup"><span data-stu-id="f4285-126">Use bold for property names, parameter names, class names, module names, entity names, object or type names</span></span>
  - <span data-ttu-id="f4285-127">Fett wird für semantisches Markup verwendet, nicht zur Betonung</span><span class="sxs-lookup"><span data-stu-id="f4285-127">Bold is used for semantic markup, not emphasis</span></span>
  - <span data-ttu-id="f4285-128">Fett: Sternchen `**`</span><span class="sxs-lookup"><span data-stu-id="f4285-128">Bold - use asterisks `**`</span></span>
- <span data-ttu-id="f4285-129">Kursiv: Unterstrich `_`</span><span class="sxs-lookup"><span data-stu-id="f4285-129">Italic - use underscore `_`</span></span>
  - <span data-ttu-id="f4285-130">Wird nur zur Betonung verwendet, nicht für semantisches Markup</span><span class="sxs-lookup"><span data-stu-id="f4285-130">Only used for emphasis, not for semantic markup</span></span>
- <span data-ttu-id="f4285-131">Zeilenumbrüche bei 100 Spalten (oder 80 für **about_Topics**)</span><span class="sxs-lookup"><span data-stu-id="f4285-131">Line breaks at 100 columns (or at 80 for **about_Topics**)</span></span>
- <span data-ttu-id="f4285-132">Keine harten Tabstoppzeichen, nur Leerzeichen verwenden</span><span class="sxs-lookup"><span data-stu-id="f4285-132">No hard tabs - use spaces only</span></span>
- <span data-ttu-id="f4285-133">Nachgestellte Leerzeichen in Zeilen</span><span class="sxs-lookup"><span data-stu-id="f4285-133">No trailing spaces on lines</span></span>

### <a name="headers"></a><span data-ttu-id="f4285-134">Header</span><span class="sxs-lookup"><span data-stu-id="f4285-134">Headers</span></span>

- <span data-ttu-id="f4285-135">H1 als Erstes. Nur ein H1 pro Artikel</span><span class="sxs-lookup"><span data-stu-id="f4285-135">H1 is first - only one H1 per article</span></span>
- <span data-ttu-id="f4285-136">Nur [ATX-Header](https://github.github.com/gfm/#atx-headings) verwenden</span><span class="sxs-lookup"><span data-stu-id="f4285-136">Use [ATX Headers](https://github.github.com/gfm/#atx-headings) only</span></span>
- <span data-ttu-id="f4285-137">Ersten Buchstaben in allen Headern großschreiben</span><span class="sxs-lookup"><span data-stu-id="f4285-137">Use sentence case for all headers</span></span>
- <span data-ttu-id="f4285-138">Keine Ebenen überspringen: kein H3 ohne H2</span><span class="sxs-lookup"><span data-stu-id="f4285-138">Do not skip levels - no H3 without an H2</span></span>
- <span data-ttu-id="f4285-139">Maximale Tiefe von H3 oder H4</span><span class="sxs-lookup"><span data-stu-id="f4285-139">Max depth of H3 or H4</span></span>
- <span data-ttu-id="f4285-140">Leerzeile davor und dahinter</span><span class="sxs-lookup"><span data-stu-id="f4285-140">Blank line before and after</span></span>
- <span data-ttu-id="f4285-141">PlatyPS erzwingt bestimmte Header in seinem Schema. Keine Header hinzufügen oder entfernen</span><span class="sxs-lookup"><span data-stu-id="f4285-141">PlatyPS enforces specific headers in its schema - do not add or remove headers</span></span>

### <a name="code-blocks"></a><span data-ttu-id="f4285-142">Codeblöcke</span><span class="sxs-lookup"><span data-stu-id="f4285-142">Code blocks</span></span>

- <span data-ttu-id="f4285-143">Leerzeile davor und dahinter</span><span class="sxs-lookup"><span data-stu-id="f4285-143">Blank line before and after</span></span>
- <span data-ttu-id="f4285-144">Codeumgrenzungen in Form von Tags verwenden: **PowerShell**, **Ausgabe** oder andere geeignete Sprach-ID</span><span class="sxs-lookup"><span data-stu-id="f4285-144">Use tagged code fences - **powershell**, **Output**, or other appropriate language ID</span></span>
- <span data-ttu-id="f4285-145">Umgrenzung ohne Tags: Syntaxblöcke oder andere Shells</span><span class="sxs-lookup"><span data-stu-id="f4285-145">Untagged fence - syntax blocks or other shells</span></span>
- <span data-ttu-id="f4285-146">Platzieren Sie die Ausgabe in einem separaten Codeblock (mit Ausnahme von einfachen Beispielen, bei denen Sie nicht beabsichtigen, dass der Leser auf die Schaltfläche **Kopieren** klickt)</span><span class="sxs-lookup"><span data-stu-id="f4285-146">Put output in separate code block except for simple examples where you don't intend the for the reader to use the **Copy** button</span></span>
- <span data-ttu-id="f4285-147">Siehe die Liste der [unterstützten Sprachen](/contribute/code-in-docs#supported-languages)</span><span class="sxs-lookup"><span data-stu-id="f4285-147">See list of [supported languages](/contribute/code-in-docs#supported-languages)</span></span>

### <a name="lists"></a><span data-ttu-id="f4285-148">Listen</span><span class="sxs-lookup"><span data-stu-id="f4285-148">Lists</span></span>

- <span data-ttu-id="f4285-149">Ordnungsgemäß eingerückt</span><span class="sxs-lookup"><span data-stu-id="f4285-149">Indented properly</span></span>
- <span data-ttu-id="f4285-150">Leerzeile vor dem ersten und hinter dem letzten Element</span><span class="sxs-lookup"><span data-stu-id="f4285-150">Blank line before first item and after last item</span></span>
- <span data-ttu-id="f4285-151">Aufzählungszeichen: Bindestrich (`-`) verwenden, keine Sternchen (`*`) –zu leicht mit Betonung zu verwechseln</span><span class="sxs-lookup"><span data-stu-id="f4285-151">Bullet - use hyphen (`-`) not asterisk (`*`) - too easy to confuse with emphasis</span></span>
- <span data-ttu-id="f4285-152">Bei nummerierten Listen lauten alle Zahlen „1“.</span><span class="sxs-lookup"><span data-stu-id="f4285-152">For numbered lists, all numbers are "1."</span></span>

## <a name="terminology"></a><span data-ttu-id="f4285-153">Begriff</span><span class="sxs-lookup"><span data-stu-id="f4285-153">Terminology</span></span>

- <span data-ttu-id="f4285-154">PowerShell verglichen mit Windows PowerShell verglichen mit PowerShell Core</span><span class="sxs-lookup"><span data-stu-id="f4285-154">PowerShell vs. Windows PowerShell vs. PowerShell Core</span></span>
- <span data-ttu-id="f4285-155">Siehe [Produktterminologie](powershell-style-guide.md#product-terminology)</span><span class="sxs-lookup"><span data-stu-id="f4285-155">See [Product Terminology](powershell-style-guide.md#product-terminology)</span></span>

## <a name="cmdlet-reference-examples"></a><span data-ttu-id="f4285-156">Cmdlet-Referenz: Beispiele</span><span class="sxs-lookup"><span data-stu-id="f4285-156">Cmdlet reference examples</span></span>

- <span data-ttu-id="f4285-157">Mindestens ein Beispiel muss in der Cmdlet-Referenz vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="f4285-157">Must have at least one example in cmdlet reference</span></span>
- <span data-ttu-id="f4285-158">Beispiele sollten gerade nur so viel Code enthalten, um die Verwendung zu veranschaulichen.</span><span class="sxs-lookup"><span data-stu-id="f4285-158">Examples should be just enough code to demonstrate the usage</span></span>
- <span data-ttu-id="f4285-159">PowerShell-Syntax</span><span class="sxs-lookup"><span data-stu-id="f4285-159">PowerShell syntax</span></span>
  - <span data-ttu-id="f4285-160">Vollständige Namen von Cmdlets und Parametern verwenden – keine Aliase</span><span class="sxs-lookup"><span data-stu-id="f4285-160">Use full names of cmdlets and parameters - no aliases</span></span>
  - <span data-ttu-id="f4285-161">Aufteilung von Parametern verwenden, wenn die Befehlszeile zu lang wird</span><span class="sxs-lookup"><span data-stu-id="f4285-161">Use splatting for parameters when the command line gets too long</span></span>
  - <span data-ttu-id="f4285-162">Hochkommas zur Zeilenfortsetzung vermeiden, nur bei Bedarf verwenden</span><span class="sxs-lookup"><span data-stu-id="f4285-162">Avoid using line continuation backticks - only use when necessary</span></span>
- <span data-ttu-id="f4285-163">Die PowerShell-Eingabeaufforderung (`PS>`) entfernen oder vereinfachen, außer wenn für das Beispiel erforderlich</span><span class="sxs-lookup"><span data-stu-id="f4285-163">Remove or simplify the PowerShell prompt (`PS>`) except where required for the example</span></span>
- <span data-ttu-id="f4285-164">Das Cmdlet-Referenzbeispiel muss dem folgenden PlatyPS-Schema folgen</span><span class="sxs-lookup"><span data-stu-id="f4285-164">Cmdlet reference example must follow the following PlatyPS schema</span></span>

  ~~~Markdown
  ### Example 1 - Descriptive title

  Zero or more short descriptive paragraphs explaining the context of the example followed by one or
  more code blocks. Recommend at least one and no more than two.

  ```powershell
  ... one or more PowerShell code statements ...
  ```

  ```Output
  Example output of the code above.
  ```

  Zero or more optional follow up paragraphs that explain the details of the code and output.
  ~~~

- <span data-ttu-id="f4285-165">Setzen Sie keine Absätze zwischen die Codeblöcke.</span><span class="sxs-lookup"><span data-stu-id="f4285-165">Do not put paragraphs between the code blocks.</span></span> <span data-ttu-id="f4285-166">Der gesamte beschreibende Inhalt muss vor oder hinter den Codeblöcken stehen.</span><span class="sxs-lookup"><span data-stu-id="f4285-166">All descriptive content must come before or after the code blocks.</span></span>

## <a name="linking-to-other-documents"></a><span data-ttu-id="f4285-167">Verknüpfen mit anderen Dokumenten</span><span class="sxs-lookup"><span data-stu-id="f4285-167">Linking to other documents</span></span>

- <span data-ttu-id="f4285-168">Verknüpfung außerhalb des Docsets oder zwischen Cmdlet-Referenz und konzeptuellen Inhalten</span><span class="sxs-lookup"><span data-stu-id="f4285-168">Linking outside the docset or between cmdlet reference and conceptual</span></span>
  - <span data-ttu-id="f4285-169">Relative URLs beim Verknüpfen mit docs.microsoft.com verwenden (`https://docs.microsoft.com/en-us` entfernen)</span><span class="sxs-lookup"><span data-stu-id="f4285-169">Use relative URLs when linking to docs.microsoft.com (remove `https://docs.microsoft.com/en-us`)</span></span>
  - <span data-ttu-id="f4285-170">Schließen Sie keine Gebietsschemas in URLs in Microsoft-Eigenschaften ein (entfernen Sie beispielsweise</span><span class="sxs-lookup"><span data-stu-id="f4285-170">Do not include locales in URLs on Microsoft properties (eg.</span></span> <span data-ttu-id="f4285-171">`/en-us` aus dem URL)</span><span class="sxs-lookup"><span data-stu-id="f4285-171">remove `/en-us` from URL)</span></span>
  - <span data-ttu-id="f4285-172">Alle URLs zu externen Websites müssen HTTPS verwenden, es sei denn, dies gilt nicht für die Zielwebsite</span><span class="sxs-lookup"><span data-stu-id="f4285-172">All URLs to external websites should use HTTPS unless that is not valid for the target site</span></span>
- <span data-ttu-id="f4285-173">Innerhalb des Docsets</span><span class="sxs-lookup"><span data-stu-id="f4285-173">Within docset</span></span>
  - <span data-ttu-id="f4285-174">Link zu Dateipfad (z. B. `../folder/file.md`)</span><span class="sxs-lookup"><span data-stu-id="f4285-174">Link to file path (e.g. `../folder/file.md`)</span></span>
  - <span data-ttu-id="f4285-175">Alle Dateipfade enthalten Schrägstriche (`/`).</span><span class="sxs-lookup"><span data-stu-id="f4285-175">All file paths use forward-slash (`/`) characters</span></span>
- <span data-ttu-id="f4285-176">Bildlinks müssen eindeutigen alternativen Text enthalten.</span><span class="sxs-lookup"><span data-stu-id="f4285-176">Image links should have unique alt text</span></span>
