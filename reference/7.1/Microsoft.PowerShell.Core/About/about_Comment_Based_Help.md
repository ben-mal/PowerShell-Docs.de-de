---
description: Beschreibt, wie Kommentar basierte Hilfe Themen für Funktionen und Skripts geschrieben werden.
keywords: powershell,cmdlet
ms.date: 06/18/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_comment_based_help?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Comment_Based_Help
ms.openlocfilehash: 386ed8e1c28904c484261aa91d11ce028632cd16
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2020
ms.locfileid: "94391271"
---
# <a name="about-comment-based-help"></a><span data-ttu-id="13c62-104">Informationen zur Kommentar basierten Hilfe</span><span class="sxs-lookup"><span data-stu-id="13c62-104">About Comment-based Help</span></span>

## <a name="short-description"></a><span data-ttu-id="13c62-105">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="13c62-105">Short description</span></span>
<span data-ttu-id="13c62-106">Beschreibt, wie Kommentar basierte Hilfe Themen für Funktionen und Skripts geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="13c62-106">Describes how to write comment-based help topics for functions and scripts.</span></span>

## <a name="long-description"></a><span data-ttu-id="13c62-107">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="13c62-107">Long description</span></span>

<span data-ttu-id="13c62-108">Sie können Kommentar basierte Hilfe Themen für Funktionen und Skripts schreiben, indem Sie besondere Hilfe Kommentar Schlüsselwörter verwenden.</span><span class="sxs-lookup"><span data-stu-id="13c62-108">You can write comment-based help topics for functions and scripts by using special help comment keywords.</span></span>

<span data-ttu-id="13c62-109">Das Cmdlet " [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) " zeigt die Kommentar basierte Hilfe im gleichen Format an, in dem die Cmdlet-Hilfe Themen angezeigt werden, die aus XML-Dateien generiert werden.</span><span class="sxs-lookup"><span data-stu-id="13c62-109">The [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) cmdlet displays comment-based help in the same format in which it displays the cmdlet help topics that are generated from XML files.</span></span> <span data-ttu-id="13c62-110">Benutzer können alle Parameter von `Get-Help` , wie z. b. " **ausführlich** ", " **vollständig** ", " **Beispiele** " und " **Online** ", verwenden, um den Inhalt der Kommentar basierten Hilfe anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="13c62-110">Users can use all of the parameters of `Get-Help`, such as **Detailed** , **Full** , **Examples** , and **Online** , to display the contents of comment-based help.</span></span>

<span data-ttu-id="13c62-111">Sie können auch XML-basierte Hilfedateien für Funktionen und Skripts schreiben.</span><span class="sxs-lookup"><span data-stu-id="13c62-111">You can also write XML-based help files for functions and scripts.</span></span> <span data-ttu-id="13c62-112">`Get-Help`Verwenden Sie das-Schlüsselwort, um das Cmdlet für die Suche nach der XML-basierten Hilfedatei für eine Funktion oder ein Skript zu aktivieren `.ExternalHelp` .</span><span class="sxs-lookup"><span data-stu-id="13c62-112">To enable the `Get-Help` cmdlet to find the XML-based help file for a function or script, use the `.ExternalHelp` keyword.</span></span> <span data-ttu-id="13c62-113">Ohne dieses Schlüsselwort `Get-Help` können keine XML-basierten Hilfe Themen für Funktionen oder Skripts gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="13c62-113">Without this keyword, `Get-Help` cannot find XML-based help topics for functions or scripts.</span></span>

<span data-ttu-id="13c62-114">In diesem Thema wird erläutert, wie Sie Hilfe Themen für Funktionen und Skripts schreiben.</span><span class="sxs-lookup"><span data-stu-id="13c62-114">This topic explains how to write help topics for functions and scripts.</span></span> <span data-ttu-id="13c62-115">Weitere Informationen zum Anzeigen von Hilfe Themen für Funktionen und Skripts finden [Sie unter Get-Help](xref:Microsoft.PowerShell.Core.Get-Help).</span><span class="sxs-lookup"><span data-stu-id="13c62-115">For information about how to display help topics for functions and scripts, see [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help).</span></span>

<span data-ttu-id="13c62-116">Die Cmdlets " [Update-Help](xref:Microsoft.PowerShell.Core.Update-Help) " und " [Save-Help](xref:Microsoft.PowerShell.Core.Save-Help) " funktionieren nur in XML-Dateien.</span><span class="sxs-lookup"><span data-stu-id="13c62-116">The [Update-Help](xref:Microsoft.PowerShell.Core.Update-Help) and [Save-Help](xref:Microsoft.PowerShell.Core.Save-Help) cmdlets work only on XML files.</span></span> <span data-ttu-id="13c62-117">Die aktualisierbare Hilfe unterstützt keine Kommentar basierten Hilfe Themen.</span><span class="sxs-lookup"><span data-stu-id="13c62-117">Updatable Help does not support comment-based help topics.</span></span>

## <a name="syntax-for-comment-based-help"></a><span data-ttu-id="13c62-118">Syntax für die Kommentar basierte Hilfe</span><span class="sxs-lookup"><span data-stu-id="13c62-118">Syntax for comment-based help</span></span>

<span data-ttu-id="13c62-119">Die Syntax für die Kommentar basierte Hilfe lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="13c62-119">The syntax for comment-based help is as follows:</span></span>

```
# .<help keyword>
# <help content>
```

<span data-ttu-id="13c62-120">oder</span><span class="sxs-lookup"><span data-stu-id="13c62-120">or</span></span>

```
<#
.<help keyword>
<help content>
#>
```

<span data-ttu-id="13c62-121">Die Kommentar basierte Hilfe wird als eine Reihe von Kommentaren geschrieben.</span><span class="sxs-lookup"><span data-stu-id="13c62-121">Comment-based help is written as a series of comments.</span></span> <span data-ttu-id="13c62-122">Sie können `#` vor jeder Zeile von Kommentaren ein Kommentar Symbol eingeben, oder Sie können das-Symbol und das-Symbol verwenden, `<#` `#>` um einen Kommentar Block zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="13c62-122">You can type a comment symbol `#` before each line of comments, or you can use the `<#` and `#>` symbols to create a comment block.</span></span> <span data-ttu-id="13c62-123">Alle Zeilen innerhalb des Kommentar Blocks werden als Kommentare interpretiert.</span><span class="sxs-lookup"><span data-stu-id="13c62-123">All the lines within the comment block are interpreted as comments.</span></span>

<span data-ttu-id="13c62-124">Alle Zeilen in einem Kommentar basierten Hilfethema müssen zusammenhängend sein.</span><span class="sxs-lookup"><span data-stu-id="13c62-124">All of the lines in a comment-based help topic must be contiguous.</span></span> <span data-ttu-id="13c62-125">Wenn ein Kommentar basiertes Hilfethema einem Kommentar folgt, der nicht Teil des Hilfe Themas ist, muss mindestens eine Leerzeile zwischen der letzten nicht-Hilfe Kommentarzeile und dem Anfang der Kommentar basierten Hilfe vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="13c62-125">If a comment-based help topic follows a comment that is not part of the help topic, there must be at least one blank line between the last non-help comment line and the beginning of the comment-based help.</span></span>

