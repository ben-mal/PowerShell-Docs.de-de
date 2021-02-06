---
title: Styleguide für die PowerShell-Dokumentation
description: Dieser Artikel enthält die Stilregeln für das Schreiben von PowerShell-Dokumentation.
ms.date: 12/09/2020
ms.topic: conceptual
ms.openlocfilehash: 6f23f63cffc9fed9cbbcf84539875bfaf4247732
ms.sourcegitcommit: 61765d08321623743dc5db5367160f6982fe7857
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/12/2020
ms.locfileid: "99596530"
---
# <a name="powershell-docs-style-guide"></a><span data-ttu-id="6100b-103">Styleguide für die PowerShell-Dokumentation</span><span class="sxs-lookup"><span data-stu-id="6100b-103">PowerShell-Docs style guide</span></span>

<span data-ttu-id="6100b-104">Dieser Artikel enthält die spezifischen Stilanweisungen für Inhalte der PowerShell-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="6100b-104">This article provides style guidance specific to the PowerShell-Docs content.</span></span> <span data-ttu-id="6100b-105">Es basiert auf den Informationen, die in der [Übersicht](overview.md#get-started-writing-docs)beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="6100b-105">It builds on the information outlined in the [Overview](overview.md#get-started-writing-docs).</span></span>

## <a name="product-terminology"></a><span data-ttu-id="6100b-106">Produktterminologie</span><span class="sxs-lookup"><span data-stu-id="6100b-106">Product Terminology</span></span>

<span data-ttu-id="6100b-107">Es gibt mehrere Varianten von PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6100b-107">There are several variants of PowerShell.</span></span>

- <span data-ttu-id="6100b-108">**PowerShell**: Dies ist die Standardvariante.</span><span class="sxs-lookup"><span data-stu-id="6100b-108">**PowerShell** - This is the default.</span></span> <span data-ttu-id="6100b-109">Wir sehen uns an, dass PowerShell 7 und darüber hinaus die richtige PowerShell ist.</span><span class="sxs-lookup"><span data-stu-id="6100b-109">We consider PowerShell 7 and beyond to be the one, true PowerShell.</span></span>
- <span data-ttu-id="6100b-110">**PowerShell Core-** : PowerShell basierend auf .NET Core.</span><span class="sxs-lookup"><span data-stu-id="6100b-110">**PowerShell Core** - PowerShell built on .NET Core.</span></span> <span data-ttu-id="6100b-111">Die Verwendung des Begriffs " **Core** " sollte auf Fälle beschränkt werden, in denen er von Windows PowerShell unterschieden werden muss.</span><span class="sxs-lookup"><span data-stu-id="6100b-111">Usage of the term **Core** should be limited to cases where it's necessary to differentiate it from Windows PowerShell.</span></span>
- <span data-ttu-id="6100b-112">**Windows PowerShell**:- PowerShell basierend auf .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6100b-112">**Windows PowerShell** - PowerShell built on .NET Framework.</span></span> <span data-ttu-id="6100b-113">Windows PowerShell wird nur für Windows ausgeliefert und erfordert das gesamte Framework.</span><span class="sxs-lookup"><span data-stu-id="6100b-113">Windows PowerShell ships only on Windows and requires the complete Framework.</span></span>

  <span data-ttu-id="6100b-114">Im Allgemeinen können Verweise auf "Windows PowerShell" in der-Dokumentation in _PowerShell_ geändert werden.</span><span class="sxs-lookup"><span data-stu-id="6100b-114">In general, references to "Windows PowerShell" in documentation can be changed to _PowerShell_.</span></span>
  <span data-ttu-id="6100b-115">"Windows PowerShell" sollte bei der Erörterung von _Windows PowerShell_-spezifischem Verhalten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6100b-115">"Windows PowerShell" should be used when _Windows PowerShell_-specific behavior is being discussed.</span></span>

<span data-ttu-id="6100b-116">Verwandte Produkte</span><span class="sxs-lookup"><span data-stu-id="6100b-116">Related products</span></span>

- <span data-ttu-id="6100b-117">**Visual Studio Code (vs Code)** : Dies ist der kostenlose Open Source-Editor von Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6100b-117">**Visual Studio Code (VS Code)** - This is Microsoft's free, open-source editor.</span></span> <span data-ttu-id="6100b-118">Bei der ersten Erwähnung sollte der vollständige Name verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6100b-118">At first mention, the full name should be used.</span></span> <span data-ttu-id="6100b-119">Anschließend können Sie **VS Code** verwenden.</span><span class="sxs-lookup"><span data-stu-id="6100b-119">After that you may use **VS Code**.</span></span> <span data-ttu-id="6100b-120">Verwenden Sie "vscode" nicht.</span><span class="sxs-lookup"><span data-stu-id="6100b-120">Don't use "VSCode".</span></span>
- <span data-ttu-id="6100b-121">**PowerShell-Erweiterung für Visual Studio Code**: Mit dieser Erweiterung wird VS Code in die bevorzugte IDE für PowerShell umgewandelt.</span><span class="sxs-lookup"><span data-stu-id="6100b-121">**PowerShell Extension for Visual Studio Code** - The extension turns VS Code into the preferred IDE for PowerShell.</span></span> <span data-ttu-id="6100b-122">Bei der ersten Erwähnung sollte der vollständige Name verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6100b-122">At first mention, the full name should be used.</span></span> <span data-ttu-id="6100b-123">Anschließend können Sie **PowerShell-Erweiterung** verwenden.</span><span class="sxs-lookup"><span data-stu-id="6100b-123">After that you may use **PowerShell extension**.</span></span>
- <span data-ttu-id="6100b-124">**Azure PowerShell**: Dies ist die Sammlung von PowerShell-Modulen, mit denen Azure-Dienste verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="6100b-124">**Azure PowerShell** - This is the collection of PowerShell modules used to manage Azure services.</span></span>
- <span data-ttu-id="6100b-125">**Azure PowerShell**: Dies ist die Sammlung von PowerShell-Modulen, mit denen die Hybrid Cloud-Lösung von Microsoft verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="6100b-125">**Azure Stack PowerShell** - This is the collection of PowerShell modules used to manage Microsoft's hybrid cloud solution.</span></span>

## <a name="markdown-specifics"></a><span data-ttu-id="6100b-126">Besonderheiten von Markdown</span><span class="sxs-lookup"><span data-stu-id="6100b-126">Markdown specifics</span></span>

<span data-ttu-id="6100b-127">Das Microsoft Open Publishing System (OPS), mit dem unsere Dokumentation erstellt wird, verwendet [markdig][], um die Markdown-Dokumente zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="6100b-127">The Microsoft Open Publishing System (OPS) that builds our documentation uses [markdig][] to process the Markdown documents.</span></span> <span data-ttu-id="6100b-128">Markdig analysiert die Dokumente auf der Grundlage der Regeln der aktuellen [CommonMark][]-Spezifikation.</span><span class="sxs-lookup"><span data-stu-id="6100b-128">Markdig parses the documents based on the rules of the latest [CommonMark][] specification.</span></span>

<span data-ttu-id="6100b-129">Die neue CommonMark-Spezifikation ist weitaus strenger im Hinblick auf den Aufbau einiger Markdown-Elemente.</span><span class="sxs-lookup"><span data-stu-id="6100b-129">The new CommonMark spec is much stricter about the construction of some Markdown elements.</span></span> <span data-ttu-id="6100b-130">Beachten Sie die Detailinformationen in diesem Dokument genau.</span><span class="sxs-lookup"><span data-stu-id="6100b-130">Pay close attention to the details provided in this document.</span></span>

### <a name="blank-lines-spaces-and-tabs"></a><span data-ttu-id="6100b-131">Leerzeilen, Leerzeichen und Tabstoppzeichen</span><span class="sxs-lookup"><span data-stu-id="6100b-131">Blank lines, spaces, and tabs</span></span>

<span data-ttu-id="6100b-132">Leerzeilen signalisieren darüber hinaus in Markdown das Ende eines Blocks.</span><span class="sxs-lookup"><span data-stu-id="6100b-132">Blank lines also signal the end of a block in Markdown.</span></span> <span data-ttu-id="6100b-133">Zwischen Markdown-Blöcken unterschiedlicher Typen (z. B. zwischen einem Absatz und einer Liste oder einem Header) sollte eine einzelne Leerzeile stehen.</span><span class="sxs-lookup"><span data-stu-id="6100b-133">There should be a single blank between Markdown blocks of different types (for example, between a paragraph and a list or header).</span></span>

<span data-ttu-id="6100b-134">Mehrere aufeinander folgende leere Zeilen werden als einzelne leere Zeile in HTML dargestellt.</span><span class="sxs-lookup"><span data-stu-id="6100b-134">Multiple consecutive blank lines render as a single blank line in HTML.</span></span> <span data-ttu-id="6100b-135">Sie dienen keinem Zweck.</span><span class="sxs-lookup"><span data-stu-id="6100b-135">They serve no purpose.</span></span>
<span data-ttu-id="6100b-136">In einem Codeblock brechen aufeinander folgende leere Zeilen den Codeblock aus.</span><span class="sxs-lookup"><span data-stu-id="6100b-136">Within a code block, consecutive blank lines break the code block.</span></span>

<span data-ttu-id="6100b-137">Entfernen Sie zusätzliche Leerzeichen am Zeilenende.</span><span class="sxs-lookup"><span data-stu-id="6100b-137">Remove extra spaces at the end of lines.</span></span>

> [!NOTE]
> <span data-ttu-id="6100b-138">Abstände sind in Markdown wichtig.</span><span class="sxs-lookup"><span data-stu-id="6100b-138">Spacing is significant in Markdown.</span></span> <span data-ttu-id="6100b-139">Verwenden Sie immer Leerzeichen anstelle harter Tabstoppzeichen.</span><span class="sxs-lookup"><span data-stu-id="6100b-139">Always uses spaces instead of hard tabs.</span></span> <span data-ttu-id="6100b-140">Nachgestellte Leerzeichen können sich auf das Rendern von Markdown auswirken.</span><span class="sxs-lookup"><span data-stu-id="6100b-140">Trailing spaces can change how Markdown renders.</span></span>

### <a name="titles-and-headings"></a><span data-ttu-id="6100b-141">Titel und Überschriften</span><span class="sxs-lookup"><span data-stu-id="6100b-141">Titles and headings</span></span>

<span data-ttu-id="6100b-142">Verwenden Sie nur [ATX-Überschriften][atx] (#-Formatvorlage, im Gegensatz zu Überschriften der `=`- oder `-`-Formatvorlagen).</span><span class="sxs-lookup"><span data-stu-id="6100b-142">Only use [ATX headings][atx] (# style, as opposed to `=` or `-` style headers).</span></span>

- <span data-ttu-id="6100b-143">Verwenden Sie normale Groß-/Kleinschreibung – nur Eigennamen und der erste Buchstabe eines Titels oder einer Überschrift sollten groß geschrieben werden</span><span class="sxs-lookup"><span data-stu-id="6100b-143">Use sentence case - only proper nouns and the first letter of a title or header should be capitalized</span></span>
- <span data-ttu-id="6100b-144">Zwischen dem `#` und dem ersten Buchstaben des Titels muss ein einfaches Leerzeichen stehen</span><span class="sxs-lookup"><span data-stu-id="6100b-144">There must be a single space between the `#` and the first letter of the heading</span></span>
- <span data-ttu-id="6100b-145">Überschriften sollten von einer einzelnen Leerzeile umgeben sein</span><span class="sxs-lookup"><span data-stu-id="6100b-145">Headings should be surrounded by a single blank line</span></span>
- <span data-ttu-id="6100b-146">Nur eine Überschrift der Ebene H1 pro Dokument</span><span class="sxs-lookup"><span data-stu-id="6100b-146">Only one H1 per document</span></span>
- <span data-ttu-id="6100b-147">Überschriftebenen sollten um 1 erhöht werden.</span><span class="sxs-lookup"><span data-stu-id="6100b-147">Header levels should increment by one.</span></span> <span data-ttu-id="6100b-148">Ebenen nicht überspringen</span><span class="sxs-lookup"><span data-stu-id="6100b-148">Don't skip levels</span></span>
- <span data-ttu-id="6100b-149">Verwenden Sie kein Fett oder anderes Markup in Headern.</span><span class="sxs-lookup"><span data-stu-id="6100b-149">Don't use bold or other markup in headers</span></span>

### <a name="limit-line-length-to-100-characters"></a><span data-ttu-id="6100b-150">Begrenzen Sie die Zeilenlänge auf 100 Zeichen</span><span class="sxs-lookup"><span data-stu-id="6100b-150">Limit line length to 100 characters</span></span>

<span data-ttu-id="6100b-151">Dies gilt für konzeptionelle Artikel und die Cmdlet-Referenz.</span><span class="sxs-lookup"><span data-stu-id="6100b-151">This applies to conceptual articles and cmdlet reference.</span></span> <span data-ttu-id="6100b-152">Das Beschränken der Zeilenlänge verbessert die Lesbarkeit von git-Diffs und git-Verlauf.</span><span class="sxs-lookup"><span data-stu-id="6100b-152">Limiting the line length improves the readability of git diffs and history.</span></span> <span data-ttu-id="6100b-153">Es erleichtert außerdem anderen Autoren das Einbringen ihres Beitrags.</span><span class="sxs-lookup"><span data-stu-id="6100b-153">It also makes it easier for other writers to make contributions.</span></span>

<span data-ttu-id="6100b-154">Verwenden Sie die Erweiterung [Reflow Markdown][reflow] in Visual Studio Code, um Absätze komfortabel umzubrechen, sodass sie in die erforderliche Zeilenlänge passen.</span><span class="sxs-lookup"><span data-stu-id="6100b-154">Use the [Reflow Markdown][reflow] extension in Visual Studio Code to easily reflow paragraphs to fit the prescribed line length.</span></span>

<span data-ttu-id="6100b-155">Klassische Hilfethemen (About_topics) sind auf 80 Zeichen beschränkt.</span><span class="sxs-lookup"><span data-stu-id="6100b-155">About_topics are limited to 80 characters.</span></span> <span data-ttu-id="6100b-156">Genauere Informationen finden Sie unter [Formatieren von About_ Dateien](#formatting-about_-files).</span><span class="sxs-lookup"><span data-stu-id="6100b-156">For more specific information, see [Formatting About_ files](#formatting-about_-files).</span></span>

### <a name="lists"></a><span data-ttu-id="6100b-157">Listen</span><span class="sxs-lookup"><span data-stu-id="6100b-157">Lists</span></span>

<span data-ttu-id="6100b-158">Wenn die Liste mehrere Sätze oder Absätze enthält, sollten Sie eine untergeordnete Kopfzeile anstelle einer Liste verwenden.</span><span class="sxs-lookup"><span data-stu-id="6100b-158">If your list contains multiple sentences or paragraphs, consider using a sublevel header rather than a list.</span></span>

<span data-ttu-id="6100b-159">Eine Liste sollte von einer einzelnen Leerzeile umgeben sein.</span><span class="sxs-lookup"><span data-stu-id="6100b-159">List should be surrounded by a single blank line.</span></span>

#### <a name="unordered-lists"></a><span data-ttu-id="6100b-160">Unsortierte Listen</span><span class="sxs-lookup"><span data-stu-id="6100b-160">Unordered lists</span></span>

<span data-ttu-id="6100b-161">Beenden Sie Listenelemente nicht mit einem Zeitraum, es sei denn, Sie enthalten mehrere Sätze.</span><span class="sxs-lookup"><span data-stu-id="6100b-161">Don't end list items with a period unless they contain multiple sentences.</span></span> <span data-ttu-id="6100b-162">Verwenden Sie das Bindestrich Zeichen (`-`) für Listenelement Aufzählungen.</span><span class="sxs-lookup"><span data-stu-id="6100b-162">Use the hyphen character (`-`) for list item bullets.</span></span> <span data-ttu-id="6100b-163">Dadurch wird die Verwechselung mit fettem oder kursivem Markup vermieden, für das das Sternchen [`*`] verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="6100b-163">This avoids confusion with bold or italic markup that uses the asterisk [`*`].</span></span> <span data-ttu-id="6100b-164">Um einen Absatz oder andere Elemente unter einem Aufzählungselement einzuschließen, fügen Sie einen Zeilenumbruch ein, und richten Sie den Einzug am ersten Zeichen nach dem Aufzählungszeichen aus.</span><span class="sxs-lookup"><span data-stu-id="6100b-164">To include a paragraph or other elements under a bullet item, insert a line break and align indentation with the first character after the bullet.</span></span>

<span data-ttu-id="6100b-165">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="6100b-165">For example:</span></span>

```markdown
This is a list that contain child elements under a bullet item.

- First bullet item

  Sentence explaining the first bullet.

  - Child bullet item

    Sentence explaining the child bullet.

- Second bullet item
- Third bullet item
```

<span data-ttu-id="6100b-166">Dies ist eine Liste, die untergeordnete Elemente unter einem Aufzählungs Element enthält.</span><span class="sxs-lookup"><span data-stu-id="6100b-166">This is a list that contains child elements under a bullet item.</span></span>

- <span data-ttu-id="6100b-167">Erstes Aufzählungselement</span><span class="sxs-lookup"><span data-stu-id="6100b-167">First bullet item</span></span>

  <span data-ttu-id="6100b-168">Satz zur Erläuterung des ersten Aufzählungszeichens.</span><span class="sxs-lookup"><span data-stu-id="6100b-168">Sentence explaining the first bullet.</span></span>

  - <span data-ttu-id="6100b-169">Aufzählungs Element</span><span class="sxs-lookup"><span data-stu-id="6100b-169">Child bullet item</span></span>

    <span data-ttu-id="6100b-170">Satz, der die untergeordnete Aufzählung erläutert.</span><span class="sxs-lookup"><span data-stu-id="6100b-170">Sentence explaining the child bullet.</span></span>

- <span data-ttu-id="6100b-171">Zweites Aufzählungszeichen</span><span class="sxs-lookup"><span data-stu-id="6100b-171">Second bullet item</span></span>
- <span data-ttu-id="6100b-172">Drittes Aufzählungszeichen</span><span class="sxs-lookup"><span data-stu-id="6100b-172">Third bullet item</span></span>

#### <a name="ordered-lists"></a><span data-ttu-id="6100b-173">Sortierte Listen</span><span class="sxs-lookup"><span data-stu-id="6100b-173">Ordered lists</span></span>

<span data-ttu-id="6100b-174">Um einen Absatz oder andere Elemente unter einer Aufzählung einzuschließen, richten Sie den Einzug am ersten Zeichen nach der Elementnummer aus.</span><span class="sxs-lookup"><span data-stu-id="6100b-174">To include a paragraph or other elements under a numbered item, align indentation with the first character after the item number.</span></span> <span data-ttu-id="6100b-175">Alle Elemente in einer Liste sollten die Nummer `1.` verwenden, statt jedes einzelne Element zu erhöhen.</span><span class="sxs-lookup"><span data-stu-id="6100b-175">All items in a numbered listed should use the number `1.` rather than incrementing each item.</span></span> <span data-ttu-id="6100b-176">Beim Rendering erhöht Markdown den Wert automatisch.</span><span class="sxs-lookup"><span data-stu-id="6100b-176">Markdown rendering increments the value automatically.</span></span> <span data-ttu-id="6100b-177">Dadurch wird die Neuanordnung von Elementen vereinfacht und der Einzug von untergeordnetem Inhalt standardisiert.</span><span class="sxs-lookup"><span data-stu-id="6100b-177">This makes reordering items easier and standardizes the indentation of subordinate content.</span></span>

<span data-ttu-id="6100b-178">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="6100b-178">For example:</span></span>

```markdown
1. For the first element, insert a single space after the 1. Long sentences should be
   wrapped to the next line and must line up with the first character after the numbered
   list marker.

   To include a second element (like this one), insert a line break after the first
   and align indentations. The indentation of the second element must line up with
   the first character after the numbered list marker. For single digit items, like
   this one, you indent to column 4. For double digits items, for example item number
   10, you indent to column 5.

1. The next numbered item starts here.
```

<span data-ttu-id="6100b-179">Der resultierende Markdown wird wie folgt gerendert:</span><span class="sxs-lookup"><span data-stu-id="6100b-179">The resulting Markdown is rendered as follows:</span></span>

1. <span data-ttu-id="6100b-180">Fügen Sie für das erste Element ein einzelnes Leerzeichen nach der 1 ein.</span><span class="sxs-lookup"><span data-stu-id="6100b-180">For the first element, insert a single space after the 1.</span></span> <span data-ttu-id="6100b-181">Lange Sätze sollten in die nächste Zeile umbrochen werden und müssen am ersten Zeichen hinter dem nummerierten Listenmarker ausgerichtet werden.</span><span class="sxs-lookup"><span data-stu-id="6100b-181">Long sentences should be wrapped to the next line and must line up with the first character after the numbered list marker.</span></span>

   <span data-ttu-id="6100b-182">Um ein zweites Element (wie dieses hier) aufzuführen, fügen Sie nach dem ersten Element einen Zeilenumbruch ein, und richten Sie die Einzüge aus.</span><span class="sxs-lookup"><span data-stu-id="6100b-182">To include a second element (like this one), insert a line break after the first and align indentations.</span></span> <span data-ttu-id="6100b-183">Der Einzug des zweiten Elements muss am ersten Zeichen hinter dem nummerierten Listenmarker ausgerichtet werden.</span><span class="sxs-lookup"><span data-stu-id="6100b-183">The indentation of the second element must line up with the first character after the numbered list marker.</span></span> <span data-ttu-id="6100b-184">Für einstellige Elemente wie dieses ziehen Sie in Spalte 4 ein.</span><span class="sxs-lookup"><span data-stu-id="6100b-184">For single digit items, like this one, you indent to column 4.</span></span> <span data-ttu-id="6100b-185">Für zweistellige Elemente, beispielsweise die Elementnummer 10, ziehen Sie in Spalte 5 ein.</span><span class="sxs-lookup"><span data-stu-id="6100b-185">For double digits items, for example item number 10, you indent to column 5.</span></span>

1. <span data-ttu-id="6100b-186">Das nächste nummerierte Element beginnt hier.</span><span class="sxs-lookup"><span data-stu-id="6100b-186">The next numbered item starts here.</span></span>

### <a name="images"></a><span data-ttu-id="6100b-187">Bilder</span><span class="sxs-lookup"><span data-stu-id="6100b-187">Images</span></span>

<span data-ttu-id="6100b-188">Die Syntax zum Einschließen eines Bilds lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="6100b-188">The syntax to include an image is:</span></span>

```markdown
![[alt text]](<folderPath>)

Example:
![Introduction](./media/overview/Introduction.png)
```

<span data-ttu-id="6100b-189">Dabei stellt `alt text` eine kurze Beschreibung des Bilds und `<folder path>` einen relativen Pfad zum Bild dar.</span><span class="sxs-lookup"><span data-stu-id="6100b-189">Where `alt text` is a brief description of the image and `<folder path>` is a relative path to the image.</span></span> <span data-ttu-id="6100b-190">Alternativtext ist für Bildschirmsprachausgaben für Personen mit eingeschränktem Sehvermögen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="6100b-190">Alternate text is required for screen readers for the visually impaired.</span></span>

<span data-ttu-id="6100b-191">Bilder sollten in einem `media/<article-name>` Ordner innerhalb des Ordners gespeichert werden, der den Artikel enthält.</span><span class="sxs-lookup"><span data-stu-id="6100b-191">Images should be stored in a `media/<article-name>` folder within the folder containing the article.</span></span>
<span data-ttu-id="6100b-192">Geben Sie Bilder nicht zwischen Artikeln frei.</span><span class="sxs-lookup"><span data-stu-id="6100b-192">Don't share images between articles.</span></span> <span data-ttu-id="6100b-193">Erstellen Sie einen Ordner, der mit dem Dateinamen Ihres Artikels im `media`-Ordner übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="6100b-193">Create a folder that matches the filename of your article under the `media` folder.</span></span> <span data-ttu-id="6100b-194">Kopieren Sie die Bilder für diesen Artikel in diesen neuen Ordner.</span><span class="sxs-lookup"><span data-stu-id="6100b-194">Copy the images for that article to that new folder.</span></span> <span data-ttu-id="6100b-195">Wenn ein Bild in mehreren Artikeln verwendet wird, muss jeder Bildordner eine Kopie dieser Bilddatei enthalten.</span><span class="sxs-lookup"><span data-stu-id="6100b-195">If an image is used by multiple articles, each image folder must have a copy of that image file.</span></span> <span data-ttu-id="6100b-196">Durch diese Vorgehensweise wird verhindert, dass eine Änderung an einem Bild in einem Artikel sich auf einen anderen Artikel auswirkt.</span><span class="sxs-lookup"><span data-stu-id="6100b-196">This practice prevents a change to an image in one article affecting another article.</span></span>

<span data-ttu-id="6100b-197">Die folgenden Bild Dateitypen werden unterstützt: `*.png` , `*.gif` , `*.jpeg` , `*.jpg` , `*.svg`</span><span class="sxs-lookup"><span data-stu-id="6100b-197">The following image file types are supported: `*.png`, `*.gif`, `*.jpeg`, `*.jpg`, `*.svg`</span></span>

### <a name="markdown-extensions-supported-by-open-publishing"></a><span data-ttu-id="6100b-198">Von Open Publishing unterstützte Markdownerweiterungen</span><span class="sxs-lookup"><span data-stu-id="6100b-198">Markdown extensions supported by Open Publishing</span></span>

<span data-ttu-id="6100b-199">Das [Microsoft-Dokumentation Authoring Pack](/contribute/how-to-write-docs-auth-pack) enthält Tools, die Features unterstützen, die für unser Veröffentlichungs System eindeutig sind.</span><span class="sxs-lookup"><span data-stu-id="6100b-199">The [Microsoft Docs Authoring Pack](/contribute/how-to-write-docs-auth-pack) contains tools that support features unique to our publishing system.</span></span> <span data-ttu-id="6100b-200">Warnungen sind eine markdown-Erweiterung zum Erstellen von blockanführungs Zeichen, die auf docs.Microsoft.com mit Farben und Symbolen gerengt werden, die die Bedeutung der Inhalte hervorheben.</span><span class="sxs-lookup"><span data-stu-id="6100b-200">Alerts are a Markdown extension to create blockquotes that render on docs.microsoft.com with colors and icons that highlight the significance of the content.</span></span> <span data-ttu-id="6100b-201">Die folgenden Warnungstypen werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="6100b-201">The following alert types are supported:</span></span>

```markdown
> [!NOTE]
> Information the user should notice even if skimming.

> [!TIP]
> Optional information to help a user be more successful.

> [!IMPORTANT]
> Essential information required for user success.

> [!CAUTION]
> Negative potential consequences of an action.

> [!WARNING]
> Dangerous certain consequences of an action.
```

<span data-ttu-id="6100b-202">Diese Warnungen sehen auf docs.microsoft.com folgendermaßen aus:</span><span class="sxs-lookup"><span data-stu-id="6100b-202">These alerts look like this on docs.microsoft.com:</span></span>

<span data-ttu-id="6100b-203">Notizblock</span><span class="sxs-lookup"><span data-stu-id="6100b-203">Note block</span></span>

> [!NOTE]
> <span data-ttu-id="6100b-204">Information the user should notice even if skimming.</span><span class="sxs-lookup"><span data-stu-id="6100b-204">Information the user should notice even if skimming.</span></span>

<span data-ttu-id="6100b-205">Tip-Block</span><span class="sxs-lookup"><span data-stu-id="6100b-205">Tip block</span></span>

> [!TIP]
> <span data-ttu-id="6100b-206">Optional information to help a user be more successful.</span><span class="sxs-lookup"><span data-stu-id="6100b-206">Optional information to help a user be more successful.</span></span>

<span data-ttu-id="6100b-207">Wichtiger Block</span><span class="sxs-lookup"><span data-stu-id="6100b-207">Important block</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6100b-208">Essential information required for user success.</span><span class="sxs-lookup"><span data-stu-id="6100b-208">Essential information required for user success.</span></span>

<span data-ttu-id="6100b-209">Warn Block</span><span class="sxs-lookup"><span data-stu-id="6100b-209">Caution block</span></span>

> [!CAUTION]
> <span data-ttu-id="6100b-210">Negative potential consequences of an action.</span><span class="sxs-lookup"><span data-stu-id="6100b-210">Negative potential consequences of an action.</span></span>

<span data-ttu-id="6100b-211">Warnungs Block</span><span class="sxs-lookup"><span data-stu-id="6100b-211">Warning block</span></span>

> [!WARNING]
> <span data-ttu-id="6100b-212">Gefährliche Folgen einer Aktion.</span><span class="sxs-lookup"><span data-stu-id="6100b-212">Dangerous certain consequences of an action.</span></span>

### <a name="hyperlinks"></a><span data-ttu-id="6100b-213">Links</span><span class="sxs-lookup"><span data-stu-id="6100b-213">Hyperlinks</span></span>

- <span data-ttu-id="6100b-214">Hyperlinks müssen die markdown-Syntax verwenden `[friendlyname](url-or-path)` .</span><span class="sxs-lookup"><span data-stu-id="6100b-214">Hyperlinks must use Markdown syntax `[friendlyname](url-or-path)`.</span></span> <span data-ttu-id="6100b-215">[Link Verweise][linkref] werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="6100b-215">[Link references][linkref] are supported.</span></span>
- <span data-ttu-id="6100b-216">Das Veröffentlichungs System unterstützt drei Arten von Verknüpfungen:</span><span class="sxs-lookup"><span data-stu-id="6100b-216">The publishing system supports three types of links:</span></span>
  - <span data-ttu-id="6100b-217">URL-Links</span><span class="sxs-lookup"><span data-stu-id="6100b-217">URL links</span></span>
  - <span data-ttu-id="6100b-218">Datei Verknüpfungen</span><span class="sxs-lookup"><span data-stu-id="6100b-218">File links</span></span>
  - <span data-ttu-id="6100b-219">Querverweis Verknüpfungen</span><span class="sxs-lookup"><span data-stu-id="6100b-219">Cross-reference links</span></span>
- <span data-ttu-id="6100b-220">Links zu anderen Artikeln auf docs.Microsoft.com müssen Site relative Pfade sein.</span><span class="sxs-lookup"><span data-stu-id="6100b-220">Links to other articles on docs.microsoft.com must be site-relative paths</span></span>
- <span data-ttu-id="6100b-221">Alle URLs für externe Websites sollten HTTPS verwenden, es sei denn, der Ziel Standort ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="6100b-221">All URLs to external websites should use HTTPS unless that isn't valid for the target site.</span></span>
- <span data-ttu-id="6100b-222">Links müssen einen anzeigen Amen haben, in der Regel den Titel des verknüpften Artikels.</span><span class="sxs-lookup"><span data-stu-id="6100b-222">Links must have a friendly name, usually the title of the linked article</span></span>
- <span data-ttu-id="6100b-223">Alle Elemente im Abschnitt _verknüpfte Verknüpfungen_ im unteren Bereich sollten hyperverknüpft werden.</span><span class="sxs-lookup"><span data-stu-id="6100b-223">All items in the _Related links_ section at the bottom should be hyperlinked</span></span>
- <span data-ttu-id="6100b-224">Verwenden Sie keine Backticks, Fett oder andere Markup innerhalb der Klammern eines Links.</span><span class="sxs-lookup"><span data-stu-id="6100b-224">Don't use backticks, bold, or other markup inside the brackets of a hyperlink.</span></span>
- <span data-ttu-id="6100b-225">Bare-URLs können verwendet werden, wenn Sie einen bestimmten URI dokumentieren.</span><span class="sxs-lookup"><span data-stu-id="6100b-225">Bare URLs may be used when you're documenting a specific URI.</span></span> <span data-ttu-id="6100b-226">Der URI muss in Backticks eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="6100b-226">The URI must be enclosed in backticks.</span></span> <span data-ttu-id="6100b-227">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="6100b-227">For example:</span></span>

  ```markdown
  By default, if you don't specify this parameter, the DMTF standard resource URI
  `http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/` is used and the class name is appended to it.
  ```

#### <a name="linking-to-other-content-on-docsmicrosoftcom"></a><span data-ttu-id="6100b-228">Verknüpfen mit anderem Inhalt auf docs.Microsoft.com</span><span class="sxs-lookup"><span data-stu-id="6100b-228">Linking to other content on docs.microsoft.com</span></span>

- <span data-ttu-id="6100b-229">**URL-Links** zu anderen Artikeln auf docs.Microsoft.com müssen Site relative Pfade sein.</span><span class="sxs-lookup"><span data-stu-id="6100b-229">**URL links** to other articles on docs.microsoft.com must be site-relative paths.</span></span> <span data-ttu-id="6100b-230">Die einfachste Möglichkeit, eine relative Verknüpfung zu erstellen, besteht darin, die URL aus dem Browser zu kopieren und dann aus dem Wert zu entfernen, den `https://docs.microsoft.com/en-us` Sie in markdown eingefügt haben.</span><span class="sxs-lookup"><span data-stu-id="6100b-230">The simplest way to create a relative link is to copy the URL from your browser then remove `https://docs.microsoft.com/en-us` from the value you paste into markdown.</span></span> <span data-ttu-id="6100b-231">Gebiets Schemas nicht in URLs in Microsoft-Eigenschaften einschließen (Remove `/en-us` from URL).</span><span class="sxs-lookup"><span data-stu-id="6100b-231">Don't include locales in URLs on Microsoft properties (remove `/en-us` from URL).</span></span> <span data-ttu-id="6100b-232">Entfernen Sie alle unnötigen Abfrage Parameter aus der URL.</span><span class="sxs-lookup"><span data-stu-id="6100b-232">Remove any unnecessary query parameters from the URL.</span></span> <span data-ttu-id="6100b-233">Zu entfernende Beispiele:</span><span class="sxs-lookup"><span data-stu-id="6100b-233">Examples that should be removed:</span></span>

  - <span data-ttu-id="6100b-234">`?view=powershell-5.1` : wird zum Verknüpfen mit einer bestimmten Version von PowerShell verwendet.</span><span class="sxs-lookup"><span data-stu-id="6100b-234">`?view=powershell-5.1` - used to link to a specific version of PowerShell</span></span>
  - <span data-ttu-id="6100b-235">`?redirectedfrom=MSDN` -wird der URL hinzugefügt, wenn Sie von einem alten Artikel an den neuen Speicherort umgeleitet werden</span><span class="sxs-lookup"><span data-stu-id="6100b-235">`?redirectedfrom=MSDN` - added to the URL when you get redirected from an old article to its new location</span></span>

  <span data-ttu-id="6100b-236">Wenn Sie eine Verknüpfung mit einer bestimmten Version eines Dokuments herstellen müssen, müssen Sie den `&preserve_view=true` Parameter der Abfrage Zeichenfolge hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="6100b-236">If you need to link to a specific version of a document, then you need to add the `&preserve_view=true` parameter to the query string.</span></span> <span data-ttu-id="6100b-237">Beispiel: `?view=powershell-5.1&preserve_view=true`</span><span class="sxs-lookup"><span data-stu-id="6100b-237">For example: `?view=powershell-5.1&preserve_view=true`</span></span>

- <span data-ttu-id="6100b-238">Ein **Dateilink** wird verwendet, um eine Verknüpfung zwischen Verweis Artikeln oder einem konzeptionellen Artikel zu einem anderen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="6100b-238">A **file link** is used to link from one reference article to another, or from one conceptual article to another.</span></span> <span data-ttu-id="6100b-239">Wenn Sie eine Verknüpfung mit einem Referenz Artikel für eine bestimmte Version von PowerShell herstellen müssen, müssen Sie einen URL-Link verwenden.</span><span class="sxs-lookup"><span data-stu-id="6100b-239">If you need to link to a reference article for a specific version of PowerShell, then you must use a URL link.</span></span>

  - <span data-ttu-id="6100b-240">Datei Verknüpfungen enthalten einen relativen Dateipfad (Beispiel: `../folder/file.md` ).</span><span class="sxs-lookup"><span data-stu-id="6100b-240">File links contain a relative file path (for example: `../folder/file.md`)</span></span>
  - <span data-ttu-id="6100b-241">Alle Dateipfade verwenden Schrägstriche ( `/` ).</span><span class="sxs-lookup"><span data-stu-id="6100b-241">All file paths use forward-slash (`/`) characters</span></span>

- <span data-ttu-id="6100b-242">**Querverweis Verknüpfungen** sind eine spezielle Funktion, die vom Veröffentlichungs System unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="6100b-242">**Cross-reference links** are a special feature supported by the publishing system.</span></span> <span data-ttu-id="6100b-243">Sie können Verweis übergreifende Links in konzeptionellen Artikeln verwenden, um eine Verknüpfung mit der .NET-API oder der Cmdlet-Referenz zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="6100b-243">You can use cross-reference links in conceptual articles to link to .NET API or cmdlet reference.</span></span>

  <span data-ttu-id="6100b-244">Links zur .NET-API-Referenz finden Sie unter [Verwenden von Links in der Dokumentation](/contribute/how-to-write-links#xref-cross-reference-links) im Leitfaden "zentrale Mitwirkende".</span><span class="sxs-lookup"><span data-stu-id="6100b-244">For links to .NET API reference, see [Use links in documentation](/contribute/how-to-write-links#xref-cross-reference-links) in the central Contributor Guide.</span></span>

  <span data-ttu-id="6100b-245">Links zur Cmdlet-Referenz haben das folgende Format: `xref:<module-name>.<cmdlet-name>` .</span><span class="sxs-lookup"><span data-stu-id="6100b-245">Links to cmdlet reference have the following format: `xref:<module-name>.<cmdlet-name>`.</span></span> <span data-ttu-id="6100b-246">Beispielsweise, um eine Verknüpfung mit dem- `Get-Content` Cmdlet im **Microsoft. PowerShell. Management** -Modul zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="6100b-246">For example, to link to the `Get-Content` cmdlet in the **Microsoft.PowerShell.Management** module.</span></span>

  `[Get-Content](xref:Microsoft.PowerShell.Management.Get-Content)`

<span data-ttu-id="6100b-247">Deep Linking ist sowohl für URL-als auch für Datei Verknüpfungen zulässig.</span><span class="sxs-lookup"><span data-stu-id="6100b-247">Deep linking is allowed on both URL and file links.</span></span> <span data-ttu-id="6100b-248">Fügen Sie den Anker am Ende des Zielpfads hinzu.</span><span class="sxs-lookup"><span data-stu-id="6100b-248">Add the anchor to the end of the target path.</span></span>
<span data-ttu-id="6100b-249">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="6100b-249">For example:</span></span>

- `[about_Splatting](about_Splatting.md#splatting-with-arrays)`
- `[custom key bindings](https://code.visualstudio.com/docs/getstarted/keybindings#_custom-keybindings-for-refactorings)`

<span data-ttu-id="6100b-250">Weitere Informationen finden Sie unter [Verwenden von Links in der Dokumentation](/contribute/how-to-write-links).</span><span class="sxs-lookup"><span data-stu-id="6100b-250">For more information, see [Use links in documentation](/contribute/how-to-write-links).</span></span>

## <a name="formatting-command-syntax-elements"></a><span data-ttu-id="6100b-251">Formatieren von Befehlssyntaxelementen</span><span class="sxs-lookup"><span data-stu-id="6100b-251">Formatting command syntax elements</span></span>

- <span data-ttu-id="6100b-252">Verwenden Sie immer den vollständigen Namen für Cmdlets und Parameter.</span><span class="sxs-lookup"><span data-stu-id="6100b-252">Always use the full name for cmdlets and parameters.</span></span> <span data-ttu-id="6100b-253">Vermeiden Sie die Verwendung von Aliasen, es sei denn, Sie demonstrieren den Alias.</span><span class="sxs-lookup"><span data-stu-id="6100b-253">Avoid using aliases unless you're specifically demonstrating the alias.</span></span>

- <span data-ttu-id="6100b-254">Eigenschaft, Parameter, Objekt, Typnamen, Klassennamen und Klassen Methoden sollten **Fett** formatiert sein.</span><span class="sxs-lookup"><span data-stu-id="6100b-254">Property, parameter, object, type names, class names, class methods should be **bold**.</span></span>
  - <span data-ttu-id="6100b-255">Eigenschafts-und Parameterwerte sollten in Graviszeichen ( `` ` `` ) verpackt werden.</span><span class="sxs-lookup"><span data-stu-id="6100b-255">Property and parameter values should be wrapped in backticks (`` ` ``).</span></span>
  - <span data-ttu-id="6100b-256">Verwenden Sie Backticks, wenn Sie auf Typen verweisen, die in Klammern stehen.</span><span class="sxs-lookup"><span data-stu-id="6100b-256">When referring to types using the bracketed style, use backticks.</span></span> <span data-ttu-id="6100b-257">Beispiel: `[System.Io.FileInfo]`</span><span class="sxs-lookup"><span data-stu-id="6100b-257">For example: `[System.Io.FileInfo]`</span></span>

- <span data-ttu-id="6100b-258">Sprach Schlüsselwörter, Namen von Cmdlets, Funktionen, Variablen, systemeigene EXE-Dateien, Dateipfade und Inline Syntax Beispiele sollten in Graviszeichen ()-Zeichen umschließt werden `` ` `` .</span><span class="sxs-lookup"><span data-stu-id="6100b-258">Language keywords, cmdlet names, functions, variables, native EXEs, file paths, and inline syntax examples should be wrapped in backtick (`` ` ``) characters.</span></span>

  <span data-ttu-id="6100b-259">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="6100b-259">For example:</span></span>

  ~~~markdown
  The following code uses `Get-ChildItem` to list the contents of `C:\Windows` and assigns
  the output to the `$files` variable.

  ```powershell
  $files = Get-ChildItem C:\Windows
  ```
  ~~~

  - <span data-ttu-id="6100b-260">Wenn Sie einen Parameter bei Namen nennen, sollte der Name **fett** geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="6100b-260">When referring to a parameter by name, the name should be **bold**.</span></span> <span data-ttu-id="6100b-261">Wenn Sie die Verwendung eines Parameters mithilfe eines Bindestrichs als Präfix darstellen, sollte der Parameter von Backticks umschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="6100b-261">When illustrating the use of a parameter with the hyphen prefix, the parameter should be wrapped in backticks.</span></span> <span data-ttu-id="6100b-262">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="6100b-262">For example:</span></span>

    ```markdown
    The parameter's name is **Name**, but it's typed as `-Name` when used on the command
    line as a parameter.
    ```

  - <span data-ttu-id="6100b-263">Wenn Sie die Verwendung eines externen Befehls veranschaulichen, sollte das Beispiel von Backticks umschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="6100b-263">When showing example usage of an external command, the example should be wrapped in backticks.</span></span>
    <span data-ttu-id="6100b-264">Fügen Sie die Dateierweiterung immer in den nativen Befehl ein.</span><span class="sxs-lookup"><span data-stu-id="6100b-264">Always include the file extension in the native command.</span></span> <span data-ttu-id="6100b-265">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="6100b-265">For example:</span></span>

    ```markdown
    To start the spooler service on a remote computer named DC01, you type `sc.exe \\DC01 start spooler`.
    ```

    <span data-ttu-id="6100b-266">Durch einschließen der Dateierweiterung wird sichergestellt, dass der richtige Befehl entsprechend der Befehls Rangfolge von PowerShell ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="6100b-266">Including the file extension ensures that the correct command is executed according to PowerShell's command precedence.</span></span>

- <span data-ttu-id="6100b-267">Wenn Sie einen Konzeptartikel schreiben (im Gegensatz zu Referenzinhalten), sollte das erste Vorkommnis eines Cmdlet-Namens ein Link zur Dokumentation des Cmdlets sein.</span><span class="sxs-lookup"><span data-stu-id="6100b-267">When writing a conceptual article (as opposed to reference content), the first instance of a cmdlet name should be hyperlinked to the cmdlet documentation.</span></span> <span data-ttu-id="6100b-268">Verwenden Sie keine Backticks, Fett oder andere Markup innerhalb der Klammern eines Links.</span><span class="sxs-lookup"><span data-stu-id="6100b-268">Don't use backticks, bold, or other markup inside the brackets of a hyperlink.</span></span>

  <span data-ttu-id="6100b-269">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="6100b-269">For example:</span></span>

  ```markdown
  This [Write-Host](/powershell/module/Microsoft.PowerShell.Utility/Write-Host) cmdlet
  uses the **Object** parameter to ...
  ```

  <span data-ttu-id="6100b-270">Weitere Informationen finden Sie in diesem Artikel im Abschnitt [Hyperlinks](#hyperlinks) .</span><span class="sxs-lookup"><span data-stu-id="6100b-270">For more information, see [Hyperlinks](#hyperlinks) section of this article.</span></span>

## <a name="markdown-for-code-samples"></a><span data-ttu-id="6100b-271">Markdown für Codebeispiele</span><span class="sxs-lookup"><span data-stu-id="6100b-271">Markdown for code samples</span></span>

<span data-ttu-id="6100b-272">Markdown unterstützt zwei verschiedene Codestile:</span><span class="sxs-lookup"><span data-stu-id="6100b-272">Markdown supports two different code styles:</span></span>

- <span data-ttu-id="6100b-273">**Code spannen (Inline)** : gekennzeichnet durch ein einzelnes Graviszeichen ( `` ` `` ).</span><span class="sxs-lookup"><span data-stu-id="6100b-273">**Code spans (inline)** - marked by a single backtick (`` ` ``) character.</span></span> <span data-ttu-id="6100b-274">Wird in einem Absatz anstelle als eigenständiger Block verwendet.</span><span class="sxs-lookup"><span data-stu-id="6100b-274">Used within a paragraph rather than as a standalone block.</span></span>
- <span data-ttu-id="6100b-275">**Code Blöcke** : ein mehrzeiligen Block, der von Triple-Backtick ()-Zeichen folgen umgeben ist `` ``` `` .</span><span class="sxs-lookup"><span data-stu-id="6100b-275">**Code blocks** - a multi-line block surrounded by triple-backtick (`` ``` ``) strings.</span></span> <span data-ttu-id="6100b-276">Code Blöcke können auch über eine sprach Bezeichnung verfügen, die den Backticks folgt.</span><span class="sxs-lookup"><span data-stu-id="6100b-276">Code blocks may also have a language label following the backticks.</span></span> <span data-ttu-id="6100b-277">Die sprach Bezeichnung ermöglicht die Syntax Hervorhebung für den Inhalt des Code Blocks.</span><span class="sxs-lookup"><span data-stu-id="6100b-277">The language label enables syntax highlighting for the contents of the code block.</span></span>

<span data-ttu-id="6100b-278">Alle Codeblöcke sollten in einem Codefence enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="6100b-278">All code blocks should be contained in a code fence.</span></span> <span data-ttu-id="6100b-279">Verwenden Sie niemals den Einzug für Code Blöcke.</span><span class="sxs-lookup"><span data-stu-id="6100b-279">Never use indentation for code blocks.</span></span> <span data-ttu-id="6100b-280">Markdown lässt dieses Muster zu, kann jedoch problematisch sein und sollte vermieden werden.</span><span class="sxs-lookup"><span data-stu-id="6100b-280">Markdown allows this pattern but it can be problematic and should be avoided.</span></span>

<span data-ttu-id="6100b-281">Ein Codeblock ist eine oder mehrere Codezeilen, die von einem Code-Fence mit dreifacher Backtick () umgeben sind `` ``` `` .</span><span class="sxs-lookup"><span data-stu-id="6100b-281">A code block is one or more lines of code surrounded by a triple-backtick (`` ``` ``) code fence.</span></span>
<span data-ttu-id="6100b-282">Die Codefencemarker müssen vor und nach dem Codebeispiel in einer eigenen Zeile stehen.</span><span class="sxs-lookup"><span data-stu-id="6100b-282">The code fence markers must be on their own line before and after the code sample.</span></span> <span data-ttu-id="6100b-283">Der Marker am Anfang des Codeblocks kann eine optionale Sprachbezeichnung aufweisen.</span><span class="sxs-lookup"><span data-stu-id="6100b-283">The marker at the start of the code block may have an optional language label.</span></span> <span data-ttu-id="6100b-284">Das Open Publishing System (OPS) von Microsoft verwendet die Sprachbezeichnung, um die Funktion der Syntaxhervorhebung zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="6100b-284">Microsoft's Open Publishing System (OPS) uses the language label to support the syntax highlighting feature.</span></span>

<span data-ttu-id="6100b-285">Eine vollständige Liste der unterstützten Sprachen [Tags finden Sie im Leitfaden zu den](/contribute/code-in-docs#fenced-code-blocks) zentralisierten Mitwirkenden.</span><span class="sxs-lookup"><span data-stu-id="6100b-285">For a full list of supported language tags, see [Fenced code blocks](/contribute/code-in-docs#fenced-code-blocks) in the centralized contributor guide.</span></span>

<span data-ttu-id="6100b-286">OPS fügt auch eine **Kopieren**-Schaltfläche hinzu, mit der der Inhalt des Codeblocks in die Zwischenablage kopiert wird.</span><span class="sxs-lookup"><span data-stu-id="6100b-286">OPS also adds a **Copy** button that copies the contents of the code block to the clipboard.</span></span> <span data-ttu-id="6100b-287">Dies ermöglicht es Ihnen, den Code schnell in ein Skript einzufügen, um das Codebeispiel zu testen.</span><span class="sxs-lookup"><span data-stu-id="6100b-287">This allows you to quickly paste the code into a script to test the code sample.</span></span> <span data-ttu-id="6100b-288">Allerdings sind nicht alle Beispiele in unserer Dokumentation unverändert auszuführen.</span><span class="sxs-lookup"><span data-stu-id="6100b-288">However, not all examples in our documentation are intended to be run as-is.</span></span> <span data-ttu-id="6100b-289">Einige Code Blöcke sind einfache Abbildungen eines PowerShell-Konzepts.</span><span class="sxs-lookup"><span data-stu-id="6100b-289">Some code blocks are simple illustrations of a PowerShell concept.</span></span>

<span data-ttu-id="6100b-290">Es gibt drei Typen von Code Blöcken, die in unserer Dokumentation verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="6100b-290">There are three types code blocks used in our documentation:</span></span>

1. <span data-ttu-id="6100b-291">Syntax Blöcke</span><span class="sxs-lookup"><span data-stu-id="6100b-291">Syntax blocks</span></span>
1. <span data-ttu-id="6100b-292">Anschauliche Beispiele</span><span class="sxs-lookup"><span data-stu-id="6100b-292">Illustrative examples</span></span>
1. <span data-ttu-id="6100b-293">Ausführbare Beispiele</span><span class="sxs-lookup"><span data-stu-id="6100b-293">Executable examples</span></span>

### <a name="syntax-code-blocks"></a><span data-ttu-id="6100b-294">Syntax Code Blöcke</span><span class="sxs-lookup"><span data-stu-id="6100b-294">Syntax code blocks</span></span>

<span data-ttu-id="6100b-295">Syntax Code Blöcke werden verwendet, um die syntaktische Struktur eines Befehls zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="6100b-295">Syntax code blocks are used to describe the syntactic structure of a command.</span></span> <span data-ttu-id="6100b-296">Verwenden Sie für den codefence kein Sprachtag.</span><span class="sxs-lookup"><span data-stu-id="6100b-296">Don't use a language tag on the code fence.</span></span> <span data-ttu-id="6100b-297">In diesem Beispiel werden alle möglichen Parameter des `Get-Command`-Cmdlets veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="6100b-297">This example illustrates all the possible parameters of the `Get-Command` cmdlet.</span></span>

~~~markdown
```
Get-Command [-Verb <String[]>] [-Noun <String[]>] [-Module <String[]>]
  [-FullyQualifiedModule <ModuleSpecification[]>] [-TotalCount <Int32>] [-Syntax]
  [-ShowCommandInfo] [[-ArgumentList] <Object[]>] [-All] [-ListImported]
  [-ParameterName <String[]>] [-ParameterType <PSTypeName[]>] [<CommonParameters>]
```
~~~

<span data-ttu-id="6100b-298">In diesem Beispiel wird die `for`-Anweisung in allgemeinen Begriffen beschrieben:</span><span class="sxs-lookup"><span data-stu-id="6100b-298">This example describes the `for` statement in generalized terms:</span></span>

~~~markdown
```
for (<init>; <condition>; <repeat>)
{<statement list>}
```
~~~

### <a name="illustrative-examples"></a><span data-ttu-id="6100b-299">Anschauliche Beispiele</span><span class="sxs-lookup"><span data-stu-id="6100b-299">Illustrative examples</span></span>

<span data-ttu-id="6100b-300">Anschauliche Beispiele werden zur Erklärung eines PowerShell-Konzepts verwendet.</span><span class="sxs-lookup"><span data-stu-id="6100b-300">Illustrative examples are used to explain a PowerShell concept.</span></span> <span data-ttu-id="6100b-301">Sie sollen nicht zur Ausführung in die Zwischenablage kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="6100b-301">They aren't meant to be copied to the clipboard for execution.</span></span> <span data-ttu-id="6100b-302">Diese werden am häufigsten für einfache Beispiele verwendet, die einfach zu finden und leicht verständlich sind.</span><span class="sxs-lookup"><span data-stu-id="6100b-302">These are most commonly used for simple examples that are easy to type and easy to understand.</span></span> <span data-ttu-id="6100b-303">Der Codeblock kann die PowerShell-Eingabeaufforderung und Beispielausgabe enthalten.</span><span class="sxs-lookup"><span data-stu-id="6100b-303">The code block can include the PowerShell prompt and example output.</span></span>

<span data-ttu-id="6100b-304">Im folgenden finden Sie ein einfaches Beispiel zur Veranschaulichung der PowerShell-Vergleichs Operatoren.</span><span class="sxs-lookup"><span data-stu-id="6100b-304">Here's a simple example illustrating the PowerShell comparison operators.</span></span> <span data-ttu-id="6100b-305">In diesem Fall ist es nicht beabsichtigt, dieses Beispiel zu kopieren und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="6100b-305">In this case, we don't intend the reader to copy and run this example.</span></span>

~~~markdown
```powershell
PS> 2 -eq 2
True

PS> 2 -eq 3
False

PS> 1,2,3 -eq 2
2

PS> "abc" -eq "abc"
True

PS> "abc" -eq "abc", "def"
False

PS> "abc", "def" -eq "abc"
abc
```
~~~

### <a name="executable-examples"></a><span data-ttu-id="6100b-306">Ausführbare Beispiele</span><span class="sxs-lookup"><span data-stu-id="6100b-306">Executable examples</span></span>

<span data-ttu-id="6100b-307">Komplexe Beispiele oder Beispiele, die kopiert und ausgeführt werden sollen, sollten das folgende Markup im Block Format verwenden:</span><span class="sxs-lookup"><span data-stu-id="6100b-307">Complex examples, or examples that are intended to be copied and executed, should use the following block-style markup:</span></span>

~~~markdown
```powershell
<Your PowerShell code goes here>
```
~~~

<span data-ttu-id="6100b-308">Die von PowerShell-Befehlen angezeigte Ausgabe sollte in einen **Ausgabe**-Codeblock eingeschlossen werden, um die Syntaxhervorhebung zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="6100b-308">The output displayed by PowerShell commands should be enclosed in an **Output** code block to prevent syntax highlighting.</span></span> <span data-ttu-id="6100b-309">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="6100b-309">For example:</span></span>

~~~markdown
```powershell
Get-Command -Module Microsoft.PowerShell.Security
```

```Output
CommandType  Name                        Version    Source
-----------  ----                        -------    ------
Cmdlet       ConvertFrom-SecureString    3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       ConvertTo-SecureString      3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       Get-Acl                     3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       Get-AuthenticodeSignature   3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       Get-CmsMessage              3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       Get-Credential              3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       Get-ExecutionPolicy         3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       Get-PfxCertificate          3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       New-FileCatalog             3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       Protect-CmsMessage          3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       Set-Acl                     3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       Set-AuthenticodeSignature   3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       Set-ExecutionPolicy         3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       Test-FileCatalog            3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       Unprotect-CmsMessage        3.0.0.0    Microsoft.PowerShell.Security
```
~~~

<span data-ttu-id="6100b-310">Die **Ausgabe** Code Bezeichnung ist keine offizielle "Sprache", die vom System für die Syntax Hervorhebung unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="6100b-310">The **Output** code label isn't an official "language" supported by the syntax highlighting system.</span></span>
<span data-ttu-id="6100b-311">Diese Bezeichnung ist jedoch nützlich, da OPS dem Code Feld Rahmen auf der Webseite die Bezeichnung "Output" hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="6100b-311">However, this label is useful because OPS adds the "Output" label to the code box frame on the web page.</span></span> <span data-ttu-id="6100b-312">Das Codefeld "Output" hat keine Syntax Hervorhebung.</span><span class="sxs-lookup"><span data-stu-id="6100b-312">The "Output" code box has no syntax highlighting.</span></span>

## <a name="coding-style-rules"></a><span data-ttu-id="6100b-313">Codierungsstilregeln</span><span class="sxs-lookup"><span data-stu-id="6100b-313">Coding style rules</span></span>

### <a name="avoid-line-continuation-in-code-samples"></a><span data-ttu-id="6100b-314">Vermeiden von Zeilenfortsetzungen in Codebeispielen</span><span class="sxs-lookup"><span data-stu-id="6100b-314">Avoid line continuation in code samples</span></span>

<span data-ttu-id="6100b-315">Vermeiden Sie Zeilenfortsetzungszeichen (`` ` ``) in PowerShell-Codebeispielen.</span><span class="sxs-lookup"><span data-stu-id="6100b-315">Avoid using line continuation characters (`` ` ``) in PowerShell code examples.</span></span> <span data-ttu-id="6100b-316">Diese sind schwer zu erkennen und können Probleme verursachen, wenn am Ende der Zeile zusätzliche Leerzeichen vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="6100b-316">These are hard to see and can cause problems if there are extra spaces at the end of the line.</span></span>

- <span data-ttu-id="6100b-317">Verwenden Sie PowerShell-Verteilung, um die Zeilenlänge für Cmdlets mit mehreren Parametern zu verringern.</span><span class="sxs-lookup"><span data-stu-id="6100b-317">Use PowerShell splatting to reduce line length for cmdlets that have several parameters.</span></span>
- <span data-ttu-id="6100b-318">Profitieren Sie von den Vorteilen der natürlichen Zeilen Umbruchs von PowerShell, wie z. b. nach senkrechter Zeichen (), `|` öffnenden geschweiften Klammern ( `{` ), Klammern ( `(` ) und eckigen Klammern ( `[` ).</span><span class="sxs-lookup"><span data-stu-id="6100b-318">Take advantage of PowerShell's natural line break opportunities, like after pipe (`|`) characters, opening braces (`{`), parentheses (`(`), and brackets (`[`).</span></span>

### <a name="avoid-using-powershell-prompts-in-examples"></a><span data-ttu-id="6100b-319">Vermeiden Sie die Verwendung von PowerShell-Eingabeaufforderungen in Beispielen</span><span class="sxs-lookup"><span data-stu-id="6100b-319">Avoid using PowerShell prompts in examples</span></span>

<span data-ttu-id="6100b-320">Die Verwendung der Eingabe Aufforderungs Zeichenfolge wird davon abgeraten und sollte auf Szenarien beschränkt sein, die zur Veranschaulichung der Befehlszeilen Verwendung dienen.</span><span class="sxs-lookup"><span data-stu-id="6100b-320">Use of the prompt string is discouraged and should be limited to scenarios that are meant to illustrate command-line usage.</span></span> <span data-ttu-id="6100b-321">Für die meisten dieser Beispiele sollte die Eingabe Aufforderungs Zeichenfolge lauten `PS>` .</span><span class="sxs-lookup"><span data-stu-id="6100b-321">For most of these examples, the prompt string should be `PS>`.</span></span> <span data-ttu-id="6100b-322">Diese Eingabeaufforderung ist unabhängig von betriebssystemspezifischen Indikatoren.</span><span class="sxs-lookup"><span data-stu-id="6100b-322">This prompt is independent of OS-specific indicators.</span></span>

<span data-ttu-id="6100b-323">In Beispielen sind Aufforderungen erforderlich, um Befehle zu veranschaulichen, mit denen die Eingabeaufforderung geändert wird, oder wenn der angezeigte Pfad für das Szenario wichtig ist.</span><span class="sxs-lookup"><span data-stu-id="6100b-323">Prompts are required in examples to illustrate commands that alter the prompt or when the path displayed is significant to the scenario.</span></span> <span data-ttu-id="6100b-324">Im folgenden Beispiel wird veranschaulicht, wie die Eingabeaufforderung geändert wird, wenn der Registrierungsanbieter verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="6100b-324">The following example illustrates how the prompt changes when using the Registry provider.</span></span>

```powershell
PS C:\> cd HKCU:\System\
PS HKCU:\System\> dir

    Hive: HKEY_CURRENT_USER\System

Name                   Property
----                   --------
CurrentControlSet
GameConfigStore        GameDVR_Enabled                       : 1
                       GameDVR_FSEBehaviorMode               : 2
                       Win32_AutoGameModeDefaultProfile      : {2, 0, 1, 0...}
                       Win32_GameModeRelatedProcesses        : {1, 0, 1, 0...}
                       GameDVR_HonorUserFSEBehaviorMode      : 0
                       GameDVR_DXGIHonorFSEWindowsCompatible : 0
```

### <a name="dont-use-aliases-in-examples"></a><span data-ttu-id="6100b-325">Verwenden Sie in Beispielen keine Aliase.</span><span class="sxs-lookup"><span data-stu-id="6100b-325">Don't use aliases in examples</span></span>

<span data-ttu-id="6100b-326">Verwenden Sie den vollständigen Namen aller Cmdlets und Parameter, es sei denn, Sie dokumentieren den Alias.</span><span class="sxs-lookup"><span data-stu-id="6100b-326">Use the full name of all cmdlets and parameters unless you're specifically documenting the alias.</span></span>
<span data-ttu-id="6100b-327">Cmdlet-und Parameternamen müssen die richtigen [Pascal-][] Schreib Namen verwenden.</span><span class="sxs-lookup"><span data-stu-id="6100b-327">Cmdlet and parameter names must use the proper [Pascal-cased][] names.</span></span>

### <a name="using-parameters-in-examples"></a><span data-ttu-id="6100b-328">Verwenden der Parameter in Beispielen</span><span class="sxs-lookup"><span data-stu-id="6100b-328">Using parameters in examples</span></span>

<span data-ttu-id="6100b-329">Vermeiden Sie Positionsparameter.</span><span class="sxs-lookup"><span data-stu-id="6100b-329">Avoid using positional parameters.</span></span> <span data-ttu-id="6100b-330">Im Allgemeinen sollten Sie immer den Parameternamen in ein Beispiel einschließen, auch wenn der Parameter eine positionelle ist.</span><span class="sxs-lookup"><span data-stu-id="6100b-330">In general, you should always include the parameter name in an example, even if the parameter is positional.</span></span> <span data-ttu-id="6100b-331">Dadurch kommt es zu weniger Verwirrung in Ihren Beispielen.</span><span class="sxs-lookup"><span data-stu-id="6100b-331">This reduces the chance of confusion in your examples.</span></span>

## <a name="formatting-cmdlet-reference-articles"></a><span data-ttu-id="6100b-332">Cmdlet-Referenz Artikel zum Formatieren</span><span class="sxs-lookup"><span data-stu-id="6100b-332">Formatting cmdlet reference articles</span></span>

<span data-ttu-id="6100b-333">Cmdlet-Referenzartikel weisen eine bestimmte Struktur auf.</span><span class="sxs-lookup"><span data-stu-id="6100b-333">Cmdlet reference articles have a specific structure.</span></span> <span data-ttu-id="6100b-334">Diese Struktur wird von [PlatyPS][] definiert.</span><span class="sxs-lookup"><span data-stu-id="6100b-334">This structure is defined by [PlatyPS][].</span></span>
<span data-ttu-id="6100b-335">Platyps generiert die Cmdlet-Hilfe für PowerShell-Module in markdown.</span><span class="sxs-lookup"><span data-stu-id="6100b-335">PlatyPS generates the cmdlet help for PowerShell modules in Markdown.</span></span> <span data-ttu-id="6100b-336">Nachdem die Markdowndateien bearbeitet wurden, wird PlatyPS zum Erstellen der MAML-Hilfsdateien für das Cmdlet `Get-Help` verwendet.</span><span class="sxs-lookup"><span data-stu-id="6100b-336">After editing the Markdown files, PlatyPS is used create the MAML help files used by the `Get-Help` cmdlet.</span></span>

<span data-ttu-id="6100b-337">PlatyPS verfügt über ein hartcodiertes Schema für Cmdlet-Referenzen, das im Code enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="6100b-337">PlatyPS has a hard-coded schema for cmdlet reference that is written into the code.</span></span> <span data-ttu-id="6100b-338">Im Dokument [platyPS.schema.md][] wird diese Struktur beschrieben.</span><span class="sxs-lookup"><span data-stu-id="6100b-338">The [platyPS.schema.md][] document attempts to describe this structure.</span></span> <span data-ttu-id="6100b-339">Verstöße gegen das Schema führen zu Buildfehlern, die behoben werden müssen, bevor Ihr Beitrag akzeptiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="6100b-339">Schema violations cause build errors that must be fixed before we can accept your contribution.</span></span>

- <span data-ttu-id="6100b-340">Entfernen Sie keine der ATX-Header Strukturen.</span><span class="sxs-lookup"><span data-stu-id="6100b-340">Don't remove any of the ATX header structures.</span></span> <span data-ttu-id="6100b-341">PlatyPS erwartet spezifische Überschriften.</span><span class="sxs-lookup"><span data-stu-id="6100b-341">PlatyPS expects a specific set of headers.</span></span>
- <span data-ttu-id="6100b-342">Die Header **Input type** (Eingabetyp) und **Output type** (Ausgabetyp) müssen einen Typ aufweisen.</span><span class="sxs-lookup"><span data-stu-id="6100b-342">The **Input type** and **Output type** headers must have a type.</span></span> <span data-ttu-id="6100b-343">Wenn das Cmdlet keine Eingaben annimmt oder einen Wert zurückgibt, verwenden Sie den Wert `None` .</span><span class="sxs-lookup"><span data-stu-id="6100b-343">If the cmdlet doesn't take input or return a value, then use the value `None`.</span></span>
- <span data-ttu-id="6100b-344">Inlinecodespannen können in allen Absätzen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6100b-344">Inline code spans can be used in any paragraph.</span></span>
- <span data-ttu-id="6100b-345">Umgrenzte Code Blöcke sind nur im Abschnitt " **Beispiele** " zulässig.</span><span class="sxs-lookup"><span data-stu-id="6100b-345">Fenced code blocks are only allowed in the **EXAMPLES** section.</span></span>

<span data-ttu-id="6100b-346">Im platyps-Schema handelt es sich bei **Beispielen** um einen H2-Header.</span><span class="sxs-lookup"><span data-stu-id="6100b-346">In the PlatyPS schema, **EXAMPLES** is an H2 header.</span></span> <span data-ttu-id="6100b-347">Jedes Beispiel ist ein H3-Header.</span><span class="sxs-lookup"><span data-stu-id="6100b-347">Each example is an H3 header.</span></span> <span data-ttu-id="6100b-348">In einem Beispiel lässt das Schema nicht zu, dass Code Blöcke durch Absätze getrennt werden.</span><span class="sxs-lookup"><span data-stu-id="6100b-348">Within an example, the schema doesn't allow code blocks to be separated by paragraphs.</span></span> <span data-ttu-id="6100b-349">Das Schema ermöglicht die folgende Struktur:</span><span class="sxs-lookup"><span data-stu-id="6100b-349">The schema allows the following structure:</span></span>

```
### Example X - Title sentence

0 or more paragraphs
1 or more code blocks
0 or more paragraphs.
```

<span data-ttu-id="6100b-350">Geben Sie für alle Beispiele eine Zahl und einen kurzen Titel an.</span><span class="sxs-lookup"><span data-stu-id="6100b-350">Number each example and add a brief title.</span></span>

<span data-ttu-id="6100b-351">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="6100b-351">For example:</span></span>

~~~markdown
### Example 1: Get cmdlets, functions, and aliases

This command gets the PowerShell cmdlets, functions, and aliases that are installed on the
computer.

```powershell
Get-Command
```

### Example 2: Get commands in the current session

```powershell
Get-Command -ListImported
```
~~~

## <a name="formatting-about_-files"></a><span data-ttu-id="6100b-352">Formatieren von „About_“-Dateien</span><span class="sxs-lookup"><span data-stu-id="6100b-352">Formatting About_ files</span></span>

<span data-ttu-id="6100b-353">`About_*` Dateien werden in markdown geschrieben, aber als nur-Text-Dateien ausgeliefert.</span><span class="sxs-lookup"><span data-stu-id="6100b-353">`About_*` files are written in Markdown but are shipped as plain text files.</span></span> <span data-ttu-id="6100b-354">Sie verwenden [pandoc][] , um markdown in nur-Text zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="6100b-354">We use [Pandoc][] to convert the Markdown to plain text.</span></span> <span data-ttu-id="6100b-355">`About_*` Dateien werden für die beste Kompatibilität in allen Versionen von PowerShell und mit den Veröffentlichungs Tools formatiert.</span><span class="sxs-lookup"><span data-stu-id="6100b-355">`About_*` files are formatted for the best compatibility across all versions of PowerShell and with the publishing tools.</span></span>

<span data-ttu-id="6100b-356">Grundlegende Formatierungsrichtlinien:</span><span class="sxs-lookup"><span data-stu-id="6100b-356">Basic formatting guidelines:</span></span>

- <span data-ttu-id="6100b-357">Normale Zeilen auf 80 Zeichen begrenzen</span><span class="sxs-lookup"><span data-stu-id="6100b-357">Limit normal lines to 80 characters</span></span>
- <span data-ttu-id="6100b-358">Code Blöcke sind auf 76 Zeichen beschränkt.</span><span class="sxs-lookup"><span data-stu-id="6100b-358">Code blocks are limited to 76 characters</span></span>
- <span data-ttu-id="6100b-359">Bei blockanführungs Zeichen (und Warnungen) handelt es sich um 78 Zeichen.</span><span class="sxs-lookup"><span data-stu-id="6100b-359">Blockquotes (and Alerts) are limited 78 characters</span></span>
- <span data-ttu-id="6100b-360">Bei Verwendung dieser speziellen Meta-Zeichen `\` , `$` und `<` :</span><span class="sxs-lookup"><span data-stu-id="6100b-360">When using these special meta-characters `\`,`$`, and `<`:</span></span>
  - <span data-ttu-id="6100b-361">Innerhalb eines Headers müssen diese Zeichen mit Escapezeichen versehen werden, indem ein führendes `\` Zeichen verwendet oder in Code spannen mithilfe von Graviszeichen () eingeschlossen wird. `` ` ``</span><span class="sxs-lookup"><span data-stu-id="6100b-361">Within a header, these characters must be escaped using a leading `\` character or enclosed in code spans using backticks (`` ` ``)</span></span>
  - <span data-ttu-id="6100b-362">Innerhalb eines Absatzes sollten diese Zeichen in Code spannen eingefügt werden.</span><span class="sxs-lookup"><span data-stu-id="6100b-362">Within a paragraph, these characters should be put into code spans.</span></span> <span data-ttu-id="6100b-363">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="6100b-363">For example:</span></span>

    ~~~markdown
    ### The purpose of the \$foo variable

    The `$foo` variable is used to store ...
    ~~~

- <span data-ttu-id="6100b-364">Tabellen müssen in 76 Zeichen passen</span><span class="sxs-lookup"><span data-stu-id="6100b-364">Tables need to fit within 76 characters</span></span>
  - <span data-ttu-id="6100b-365">Umschließen Sie Inhalte von Zellen in mehreren Zeilen manuell.</span><span class="sxs-lookup"><span data-stu-id="6100b-365">Manually wrap contents of cells across multiple lines</span></span>
  - <span data-ttu-id="6100b-366">Verwenden Sie öffnende und schließende `|`-Zeichen in jeder Zeile.</span><span class="sxs-lookup"><span data-stu-id="6100b-366">Use opening and closing `|` characters on each line</span></span>
  - <span data-ttu-id="6100b-367">Im folgenden Beispiel wird veranschaulicht, wie eine Tabelle, die Informationen enthält, die in mehreren Zeilen innerhalb einer Zelle umschlossen werden, ordnungsgemäß erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="6100b-367">The following example illustrates how to properly construct a table that contains information that wraps on multiple lines within a cell.</span></span>

    ~~~markdown
    ```
    |Operator|Description                |Example                          |
    |--------|---------------------------|---------------------------------|
    |`-is`   |Returns TRUE when the input|`(get-date) -is [DateTime]`      |
    |        |is an instance of the      |`True`                           |
    |        |specified .NET type.       |                                 |
    |`-isNot`|Returns TRUE when the input|`(get-date) -isNot [DateTime]`   |
    |        |not an instance of the     |`False`                          |
    |        |specified.NET type.        |                                 |
    |`-as`   |Converts the input to the  |`"5/7/07" -as [DateTime]`        |
    |        |specified .NET type.       |`Monday, May 7, 2007 12:00:00 AM`|
    ```
    ~~~

    > [!NOTE]
    > <span data-ttu-id="6100b-368">Die Einschränkung der 76-Spalte gilt nur für `About_*` Themen.</span><span class="sxs-lookup"><span data-stu-id="6100b-368">The 76-column limitation applies only to `About_*` topics.</span></span> <span data-ttu-id="6100b-369">Sie können Breite Spalten in konzeptionellen oder Cmdlet-referenzartikeln verwenden.</span><span class="sxs-lookup"><span data-stu-id="6100b-369">You can use wide columns in conceptual or cmdlet reference articles.</span></span>

## <a name="next-steps"></a><span data-ttu-id="6100b-370">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="6100b-370">Next steps</span></span>

[<span data-ttu-id="6100b-371">Checkliste für Redakteure</span><span class="sxs-lookup"><span data-stu-id="6100b-371">Editorial checklist</span></span>](editorial-checklist.md)

<!-- link references -->
[atx]: https://github.github.com/gfm/#atx-headings
[CommonMark]: https://spec.commonmark.org/
[markdig]: https://github.com/lunet-io/markdig
[Pandoc]: https://pandoc.org
[Pascal-schreibgeschützte]: https://en.wikipedia.org/wiki/PascalCase
[Pascal-cased]: https://en.wikipedia.org/wiki/PascalCase
[platyPS.schema.md]: https://github.com/PowerShell/platyPS/blob/master/platyPS.schema.md
[PlatyPS]: https://github.com/powershell/platyps
[reflow]: https://marketplace.visualstudio.com/items?itemName=marvhen.reflow-markdown
[linkref]: https://spec.commonmark.org/0.29/#link-reference-definitions