<span data-ttu-id="13c62-126">Schlüsselwörter definieren jeden Abschnitt der Kommentar basierten Hilfe.</span><span class="sxs-lookup"><span data-stu-id="13c62-126">Keywords define each section of comment-based help.</span></span> <span data-ttu-id="13c62-127">Jedem Kommentar basierten Hilfe Schlüsselwort wird ein Punkt vorangestellt `.` .</span><span class="sxs-lookup"><span data-stu-id="13c62-127">Each comment-based help keyword is preceded by a dot `.`.</span></span> <span data-ttu-id="13c62-128">Die Schlüsselwörter können in beliebiger Reihenfolge angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="13c62-128">The keywords can appear in any order.</span></span> <span data-ttu-id="13c62-129">Beim Schlüsselwort Namen wird die Groß-/Kleinschreibung nicht beachtet.</span><span class="sxs-lookup"><span data-stu-id="13c62-129">The keyword names are not case-sensitive.</span></span>

<span data-ttu-id="13c62-130">Beispielsweise wird das- `.Description` Schlüsselwort vor einer Beschreibung einer Funktion oder eines Skripts vorangestellt.</span><span class="sxs-lookup"><span data-stu-id="13c62-130">For example, the `.Description` keyword precedes a description of a function or script.</span></span>

```
<#
.Description
Get-Function displays the name and syntax of all functions in the session.
#>
```

<span data-ttu-id="13c62-131">Der Kommentar Block muss mindestens ein Schlüsselwort enthalten.</span><span class="sxs-lookup"><span data-stu-id="13c62-131">The comment block must contain at least one keyword.</span></span> <span data-ttu-id="13c62-132">Einige der Schlüsselwörter, wie z `.EXAMPLE` . b., können oft im gleichen Kommentar Block vorkommen.</span><span class="sxs-lookup"><span data-stu-id="13c62-132">Some of the keywords, such as `.EXAMPLE`, can appear many times in the same comment block.</span></span> <span data-ttu-id="13c62-133">Der Hilfe Inhalt für jedes Schlüsselwort beginnt in der Zeile nach dem-Schlüsselwort und kann sich über mehrere Zeilen erstrecken.</span><span class="sxs-lookup"><span data-stu-id="13c62-133">The help content for each keyword begins on the line after the keyword and can span multiple lines.</span></span>

## <a name="syntax-for-comment-based-help-in-functions"></a><span data-ttu-id="13c62-134">Syntax für die Kommentar basierte Hilfe in Functions</span><span class="sxs-lookup"><span data-stu-id="13c62-134">Syntax for comment-based help in functions</span></span>

<span data-ttu-id="13c62-135">Die Kommentar basierte Hilfe für eine Funktion kann an einem von dreispeicher Orten angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="13c62-135">Comment-based help for a function can appear in one of three locations:</span></span>

- <span data-ttu-id="13c62-136">Am Anfang des Funktions Texts.</span><span class="sxs-lookup"><span data-stu-id="13c62-136">At the beginning of the function body.</span></span>
- <span data-ttu-id="13c62-137">Am Ende des Funktions Texts.</span><span class="sxs-lookup"><span data-stu-id="13c62-137">At the end of the function body.</span></span>
- <span data-ttu-id="13c62-138">Vor dem- `function` Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="13c62-138">Before the `function` keyword.</span></span> <span data-ttu-id="13c62-139">Zwischen der letzten Zeile der Funktions Hilfe und dem-Schlüsselwort darf nicht mehr als eine Leerzeile vorhanden sein `function` .</span><span class="sxs-lookup"><span data-stu-id="13c62-139">There cannot be more than one blank line between the last line of the function help and the `function` keyword.</span></span>

<span data-ttu-id="13c62-140">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="13c62-140">For example:</span></span>

```powershell
function Get-Function
{
<#
.<help keyword>
<help content>
#>

  # function logic
}
```

<span data-ttu-id="13c62-141">oder</span><span class="sxs-lookup"><span data-stu-id="13c62-141">or</span></span>

```powershell
function Get-Function
{
   # function logic

<#
.<help keyword>
<help content>
#>
}
```

<span data-ttu-id="13c62-142">oder</span><span class="sxs-lookup"><span data-stu-id="13c62-142">or</span></span>

```powershell
<#
.<help keyword>
<help content>
#>
function Get-Function { }
```

## <a name="syntax-for-comment-based-help-in-scripts"></a><span data-ttu-id="13c62-143">Syntax für die Kommentar basierte Hilfe in Skripts</span><span class="sxs-lookup"><span data-stu-id="13c62-143">Syntax for comment-based help in scripts</span></span>

<span data-ttu-id="13c62-144">Die Kommentar basierte Hilfe für ein Skript kann an einem der beiden folgenden Speicherorte im Skript angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="13c62-144">Comment-based help for a script can appear in one of the following two locations in the script.</span></span>

- <span data-ttu-id="13c62-145">Am Anfang der Skriptdatei.</span><span class="sxs-lookup"><span data-stu-id="13c62-145">At the beginning of the script file.</span></span> <span data-ttu-id="13c62-146">Der Skript Hilfe kann das Skript nur durch Kommentare und leere Zeilen vorangestellt werden.</span><span class="sxs-lookup"><span data-stu-id="13c62-146">Script help can be preceded in the script only by comments and blank lines.</span></span>

  <span data-ttu-id="13c62-147">Wenn das erste Element im Skript Text (nach der Hilfe) eine Funktionsdeklaration ist, müssen zwischen dem Ende der Skript Hilfe und der Funktionsdeklaration mindestens zwei Leerzeilen vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="13c62-147">If the first item in the script body (after the help) is a function declaration, there must be at least two blank lines between the end of the script help and the function declaration.</span></span> <span data-ttu-id="13c62-148">Andernfalls wird die Hilfe als Hilfe für die Funktion interpretiert, nicht als Hilfe für das Skript.</span><span class="sxs-lookup"><span data-stu-id="13c62-148">Otherwise, the help is interpreted as being help for the function, not help for the script.</span></span>

- <span data-ttu-id="13c62-149">Am Ende der Skriptdatei.</span><span class="sxs-lookup"><span data-stu-id="13c62-149">At the end of the script file.</span></span> <span data-ttu-id="13c62-150">Wenn das Skript jedoch signiert ist, platzieren Sie die Kommentar basierte Hilfe am Anfang der Skriptdatei.</span><span class="sxs-lookup"><span data-stu-id="13c62-150">However, if the script is signed, place Comment-based help at the beginning of the script file.</span></span> <span data-ttu-id="13c62-151">Das Ende des Skripts wird vom Signatur Block belegt.</span><span class="sxs-lookup"><span data-stu-id="13c62-151">The end of the script is occupied by the signature block.</span></span>

<span data-ttu-id="13c62-152">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="13c62-152">For example:</span></span>

```powershell
<#
.<help keyword>
<help content>
#>


function Get-Function { }
```

<span data-ttu-id="13c62-153">oder</span><span class="sxs-lookup"><span data-stu-id="13c62-153">or</span></span>

```powershell
function Get-Function { }

<#
.<help keyword>
<help content>
#>
```

## <a name="syntax-for-comment-based-help-in-script-modules"></a><span data-ttu-id="13c62-154">Syntax für die Kommentar basierte Hilfe in Skript Modulen</span><span class="sxs-lookup"><span data-stu-id="13c62-154">Syntax for comment-based help in script modules</span></span>

<span data-ttu-id="13c62-155">In einem Skript Modul `.psm1` verwendet die Kommentar basierte Hilfe die Syntax für Funktionen, nicht die Syntax für Skripts.</span><span class="sxs-lookup"><span data-stu-id="13c62-155">In a script module `.psm1`, comment-based help uses the syntax for functions, not the syntax for scripts.</span></span> <span data-ttu-id="13c62-156">Sie können die Skript Syntax nicht verwenden, um Hilfe für alle Funktionen bereitzustellen, die in einem Skript Modul definiert sind.</span><span class="sxs-lookup"><span data-stu-id="13c62-156">You cannot use the script syntax to provide help for all functions defined in a script module.</span></span>

<span data-ttu-id="13c62-157">Wenn Sie z. b. das `.ExternalHelp` -Schlüsselwort verwenden, um die XML-basierten Hilfedateien für die Funktionen in einem Skript Modul zu identifizieren, müssen Sie `.ExternalHelp` jeder Funktion einen Kommentar hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="13c62-157">For example, if you are using the `.ExternalHelp` keyword to identify the XML-based help files for the functions in a script module, you must add an `.ExternalHelp` comment to each function.</span></span>

```powershell
# .ExternalHelp <XML-file-name>
function <function-name>
{
  ...
}
```

## <a name="comment-based-help-keywords"></a><span data-ttu-id="13c62-158">Kommentar basierte Hilfe Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="13c62-158">Comment-based help keywords</span></span>

<span data-ttu-id="13c62-159">Im folgenden finden Sie gültige Kommentar basierte Hilfe Schlüsselwörter.</span><span class="sxs-lookup"><span data-stu-id="13c62-159">The following are valid comment-based help keywords.</span></span> <span data-ttu-id="13c62-160">Sie werden in der Reihenfolge aufgelistet, in der Sie in der Regel in einem Hilfethema zusammen mit der vorgesehenen Verwendung angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="13c62-160">They are listed in the order in which they typically appear in a help topic along with their intended use.</span></span> <span data-ttu-id="13c62-161">Diese Schlüsselwörter können in beliebiger Reihenfolge in der Kommentar basierten Hilfe angezeigt werden, und es wird nicht zwischen Groß-und Kleinschreibung unterschieden.</span><span class="sxs-lookup"><span data-stu-id="13c62-161">These keywords can appear in any order in the comment-based help, and they are not case-sensitive.</span></span>

### <a name="synopsis"></a><span data-ttu-id="13c62-162">. Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="13c62-162">.SYNOPSIS</span></span>

<span data-ttu-id="13c62-163">Eine kurze Beschreibung der Funktion oder des Skripts.</span><span class="sxs-lookup"><span data-stu-id="13c62-163">A brief description of the function or script.</span></span> <span data-ttu-id="13c62-164">Dieses Schlüsselwort kann nur einmal in jedem Thema verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="13c62-164">This keyword can be used only once in each topic.</span></span>

### <a name="description"></a><span data-ttu-id="13c62-165">. Beschreibung</span><span class="sxs-lookup"><span data-stu-id="13c62-165">.DESCRIPTION</span></span>

<span data-ttu-id="13c62-166">Eine ausführliche Beschreibung der Funktion oder des Skripts.</span><span class="sxs-lookup"><span data-stu-id="13c62-166">A detailed description of the function or script.</span></span> <span data-ttu-id="13c62-167">Dieses Schlüsselwort kann nur einmal in jedem Thema verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="13c62-167">This keyword can be used only once in each topic.</span></span>

### <a name="parameter"></a><span data-ttu-id="13c62-168">. Parame</span><span class="sxs-lookup"><span data-stu-id="13c62-168">.PARAMETER</span></span>

<span data-ttu-id="13c62-169">Die Beschreibung eines Parameters.</span><span class="sxs-lookup"><span data-stu-id="13c62-169">The description of a parameter.</span></span> <span data-ttu-id="13c62-170">Fügen Sie `.PARAMETER` für jeden Parameter in der Funktion oder Skript Syntax ein Schlüsselwort hinzu.</span><span class="sxs-lookup"><span data-stu-id="13c62-170">Add a `.PARAMETER` keyword for each parameter in the function or script syntax.</span></span>

<span data-ttu-id="13c62-171">Geben Sie den Parameternamen in derselben Zeile wie das `.PARAMETER` Schlüsselwort ein.</span><span class="sxs-lookup"><span data-stu-id="13c62-171">Type the parameter name on the same line as the `.PARAMETER` keyword.</span></span> <span data-ttu-id="13c62-172">Geben Sie die Parameter Beschreibung in den Zeilen nach dem `.PARAMETER` Schlüsselwort ein.</span><span class="sxs-lookup"><span data-stu-id="13c62-172">Type the parameter description on the lines following the `.PARAMETER` keyword.</span></span> <span data-ttu-id="13c62-173">Windows PowerShell interpretiert den gesamten Text zwischen der `.PARAMETER` Zeile und dem nächsten Schlüsselwort oder dem Ende des Kommentar Blocks als Teil der Parameter Beschreibung.</span><span class="sxs-lookup"><span data-stu-id="13c62-173">Windows PowerShell interprets all text between the `.PARAMETER` line and the next keyword or the end of the comment block as part of the parameter description.</span></span>
<span data-ttu-id="13c62-174">Die Beschreibung kann Absatz Umbrüche einschließen.</span><span class="sxs-lookup"><span data-stu-id="13c62-174">The description can include paragraph breaks.</span></span>

```
.PARAMETER  <Parameter-Name>
```

<span data-ttu-id="13c62-175">Die Parameter Schlüsselwörter können in beliebiger Reihenfolge im Kommentar Block angezeigt werden, aber die Funktion oder Skript Syntax bestimmt die Reihenfolge, in der die Parameter (und deren Beschreibungen) im Hilfethema angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="13c62-175">The Parameter keywords can appear in any order in the comment block, but the function or script syntax determines the order in which the parameters (and their descriptions) appear in help topic.</span></span> <span data-ttu-id="13c62-176">Ändern Sie die-Syntax, um die Reihenfolge zu ändern.</span><span class="sxs-lookup"><span data-stu-id="13c62-176">To change the order, change the syntax.</span></span>

<span data-ttu-id="13c62-177">Sie können auch eine Parameter Beschreibung angeben, indem Sie einen Kommentar in der Funktions-oder Skript Syntax direkt vor dem Variablennamen des Parameters platzieren.</span><span class="sxs-lookup"><span data-stu-id="13c62-177">You can also specify a parameter description by placing a comment in the function or script syntax immediately before the parameter variable name.</span></span> <span data-ttu-id="13c62-178">Damit dies funktioniert, müssen Sie auch über einen Kommentar Block mit mindestens einem Schlüsselwort verfügen.</span><span class="sxs-lookup"><span data-stu-id="13c62-178">For this to work, you must also have a comment block with at least one keyword.</span></span>

<span data-ttu-id="13c62-179">Wenn Sie sowohl einen Syntax Kommentar als auch ein `.PARAMETER` Schlüsselwort verwenden, wird die Beschreibung `.PARAMETER` verwendet, die dem Schlüsselwort zugeordnet ist, und der Syntax Kommentar wird ignoriert.</span><span class="sxs-lookup"><span data-stu-id="13c62-179">If you use both a syntax comment and a `.PARAMETER` keyword, the description associated with the `.PARAMETER` keyword is used, and the syntax comment is ignored.</span></span>

```powershell
<#
.SYNOPSIS
    Short description here
#>
function Verb-Noun {
    [CmdletBinding()]
    param (
        # This is the same as .Parameter
        [string]$Computername
    )
    # Verb the Noun on the computer
}
```

### <a name="example"></a><span data-ttu-id="13c62-180">. Beispiel</span><span class="sxs-lookup"><span data-stu-id="13c62-180">.EXAMPLE</span></span>

<span data-ttu-id="13c62-181">Ein Beispiel Befehl, der die Funktion oder das Skript verwendet, optional gefolgt von der Beispielausgabe und einer Beschreibung.</span><span class="sxs-lookup"><span data-stu-id="13c62-181">A sample command that uses the function or script, optionally followed by sample output and a description.</span></span> <span data-ttu-id="13c62-182">Wiederholen Sie dieses Schlüsselwort für jedes Beispiel.</span><span class="sxs-lookup"><span data-stu-id="13c62-182">Repeat this keyword for each example.</span></span>

### <a name="inputs"></a><span data-ttu-id="13c62-183">. Ungs</span><span class="sxs-lookup"><span data-stu-id="13c62-183">.INPUTS</span></span>

<span data-ttu-id="13c62-184">Die .NET-Typen von Objekten, die an die Funktion oder das Skript weitergeleitet werden können.</span><span class="sxs-lookup"><span data-stu-id="13c62-184">The .NET types of objects that can be piped to the function or script.</span></span> <span data-ttu-id="13c62-185">Sie können auch eine Beschreibung der Eingabe Objekte einschließen.</span><span class="sxs-lookup"><span data-stu-id="13c62-185">You can also include a description of the input objects.</span></span>

### <a name="outputs"></a><span data-ttu-id="13c62-186">. Ausgaben</span><span class="sxs-lookup"><span data-stu-id="13c62-186">.OUTPUTS</span></span>

<span data-ttu-id="13c62-187">Der .NET-Typ der Objekte, die vom Cmdlet zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="13c62-187">The .NET type of the objects that the cmdlet returns.</span></span> <span data-ttu-id="13c62-188">Sie können auch eine Beschreibung der zurückgegebenen Objekte einschließen.</span><span class="sxs-lookup"><span data-stu-id="13c62-188">You can also include a description of the returned objects.</span></span>

### <a name="notes"></a><span data-ttu-id="13c62-189">. Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="13c62-189">.NOTES</span></span>

<span data-ttu-id="13c62-190">Zusätzliche Informationen über die Funktion oder das Skript.</span><span class="sxs-lookup"><span data-stu-id="13c62-190">Additional information about the function or script.</span></span>

### <a name="link"></a><span data-ttu-id="13c62-191">. Verknüpfen</span><span class="sxs-lookup"><span data-stu-id="13c62-191">.LINK</span></span>

<span data-ttu-id="13c62-192">Der Name eines verwandten Themas.</span><span class="sxs-lookup"><span data-stu-id="13c62-192">The name of a related topic.</span></span> <span data-ttu-id="13c62-193">Der Wert wird in der Zeile unterhalb von angezeigt. Link "-Schlüsselwort und muss einem Kommentar Symbol vorangestellt sein, oder es muss `#` in den Kommentar Block eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="13c62-193">The value appears on the line below the ".LINK" keyword and must be preceded by a comment symbol `#` or included in the comment block.</span></span>

<span data-ttu-id="13c62-194">Wiederholen Sie das `.LINK` Schlüsselwort für jedes verwandte Thema.</span><span class="sxs-lookup"><span data-stu-id="13c62-194">Repeat the `.LINK` keyword for each related topic.</span></span>

<span data-ttu-id="13c62-195">Dieser Inhalt wird im Abschnitt Verwandte Links des Hilfe Themas angezeigt.</span><span class="sxs-lookup"><span data-stu-id="13c62-195">This content appears in the Related Links section of the help topic.</span></span>

<span data-ttu-id="13c62-196">Das `.Link` Schlüsselwort Content kann auch eine Uniform Resource Identifier (URI) zu einer Online Version desselben Hilfe Themas enthalten.</span><span class="sxs-lookup"><span data-stu-id="13c62-196">The `.Link` keyword content can also include a Uniform Resource Identifier (URI) to an online version of the same help topic.</span></span> <span data-ttu-id="13c62-197">Die Online Version wird geöffnet, wenn Sie den **Online-** Parameter von verwenden `Get-Help` .</span><span class="sxs-lookup"><span data-stu-id="13c62-197">The online version opens when you use the **Online** parameter of `Get-Help`.</span></span> <span data-ttu-id="13c62-198">Der URI muss mit "http" oder "https" beginnen.</span><span class="sxs-lookup"><span data-stu-id="13c62-198">The URI must begin with "http" or "https".</span></span>

### <a name="component"></a><span data-ttu-id="13c62-199">. Zulieferern</span><span class="sxs-lookup"><span data-stu-id="13c62-199">.COMPONENT</span></span>

<span data-ttu-id="13c62-200">Der Name der Technologie oder des Features, die bzw. das von der Funktion oder dem Skript verwendet wird bzw. mit dem Sie verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="13c62-200">The name of the technology or feature that the function or script uses, or to which it is related.</span></span> <span data-ttu-id="13c62-201">Der **Component** -Parameter von `Get-Help` verwendet diesen Wert, um die von zurückgegebenen Suchergebnisse zu filtern `Get-Help` .</span><span class="sxs-lookup"><span data-stu-id="13c62-201">The **Component** parameter of `Get-Help` uses this value to filter the search results returned by `Get-Help`.</span></span>

### <a name="role"></a><span data-ttu-id="13c62-202">. Spielen</span><span class="sxs-lookup"><span data-stu-id="13c62-202">.ROLE</span></span>

<span data-ttu-id="13c62-203">Der Name der Benutzerrolle für das Hilfethema.</span><span class="sxs-lookup"><span data-stu-id="13c62-203">The name of the user role for the help topic.</span></span> <span data-ttu-id="13c62-204">Der **Role** -Parameter von `Get-Help` verwendet diesen Wert, um die von zurückgegebenen Suchergebnisse zu filtern `Get-Help` .</span><span class="sxs-lookup"><span data-stu-id="13c62-204">The **Role** parameter of `Get-Help` uses this value to filter the search results returned by `Get-Help`.</span></span>

### <a name="functionality"></a><span data-ttu-id="13c62-205">. Alitäts</span><span class="sxs-lookup"><span data-stu-id="13c62-205">.FUNCTIONALITY</span></span>

<span data-ttu-id="13c62-206">Die Schlüsselwörter, die die beabsichtigte Verwendung der Funktion beschreiben.</span><span class="sxs-lookup"><span data-stu-id="13c62-206">The keywords that describe the intended use of the function.</span></span> <span data-ttu-id="13c62-207">Der- **Funktions** Parameter von `Get-Help` verwendet diesen Wert, um die von zurückgegebenen Suchergebnisse zu filtern `Get-Help` .</span><span class="sxs-lookup"><span data-stu-id="13c62-207">The **Functionality** parameter of `Get-Help` uses this value to filter the search results returned by `Get-Help`.</span></span>

### <a name="forwardhelptargetname"></a><span data-ttu-id="13c62-208">. Forwardhelptargetname</span><span class="sxs-lookup"><span data-stu-id="13c62-208">.FORWARDHELPTARGETNAME</span></span>

<span data-ttu-id="13c62-209">Leitet das Hilfethema für den angegebenen Befehl um.</span><span class="sxs-lookup"><span data-stu-id="13c62-209">Redirects to the help topic for the specified command.</span></span> <span data-ttu-id="13c62-210">Sie können Benutzer zu jedem beliebigen Hilfethema umleiten, einschließlich der Hilfe Themen für eine Funktion, ein Skript, ein Cmdlet oder einen Anbieter.</span><span class="sxs-lookup"><span data-stu-id="13c62-210">You can redirect users to any help topic, including help topics for a function, script, cmdlet, or provider.</span></span>

```powershell
# .FORWARDHELPTARGETNAME <Command-Name>
```

### <a name="forwardhelpcategory"></a><span data-ttu-id="13c62-211">. Forwardhelpcategory</span><span class="sxs-lookup"><span data-stu-id="13c62-211">.FORWARDHELPCATEGORY</span></span>

<span data-ttu-id="13c62-212">Gibt die Hilfe Kategorie des Elements in an `.ForwardHelpTargetName` .</span><span class="sxs-lookup"><span data-stu-id="13c62-212">Specifies the help category of the item in `.ForwardHelpTargetName`.</span></span> <span data-ttu-id="13c62-213">Gültige Werte sind `Alias` , `Cmdlet` , `HelpFile` , `Function` , `Provider` , `General` , `FAQ` , `Glossary` , `ScriptCommand` , `ExternalScript` , `Filter` oder `All` .</span><span class="sxs-lookup"><span data-stu-id="13c62-213">Valid values are `Alias`, `Cmdlet`, `HelpFile`, `Function`, `Provider`, `General`, `FAQ`, `Glossary`, `ScriptCommand`, `ExternalScript`, `Filter`, or `All`.</span></span> <span data-ttu-id="13c62-214">Verwenden Sie dieses Schlüsselwort, um Konflikte zu vermeiden, wenn Befehle mit demselben Namen vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="13c62-214">Use this keyword to avoid conflicts when there are commands with the same name.</span></span>

```powershell
# .FORWARDHELPCATEGORY <Category>
```

### <a name="remotehelprunspace"></a><span data-ttu-id="13c62-215">. Remotehelprunspace</span><span class="sxs-lookup"><span data-stu-id="13c62-215">.REMOTEHELPRUNSPACE</span></span>

<span data-ttu-id="13c62-216">Gibt eine Sitzung an, die das Hilfethema enthält.</span><span class="sxs-lookup"><span data-stu-id="13c62-216">Specifies a session that contains the help topic.</span></span> <span data-ttu-id="13c62-217">Geben Sie eine Variable ein, die ein **PSSession** -Objekt enthält.</span><span class="sxs-lookup"><span data-stu-id="13c62-217">Enter a variable that contains a **PSSession** object.</span></span> <span data-ttu-id="13c62-218">Dieses Schlüsselwort wird vom [Export-PSSession-](xref:Microsoft.PowerShell.Utility.Export-PSSession) Cmdlet verwendet, um die Hilfe Themen für die exportierten Befehle zu suchen.</span><span class="sxs-lookup"><span data-stu-id="13c62-218">This keyword is used by the [Export-PSSession](xref:Microsoft.PowerShell.Utility.Export-PSSession) cmdlet to find the help topics for the exported commands.</span></span>

```powershell
# .REMOTEHELPRUNSPACE <PSSession-variable>
```

### <a name="externalhelp"></a><span data-ttu-id="13c62-219">. Externalhelp "</span><span class="sxs-lookup"><span data-stu-id="13c62-219">.EXTERNALHELP</span></span>

<span data-ttu-id="13c62-220">Gibt eine XML-basierte Hilfedatei für das Skript oder die Funktion an.</span><span class="sxs-lookup"><span data-stu-id="13c62-220">Specifies an XML-based help file for the script or function.</span></span>

```powershell
# .EXTERNALHELP <XML Help File>
```

<span data-ttu-id="13c62-221">Das `.ExternalHelp` Schlüsselwort ist erforderlich, wenn eine Funktion oder ein Skript in XML-Dateien dokumentiert ist.</span><span class="sxs-lookup"><span data-stu-id="13c62-221">The `.ExternalHelp` keyword is required when a function or script is documented in XML files.</span></span> <span data-ttu-id="13c62-222">Ohne dieses Schlüsselwort `Get-Help` kann die XML-basierte Hilfedatei für die Funktion oder das Skript nicht finden.</span><span class="sxs-lookup"><span data-stu-id="13c62-222">Without this keyword, `Get-Help` cannot find the XML-based help file for the function or script.</span></span>

<span data-ttu-id="13c62-223">Das- `.ExternalHelp` Schlüsselwort hat Vorrang vor anderen Kommentar basierten Hilfe Schlüsselwörtern.</span><span class="sxs-lookup"><span data-stu-id="13c62-223">The `.ExternalHelp` keyword takes precedence over other comment-based help keywords.</span></span> <span data-ttu-id="13c62-224">Wenn `.ExternalHelp` vorhanden ist, wird von keine `Get-Help` Kommentar basierte Hilfe angezeigt, auch wenn kein Hilfethema gefunden werden kann, das mit dem Wert des `.ExternalHelp` Schlüssel Worts übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="13c62-224">If `.ExternalHelp` is present, `Get-Help` does not display comment-based help, even if it cannot find a help topic that matches the value of the `.ExternalHelp` keyword.</span></span>

<span data-ttu-id="13c62-225">Wenn die Funktion von einem Modul exportiert wird, legen Sie den Wert des- `.ExternalHelp` Schlüssel Worts auf einen Dateinamen ohne Pfad fest.</span><span class="sxs-lookup"><span data-stu-id="13c62-225">If the function is exported by a module, set the value of the `.ExternalHelp` keyword to a filename without a path.</span></span> <span data-ttu-id="13c62-226">`Get-Help` sucht nach dem angegebenen Dateinamen in einem sprachspezifischen Unterverzeichnis des Modul Verzeichnisses.</span><span class="sxs-lookup"><span data-stu-id="13c62-226">`Get-Help` looks for the specified file name in a language-specific subdirectory of the module directory.</span></span> <span data-ttu-id="13c62-227">Der Name der XML-basierten Hilfedatei für eine Funktion ist nicht erforderlich, aber es wird empfohlen, das folgende Format zu verwenden:</span><span class="sxs-lookup"><span data-stu-id="13c62-227">There are no requirements for the name of the XML-based help file for a function, but a best practice is to use the following format:</span></span>

```
<ScriptModule.psm1>-help.xml
```

<span data-ttu-id="13c62-228">Wenn die Funktion nicht in einem Modul enthalten ist, fügen Sie einen Pfad zur XML-basierten Hilfedatei ein.</span><span class="sxs-lookup"><span data-stu-id="13c62-228">If the function is not included in a module, include a path to the XML-based help file.</span></span> <span data-ttu-id="13c62-229">Wenn der Wert einen Pfad enthält und der Pfad Benutzeroberflächen kulturspezifische Unterverzeichnisse enthält, `Get-Help` durchsucht die Unterverzeichnisse rekursiv nach einer XML-Datei mit dem Namen des Skripts oder der Funktion in Übereinstimmung mit den für Windows eingerichteten sprach Fall Back Standards, ebenso wie in einem Modul Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="13c62-229">If the value includes a path and the path contains UI-culture-specific subdirectories, `Get-Help` searches the subdirectories recursively for an XML file with the name of the script or function in accordance with the language fallback standards established for Windows, just as it does in a module directory.</span></span>

<span data-ttu-id="13c62-230">Weitere Informationen zum XML-basierten Hilfedatei Format in der Cmdlet-Hilfe finden [Sie unter How to Write Cmdlet Help](/powershell/scripting/developer/help/writing-comment-based-help-topics).</span><span class="sxs-lookup"><span data-stu-id="13c62-230">For more information about the cmdlet help XML-based help file format, see [How to Write Cmdlet Help](/powershell/scripting/developer/help/writing-comment-based-help-topics).</span></span>

## <a name="autogenerated-content"></a><span data-ttu-id="13c62-231">Automatisch generierter Inhalt</span><span class="sxs-lookup"><span data-stu-id="13c62-231">Autogenerated content</span></span>

<span data-ttu-id="13c62-232">Der Name, die Syntax, die Parameterliste, die Parameter Attribut Tabelle, allgemeine Parameter und Hinweise werden vom `Get-Help` Cmdlet automatisch generiert.</span><span class="sxs-lookup"><span data-stu-id="13c62-232">The name, syntax, parameter list, parameter attribute table, common parameters, and remarks are automatically generated by the `Get-Help` cmdlet.</span></span>

### <a name="name"></a><span data-ttu-id="13c62-233">Name</span><span class="sxs-lookup"><span data-stu-id="13c62-233">Name</span></span>

<span data-ttu-id="13c62-234">Der **namens** Abschnitt eines Funktions Hilfe Themas wird aus dem Funktionsnamen in der Funktions Syntax entnommen.</span><span class="sxs-lookup"><span data-stu-id="13c62-234">The **Name** section of a function help topic is taken from the function name in the function syntax.</span></span> <span data-ttu-id="13c62-235">Der **Name** eines Skript Hilfe Themas wird aus dem Skript Dateiname entnommen.</span><span class="sxs-lookup"><span data-stu-id="13c62-235">The **Name** of a script help topic is taken from the script filename.</span></span> <span data-ttu-id="13c62-236">Um den Namen oder die Groß Schreibung zu ändern, ändern Sie die Funktions Syntax oder den Dateinamen des Skripts.</span><span class="sxs-lookup"><span data-stu-id="13c62-236">To change the name or its capitalization, change the function syntax or the script filename.</span></span>

### <a name="syntax"></a><span data-ttu-id="13c62-237">Syntax</span><span class="sxs-lookup"><span data-stu-id="13c62-237">Syntax</span></span>

<span data-ttu-id="13c62-238">Der Abschnitt **Syntax** des Hilfe Themas wird aus der Funktion oder der Skript Syntax generiert.</span><span class="sxs-lookup"><span data-stu-id="13c62-238">The **Syntax** section of the help topic is generated from the function or script syntax.</span></span> <span data-ttu-id="13c62-239">Um der Hilfe Themen Syntax Details hinzuzufügen, z. b. den .NET-Typ eines Parameters, fügen Sie der Syntax das Detail hinzu.</span><span class="sxs-lookup"><span data-stu-id="13c62-239">To add detail to the help topic syntax, such as the .NET type of a parameter, add the detail to the syntax.</span></span> <span data-ttu-id="13c62-240">Wenn Sie keinen Parametertyp angeben, wird der **Objekttyp** als Standardwert eingefügt.</span><span class="sxs-lookup"><span data-stu-id="13c62-240">If you do not specify a parameter type, the **Object** type is inserted as the default value.</span></span>

### <a name="parameter-list"></a><span data-ttu-id="13c62-241">Parameterliste</span><span class="sxs-lookup"><span data-stu-id="13c62-241">Parameter List</span></span>

<span data-ttu-id="13c62-242">Die Parameterliste im Hilfethema wird aus der Funktions-oder Skript Syntax und aus den Beschreibungen generiert, die Sie mit dem- `.Parameter` Schlüsselwort hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="13c62-242">The parameter list in the help topic is generated from the function or script syntax and from the descriptions that you add by using the `.Parameter` keyword.</span></span> <span data-ttu-id="13c62-243">Die Funktionsparameter werden im **Parameter** Abschnitt des Hilfe Themas in derselben Reihenfolge angezeigt, in der Sie in der Funktion oder Skript Syntax angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="13c62-243">The function parameters appear in the **Parameters** section of the help topic in the same order that they appear in the function or script syntax.</span></span> <span data-ttu-id="13c62-244">Die Schreibweise und die Groß-/Kleinschreibung von Parameternamen werden auch aus der Syntax entnommen.</span><span class="sxs-lookup"><span data-stu-id="13c62-244">The spelling and capitalization of parameter names is also taken from the syntax.</span></span> <span data-ttu-id="13c62-245">Der durch das-Schlüsselwort angegebene Parameter Name ist nicht betroffen `.Parameter` .</span><span class="sxs-lookup"><span data-stu-id="13c62-245">It is not affected by the parameter name specified by the `.Parameter` keyword.</span></span>

### <a name="common-parameters"></a><span data-ttu-id="13c62-246">Allgemeine Parameter</span><span class="sxs-lookup"><span data-stu-id="13c62-246">Common Parameters</span></span>

<span data-ttu-id="13c62-247">Die **allgemeinen Parameter** werden der Syntax und der Parameterliste des Hilfe Themas hinzugefügt, auch wenn Sie keine Auswirkung haben.</span><span class="sxs-lookup"><span data-stu-id="13c62-247">The **Common parameters** are added to the syntax and parameter list of the help topic, even if they have no effect.</span></span> <span data-ttu-id="13c62-248">Weitere Informationen zu den allgemeinen Parametern finden Sie unter [about_CommonParameters](about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="13c62-248">For more information about the common parameters, see [about_CommonParameters](about_CommonParameters.md).</span></span>

### <a name="parameter-attribute-table"></a><span data-ttu-id="13c62-249">Parameter Attribut Tabelle</span><span class="sxs-lookup"><span data-stu-id="13c62-249">Parameter Attribute Table</span></span>

<span data-ttu-id="13c62-250">`Get-Help` generiert die Tabelle mit Parameter Attributen, die angezeigt wird, wenn Sie den **Full** -Parameter oder **Parameter** -Parameter von verwenden `Get-Help` .</span><span class="sxs-lookup"><span data-stu-id="13c62-250">`Get-Help` generates the table of parameter attributes that appears when you use the **Full** or **Parameter** parameter of `Get-Help`.</span></span> <span data-ttu-id="13c62-251">Der Wert der Attribute **Required** , **Position** und **default** value wird aus der Funktion oder der Skript Syntax entnommen.</span><span class="sxs-lookup"><span data-stu-id="13c62-251">The value of the **Required** , **Position** , and **Default** value attributes is taken from the function or script syntax.</span></span>

<span data-ttu-id="13c62-252">Standardwerte und ein Wert für Platzhalter **Zeichen annehmen** werden nicht in der Parameter-Attribut Tabelle angezeigt, auch wenn Sie in der Funktion oder im Skript definiert sind.</span><span class="sxs-lookup"><span data-stu-id="13c62-252">Default values and a value for **Accept Wildcard characters** do not appear in the parameter attribute table even when they are defined in the function or script.</span></span> <span data-ttu-id="13c62-253">Um Benutzer zu unterstützen, geben Sie diese Informationen in der Parameter Beschreibung an.</span><span class="sxs-lookup"><span data-stu-id="13c62-253">To help users, provide this information in the parameter description.</span></span>

### <a name="remarks"></a><span data-ttu-id="13c62-254">Hinweise</span><span class="sxs-lookup"><span data-stu-id="13c62-254">Remarks</span></span>

<span data-ttu-id="13c62-255">Der Abschnitt " **Hinweise** " des Hilfe Themas wird automatisch aus dem Namen der Funktion oder des Skripts generiert.</span><span class="sxs-lookup"><span data-stu-id="13c62-255">The **Remarks** section of the help topic is automatically generated from the function or script name.</span></span> <span data-ttu-id="13c62-256">Der Inhalt kann nicht geändert oder beeinflusst werden.</span><span class="sxs-lookup"><span data-stu-id="13c62-256">You cannot change or affect its content.</span></span>

## <a name="examples"></a><span data-ttu-id="13c62-257">Beispiele</span><span class="sxs-lookup"><span data-stu-id="13c62-257">Examples</span></span>

### <a name="comment-based-help-for-a-function"></a><span data-ttu-id="13c62-258">Kommentar basierte Hilfe für eine Funktion</span><span class="sxs-lookup"><span data-stu-id="13c62-258">Comment-based Help for a Function</span></span>

<span data-ttu-id="13c62-259">Die folgende Beispiel Funktion enthält eine Kommentar basierte Hilfe:</span><span class="sxs-lookup"><span data-stu-id="13c62-259">The following sample function includes comment-based help:</span></span>

```powershell
function Add-Extension
{
param ([string]$Name,[string]$Extension = "txt")
$name = $name + "." + $extension
$name

<#
.SYNOPSIS

Adds a file name extension to a supplied name.

.DESCRIPTION

Adds a file name extension to a supplied name.
Takes any strings for the file name or extension.

.PARAMETER Name
Specifies the file name.

.PARAMETER Extension
Specifies the extension. "Txt" is the default.

.INPUTS

None. You cannot pipe objects to Add-Extension.

.OUTPUTS

System.String. Add-Extension returns a string with the extension
or file name.

.EXAMPLE

PS> extension -name "File"
File.txt

.EXAMPLE

PS> extension -name "File" -extension "doc"
File.doc

.EXAMPLE

PS> extension "File" "doc"
File.doc

.LINK

http://www.fabrikam.com/extension.html

.LINK

Set-Item
#>
}
```

<span data-ttu-id="13c62-260">Die Ergebnisse lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="13c62-260">The results are as follows:</span></span>

```powershell
Get-Help -Name "Add-Extension" -Full
```

```Output
NAME

Add-Extension

SYNOPSIS

Adds a file name extension to a supplied name.

SYNTAX

Add-Extension [[-Name] <String>] [[-Extension] <String>]
[<CommonParameters>]

DESCRIPTION

Adds a file name extension to a supplied name. Takes any strings for the
file name or extension.

PARAMETERS

-Name
Specifies the file name.

Required?                    false
Position?                    0
Default value
Accept pipeline input?       false
Accept wildcard characters?

-Extension
Specifies the extension. "Txt" is the default.

Required?                    false
Position?                    1
Default value
Accept pipeline input?       false
Accept wildcard characters?

<CommonParameters>
This cmdlet supports the common parameters: -Verbose, -Debug,
-ErrorAction, -ErrorVariable, -WarningAction, -WarningVariable,
-OutBuffer and -OutVariable. For more information, type
"get-help about_commonparameters".

INPUTS
None. You cannot pipe objects to Add-Extension.

OUTPUTS

System.String. Add-Extension returns a string with the extension or
file name.

Example 1

PS> extension -name "File"
File.txt

Example 2

PS> extension -name "File" -extension "doc"
File.doc

Example 3

PS> extension "File" "doc"
File.doc

RELATED LINKS

http://www.fabrikam.com/extension.html
Set-Item
```

### <a name="parameter-descriptions-in-function-syntax"></a><span data-ttu-id="13c62-261">Parameter Beschreibungen in der Funktions Syntax</span><span class="sxs-lookup"><span data-stu-id="13c62-261">Parameter Descriptions in Function Syntax</span></span>

<span data-ttu-id="13c62-262">Dieses Beispiel ist mit dem vorherigen identisch, mit dem Unterschied, dass die Parameter Beschreibungen in die Funktions Syntax eingefügt werden.</span><span class="sxs-lookup"><span data-stu-id="13c62-262">This example is the same as the previous one, except that the parameter descriptions are inserted in the function syntax.</span></span> <span data-ttu-id="13c62-263">Dieses Format ist besonders nützlich, wenn die Beschreibungen kurz sind.</span><span class="sxs-lookup"><span data-stu-id="13c62-263">This format is most useful when the descriptions are brief.</span></span>

```powershell
function Add-Extension
{
param
(

[string]
#Specifies the file name.
$name,

[string]
#Specifies the file name extension. "Txt" is the default.
$extension = "txt"
)

$name = $name + "." + $extension
$name

<#
.SYNOPSIS

Adds a file name extension to a supplied name.

.DESCRIPTION

Adds a file name extension to a supplied name. Takes any strings for the
file name or extension.

.INPUTS

None. You cannot pipe objects to Add-Extension.

.OUTPUTS

System.String. Add-Extension returns a string with the extension or
file name.

.EXAMPLE

PS> extension -name "File"
File.txt

.EXAMPLE

PS> extension -name "File" -extension "doc"
File.doc

.EXAMPLE

PS> extension "File" "doc"
File.doc

.LINK

http://www.fabrikam.com/extension.html

.LINK

Set-Item
#>
}
```

### <a name="comment-based-help-for-a-script"></a><span data-ttu-id="13c62-264">Kommentar basierte Hilfe für ein Skript</span><span class="sxs-lookup"><span data-stu-id="13c62-264">Comment-based Help for a Script</span></span>

<span data-ttu-id="13c62-265">Das folgende Beispielskript enthält eine Kommentar basierte Hilfe.</span><span class="sxs-lookup"><span data-stu-id="13c62-265">The following sample script includes comment-based help.</span></span> <span data-ttu-id="13c62-266">Beachten Sie die leeren Zeilen zwischen dem schließenden `#>` und der- `Param` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="13c62-266">Notice the blank lines between the closing `#>` and the `Param` statement.</span></span> <span data-ttu-id="13c62-267">In einem Skript, das keine `Param` -Anweisung enthält, müssen mindestens zwei Leerzeilen zwischen dem letzten Kommentar im Hilfethema und der ersten Funktionsdeklaration vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="13c62-267">In a script that does not have a `Param` statement, there must be at least two blank lines between the final comment in the help topic and the first function declaration.</span></span> <span data-ttu-id="13c62-268">Ohne diese leeren Zeilen ordnet das `Get-Help` Hilfethema der Funktion zu, nicht dem Skript.</span><span class="sxs-lookup"><span data-stu-id="13c62-268">Without these blank lines, `Get-Help` associates the help topic with the function, not the script.</span></span>

```powershell
<#
.SYNOPSIS

Performs monthly data updates.

.DESCRIPTION

The Update-Month.ps1 script updates the registry with new data generated
during the past month and generates a report.

.PARAMETER InputPath
Specifies the path to the CSV-based input file.

.PARAMETER OutputPath
Specifies the name and path for the CSV-based output file. By default,
MonthlyUpdates.ps1 generates a name from the date and time it runs, and
saves the output in the local directory.

.INPUTS

None. You cannot pipe objects to Update-Month.ps1.

.OUTPUTS

None. Update-Month.ps1 does not generate any output.

.EXAMPLE

PS> .\Update-Month.ps1

.EXAMPLE

PS> .\Update-Month.ps1 -inputpath C:\Data\January.csv

.EXAMPLE

PS> .\Update-Month.ps1 -inputpath C:\Data\January.csv -outputPath `
C:\Reports\2009\January.csv
#>

param ([string]$InputPath, [string]$OutPutPath)

function Get-Data { }
...
```

<span data-ttu-id="13c62-269">Der folgende Befehl ruft die Skript Hilfe ab.</span><span class="sxs-lookup"><span data-stu-id="13c62-269">The following command gets the script help.</span></span> <span data-ttu-id="13c62-270">Da sich das Skript nicht in einem Verzeichnis befindet, das in der `$env:Path` Umgebungsvariablen aufgelistet ist, `Get-Help` muss der Befehl, mit dem die Skript Hilfe abgerufen wird, den Skript Pfad angeben.</span><span class="sxs-lookup"><span data-stu-id="13c62-270">Because the script is not in a directory that is listed in the `$env:Path` environment variable, the `Get-Help` command that gets the script help must specify the script path.</span></span>

```powershell
Get-Help -Path .\update-month.ps1 -Full
```

```Output
# NAME

C:\ps-test\Update-Month.ps1

# SYNOPSIS

Performs monthly data updates.

# SYNTAX

C:\ps-test\Update-Month.ps1 [-InputPath] <String> [[-OutputPath]
<String>] [<CommonParameters>]

# DESCRIPTION

The Update-Month.ps1 script updates the registry with new data
generated during the past month and generates a report.

# PARAMETERS

-InputPath
Specifies the path to the CSV-based input file.

Required?                    true
Position?                    0
Default value
Accept pipeline input?       false
Accept wildcard characters?

-OutputPath
Specifies the name and path for the CSV-based output file. By
default, MonthlyUpdates.ps1 generates a name from the date
and time it runs, and saves the output in the local directory.

Required?                    false
Position?                    1
Default value
Accept pipeline input?       false
Accept wildcard characters?

<CommonParameters>
This cmdlet supports the common parameters: -Verbose, -Debug,
-ErrorAction, -ErrorVariable, -WarningAction, -WarningVariable,
-OutBuffer and -OutVariable. For more information, type,
"get-help about_commonparameters".

# INPUTS

None. You cannot pipe objects to Update-Month.ps1.

# OUTPUTS

None. Update-Month.ps1 does not generate any output.

Example 1

PS> .\Update-Month.ps1

Example 2

PS> .\Update-Month.ps1 -inputpath C:\Data\January.csv

Example 3

PS> .\Update-Month.ps1 -inputpath C:\Data\January.csv -outputPath
C:\Reports\2009\January.csv

# RELATED LINKS
```

### <a name="redirecting-to-an-xml-file"></a><span data-ttu-id="13c62-271">Umleiten an eine XML-Datei</span><span class="sxs-lookup"><span data-stu-id="13c62-271">Redirecting to an XML File</span></span>

<span data-ttu-id="13c62-272">Sie können XML-basierte Hilfe Themen für Funktionen und Skripts schreiben.</span><span class="sxs-lookup"><span data-stu-id="13c62-272">You can write XML-based help topics for functions and scripts.</span></span> <span data-ttu-id="13c62-273">Obwohl die Kommentar basierte Hilfe einfacher implementiert werden kann, ist die XML-basierte Hilfe für die aktualisierbare Hilfe und die Bereitstellung von Hilfe Themen in mehreren Sprachen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="13c62-273">Although comment-based help is easier to implement, XML-based help is required for Updatable Help and to provide help topics in multiple languages.</span></span>

<span data-ttu-id="13c62-274">Das folgende Beispiel zeigt die ersten Zeilen des Update-Month.ps1 Skripts.</span><span class="sxs-lookup"><span data-stu-id="13c62-274">The following example shows the first few lines of the Update-Month.ps1 script.</span></span>
<span data-ttu-id="13c62-275">Das Skript verwendet das- `.ExternalHelp` Schlüsselwort, um den Pfad zu einem XML-basierten Hilfethema für das Skript anzugeben.</span><span class="sxs-lookup"><span data-stu-id="13c62-275">The script uses the `.ExternalHelp` keyword to specify the path to an XML-based help topic for the script.</span></span>

<span data-ttu-id="13c62-276">Beachten Sie, dass der Wert des- `.ExternalHelp` Schlüssel Worts in derselben Zeile wie das-Schlüsselwort angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="13c62-276">Note that the value of the `.ExternalHelp` keyword appears on the same line as the keyword.</span></span> <span data-ttu-id="13c62-277">Jede andere Platzierung ist wirkungslos.</span><span class="sxs-lookup"><span data-stu-id="13c62-277">Any other placement is ineffective.</span></span>

```powershell
# .ExternalHelp C:\MyScripts\Update-Month-Help.xml

param ([string]$InputPath, [string]$OutPutPath)
function Get-Data { }
...
```

<span data-ttu-id="13c62-278">In den folgenden Beispielen werden drei gültige Platzierungs Werte des- `.ExternalHelp` Schlüssel Worts in einer-Funktion gezeigt.</span><span class="sxs-lookup"><span data-stu-id="13c62-278">The following examples show three valid placements of the `.ExternalHelp` keyword in a function.</span></span>

```powershell
function Add-Extension
{
# .ExternalHelp C:\ps-test\Add-Extension.xml

param ([string] $name, [string]$extension = "txt")
$name = $name + "." + $extension
$name
}
```

```powershell
function Add-Extension
{
param ([string] $name, [string]$extension = "txt")
$name = $name + "." + $extension
$name

# .ExternalHelp C:\ps-test\Add-Extension.xml
}
```

```powershell
# .ExternalHelp C:\ps-test\Add-Extension.xml
function Add-Extension
{
param ([string] $name, [string]$extension = "txt")
$name = $name + "." + $extension
$name
}
```

### <a name="redirecting-to-a-different-help-topic"></a><span data-ttu-id="13c62-279">Umleiten an ein anderes Hilfethema</span><span class="sxs-lookup"><span data-stu-id="13c62-279">Redirecting to a Different Help Topic</span></span>

<span data-ttu-id="13c62-280">Der folgende Code ist ein Auszug aus dem Anfang der integrierten Hilfe Funktion in PowerShell, die jeweils einen Bildschirm von Hilfe Text anzeigt.</span><span class="sxs-lookup"><span data-stu-id="13c62-280">The following code is an excerpt from the beginning of the built-in help function in PowerShell, which displays one screen of help text at a time.</span></span>
<span data-ttu-id="13c62-281">Da im Hilfethema für das `Get-Help` Cmdlet die Hilfe Funktion beschrieben wird, verwendet die Hilfe Funktion `.ForwardHelpTargetName` die `.ForwardHelpCategory` Schlüsselwörter und, um den Benutzer zum `Get-Help` Cmdlet-Hilfethema umzuleiten.</span><span class="sxs-lookup"><span data-stu-id="13c62-281">Because the help topic for the `Get-Help` cmdlet describes the help function, the help function uses the `.ForwardHelpTargetName` and `.ForwardHelpCategory` keywords to redirect the user to the `Get-Help` cmdlet help topic.</span></span>

```powershell
function help
{

<#
.FORWARDHELPTARGETNAME Get-Help
.FORWARDHELPCATEGORY Cmdlet
#>
[CmdletBinding(DefaultParameterSetName='AllUsersView')]
param(
[Parameter(Position=0, ValueFromPipelineByPropertyName=$true)]
[System.String]
${Name},
...
```

<span data-ttu-id="13c62-282">Der folgende Befehl verwendet dieses Feature:</span><span class="sxs-lookup"><span data-stu-id="13c62-282">The following command uses this feature:</span></span>

```powershell
Get-Help -Name help
```

```Output
NAME

Get-Help

SYNOPSIS

Displays information about PowerShell cmdlets and concepts.
...
```

## <a name="see-also"></a><span data-ttu-id="13c62-283">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="13c62-283">See also</span></span>

[<span data-ttu-id="13c62-284">about_Functions</span><span class="sxs-lookup"><span data-stu-id="13c62-284">about_Functions</span></span>](about_Functions.md)

[<span data-ttu-id="13c62-285">about_Functions_Advanced_Parameters</span><span class="sxs-lookup"><span data-stu-id="13c62-285">about_Functions_Advanced_Parameters</span></span>](about_Functions_Advanced_Parameters.md)

[<span data-ttu-id="13c62-286">about_Scripts</span><span class="sxs-lookup"><span data-stu-id="13c62-286">about_Scripts</span></span>](about_Scripts.md)

[<span data-ttu-id="13c62-287">Vorgehensweise beim Schreiben von Cmdlet-Hilfe</span><span class="sxs-lookup"><span data-stu-id="13c62-287">How to Write Cmdlet Help</span></span>](https://go.microsoft.com/fwlink/?LinkID=123415)
