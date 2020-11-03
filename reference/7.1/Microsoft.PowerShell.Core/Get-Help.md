---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 09/03/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-help?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Help
ms.openlocfilehash: 1a4a3f7050c3da2a73ae0d5319938117284076b7
ms.sourcegitcommit: 05f578d3fca0d9663bb1e4f76e2f14604f5303ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2020
ms.locfileid: "93219847"
---
# <span data-ttu-id="b5c68-103">Get-Help</span><span class="sxs-lookup"><span data-stu-id="b5c68-103">Get-Help</span></span>

## <span data-ttu-id="b5c68-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="b5c68-104">SYNOPSIS</span></span>
<span data-ttu-id="b5c68-105">Zeigt Informationen zu PowerShell-Befehlen und-Konzepten an.</span><span class="sxs-lookup"><span data-stu-id="b5c68-105">Displays information about PowerShell commands and concepts.</span></span>

## <span data-ttu-id="b5c68-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b5c68-106">SYNTAX</span></span>

### <span data-ttu-id="b5c68-107">Allusersview (Standard)</span><span class="sxs-lookup"><span data-stu-id="b5c68-107">AllUsersView (Default)</span></span>

```
Get-Help [[-Name] <String>] [-Path <String>] [-Category <String[]>] [-Full] [-Component <String[]>]
 [-Functionality <String[]>] [-Role <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="b5c68-108">Detailedview</span><span class="sxs-lookup"><span data-stu-id="b5c68-108">DetailedView</span></span>

```
Get-Help [[-Name] <String>] [-Path <String>] [-Category <String[]>] -Detailed
 [-Component <String[]>] [-Functionality <String[]>] [-Role <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="b5c68-109">Beispiele</span><span class="sxs-lookup"><span data-stu-id="b5c68-109">Examples</span></span>

```
Get-Help [[-Name] <String>] [-Path <String>] [-Category <String[]>] -Examples
 [-Component <String[]>] [-Functionality <String[]>] [-Role <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="b5c68-110">Parameter</span><span class="sxs-lookup"><span data-stu-id="b5c68-110">Parameters</span></span>

```
Get-Help [[-Name] <String>] [-Path <String>] [-Category <String[]>] -Parameter <String[]>
 [-Component <String[]>] [-Functionality <String[]>] [-Role <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="b5c68-111">Online</span><span class="sxs-lookup"><span data-stu-id="b5c68-111">Online</span></span>

```
Get-Help [[-Name] <String>] [-Path <String>] [-Category <String[]>] [-Component <String[]>]
 [-Functionality <String[]>] [-Role <String[]>] -Online [<CommonParameters>]
```

### <span data-ttu-id="b5c68-112">ShowWindow</span><span class="sxs-lookup"><span data-stu-id="b5c68-112">ShowWindow</span></span>

```
Get-Help [[-Name] <String>] [-Path <String>] [-Category <String[]>] [-Component <String[]>]
 [-Functionality <String[]>] [-Role <String[]>] -ShowWindow [<CommonParameters>]
```

## <span data-ttu-id="b5c68-113">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b5c68-113">DESCRIPTION</span></span>

<span data-ttu-id="b5c68-114">Das `Get-Help` -Cmdlet zeigt Informationen zu PowerShell-Konzepten und-Befehlen an, einschließlich Cmdlets, Funktionen, Common Information Model (CIM)-Befehlen, Workflows, Anbietern, Aliase und Skripts.</span><span class="sxs-lookup"><span data-stu-id="b5c68-114">The `Get-Help` cmdlet displays information about PowerShell concepts and commands, including cmdlets, functions, Common Information Model (CIM) commands, workflows, providers, aliases, and scripts.</span></span>

<span data-ttu-id="b5c68-115">Um Hilfe zu einem PowerShell-Cmdlet zu erhalten, geben Sie `Get-Help` gefolgt vom Namen des Cmdlets ein, z `Get-Help Get-Process` . b.:.</span><span class="sxs-lookup"><span data-stu-id="b5c68-115">To get help for a PowerShell cmdlet, type `Get-Help` followed by the cmdlet name, such as: `Get-Help Get-Process`.</span></span>

<span data-ttu-id="b5c68-116">Konzeptionelle Hilfeartikel in PowerShell beginnen mit **About_** , z. b. **about_Comparison_Operators**.</span><span class="sxs-lookup"><span data-stu-id="b5c68-116">Conceptual help articles in PowerShell begin with **about_** , such as **about_Comparison_Operators**.</span></span> <span data-ttu-id="b5c68-117">Wenn Sie alle **About_** Artikel anzeigen möchten, geben Sie ein `Get-Help about_*` .</span><span class="sxs-lookup"><span data-stu-id="b5c68-117">To see all **about_** articles, type `Get-Help about_*`.</span></span> <span data-ttu-id="b5c68-118">Um einen bestimmten Artikel anzuzeigen, geben Sie ein `Get-Help about_<article-name>` , z `Get-Help about_Comparison_Operators` . b..</span><span class="sxs-lookup"><span data-stu-id="b5c68-118">To see a particular article, type `Get-Help about_<article-name>`, such as `Get-Help about_Comparison_Operators`.</span></span>

<span data-ttu-id="b5c68-119">Um Hilfe zu einem PowerShell-Anbieter zu erhalten, geben Sie `Get-Help` gefolgt vom Anbieter Namen ein.</span><span class="sxs-lookup"><span data-stu-id="b5c68-119">To get help for a PowerShell provider, type `Get-Help` followed by the provider name.</span></span> <span data-ttu-id="b5c68-120">Wenn Sie z. b. Hilfe zum Zertifikat Anbieter benötigen, geben Sie ein `Get-Help Certificate` .</span><span class="sxs-lookup"><span data-stu-id="b5c68-120">For example, to get help for the Certificate provider, type `Get-Help Certificate`.</span></span>

<span data-ttu-id="b5c68-121">Sie können auch `help` oder eingeben `man` , das jeweils jeweils einen Bildschirm anzeigt.</span><span class="sxs-lookup"><span data-stu-id="b5c68-121">You can also type `help` or `man`, which displays one screen of text at a time.</span></span> <span data-ttu-id="b5c68-122">Oder, `<cmdlet-name> -?` das ist mit identisch `Get-Help` , funktioniert aber nur für Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="b5c68-122">Or, `<cmdlet-name> -?`, that is identical to `Get-Help`, but only works for cmdlets.</span></span>

<span data-ttu-id="b5c68-123">`Get-Help` Ruft den Hilfe Inhalt ab, der von Hilfedateien auf Ihrem Computer angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="b5c68-123">`Get-Help` gets the help content that it displays from help files on your computer.</span></span> <span data-ttu-id="b5c68-124">Ohne die Hilfedateien `Get-Help` zeigt nur grundlegende Informationen zu Cmdlets an.</span><span class="sxs-lookup"><span data-stu-id="b5c68-124">Without the help files, `Get-Help` displays only basic information about cmdlets.</span></span> <span data-ttu-id="b5c68-125">Einige PowerShell-Module enthalten Hilfedateien.</span><span class="sxs-lookup"><span data-stu-id="b5c68-125">Some PowerShell modules include help files.</span></span> <span data-ttu-id="b5c68-126">Ab PowerShell 3,0 enthalten die Module, die im Lieferumfang des Windows-Betriebssystems enthalten sind, keine Hilfedateien.</span><span class="sxs-lookup"><span data-stu-id="b5c68-126">Beginning in PowerShell 3.0, the modules that come with the Windows operating system don't include help files.</span></span> <span data-ttu-id="b5c68-127">Verwenden Sie das-Cmdlet, um die Hilfedateien für ein Modul in PowerShell 3,0 herunterzuladen oder zu aktualisieren `Update-Help` .</span><span class="sxs-lookup"><span data-stu-id="b5c68-127">To download or update the help files for a module in PowerShell 3.0, use the `Update-Help` cmdlet.</span></span>

<span data-ttu-id="b5c68-128">Sie können die PowerShell-Hilfedokumente auch online im Microsoft-Dokumentation anzeigen. Um die Online Version einer Hilfedatei zu erhalten, verwenden Sie den **Online-** Parameter, z `Get-Help Get-Process -Online` . b.:.</span><span class="sxs-lookup"><span data-stu-id="b5c68-128">You can also view the PowerShell help documents online in the Microsoft Docs. To get the online version of a help file, use the **Online** parameter, such as: `Get-Help Get-Process -Online`.</span></span> <span data-ttu-id="b5c68-129">Informationen zum Lesen der gesamten PowerShell-Dokumentation finden Sie in der Microsoft-Dokumentation [PowerShell-Dokumentation](/powershell).</span><span class="sxs-lookup"><span data-stu-id="b5c68-129">To read all the PowerShell documentation, see the Microsoft Docs [PowerShell Documentation](/powershell).</span></span>

<span data-ttu-id="b5c68-130">Wenn Sie eingeben `Get-Help` , gefolgt vom exakten Namen eines Hilfe Artikels oder durch ein Wort, das für einen Hilfeartikel eindeutig ist, `Get-Help` zeigt den Inhalt des Artikels an.</span><span class="sxs-lookup"><span data-stu-id="b5c68-130">If you type `Get-Help` followed by the exact name of a help article, or by a word unique to a help article, `Get-Help` displays the article's content.</span></span> <span data-ttu-id="b5c68-131">Wenn Sie den genauen Namen eines befehlsalias angeben, wird `Get-Help` die Hilfe für den ursprünglichen Befehl angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b5c68-131">If you specify the exact name of a command alias, `Get-Help` displays the help for the original command.</span></span> <span data-ttu-id="b5c68-132">Wenn Sie ein Word-oder Word-Muster eingeben, das in mehreren Hilfeartikel Titeln angezeigt wird, `Get-Help` zeigt eine Liste der übereinstimmenden Titel an.</span><span class="sxs-lookup"><span data-stu-id="b5c68-132">If you enter a word or word pattern that appears in several help article titles, `Get-Help` displays a list of the matching titles.</span></span> <span data-ttu-id="b5c68-133">Wenn Sie Text eingeben, der nicht in den Titeln von Hilfe Artikeln enthalten ist, wird `Get-Help` von eine Liste mit Artikeln angezeigt, die diesen Text im Inhalt enthalten.</span><span class="sxs-lookup"><span data-stu-id="b5c68-133">If you enter any text that doesn't appear in any help article titles, `Get-Help` displays a list of articles that include that text in their contents.</span></span>

<span data-ttu-id="b5c68-134">`Get-Help` kann Hilfeartikel für alle unterstützten Sprachen und Gebiets Schemas erhalten.</span><span class="sxs-lookup"><span data-stu-id="b5c68-134">`Get-Help` can get help articles for all supported languages and locales.</span></span> <span data-ttu-id="b5c68-135">`Get-Help` sucht zuerst nach Hilfedateien im Gebiets Schema, das für Windows festgelegt ist, und dann im übergeordneten Gebiets Schema, z. b. **PT** für **pt-br** , und dann in einem Fall Back Gebiets Schema.</span><span class="sxs-lookup"><span data-stu-id="b5c68-135">`Get-Help` first looks for help files in the locale set for Windows, then in the parent locale, such as **pt** for **pt-BR** , and then in a fallback locale.</span></span> <span data-ttu-id="b5c68-136">Wenn in PowerShell 3,0 `Get-Help` keine Hilfe im Fall Back Gebiets Schema gefunden wird, sucht es nach Hilfe Artikeln in englischer Sprache ( **en-US** ), bevor eine Fehlermeldung zurückgegeben oder automatisch generierte Hilfe angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="b5c68-136">Beginning in PowerShell 3.0, if `Get-Help` doesn't find help in the fallback locale, it looks for help articles in English, **en-US** , before it returns an error message or displaying autogenerated help.</span></span>

<span data-ttu-id="b5c68-137">Informationen zu den Symbolen, die `Get-Help` im Befehlssyntax Diagramm angezeigt werden, finden Sie unter [about_Command_Syntax](./About/about_Command_Syntax.md).</span><span class="sxs-lookup"><span data-stu-id="b5c68-137">For information about the symbols that `Get-Help` displays in the command syntax diagram, see [about_Command_Syntax](./About/about_Command_Syntax.md).</span></span>
<span data-ttu-id="b5c68-138">Weitere Informationen zu Parameter Attributen, wie z. b. **Required** und **Position** , finden Sie unter [about_Parameters](./About/about_Parameters.md).</span><span class="sxs-lookup"><span data-stu-id="b5c68-138">For information about parameter attributes, such as **Required** and **Position** , see [about_Parameters](./About/about_Parameters.md).</span></span>

>[!NOTE]
> <span data-ttu-id="b5c68-139">In PowerShell 3,0 und PowerShell 4,0 `Get-Help` können Artikel nicht **About** in Modulen gefunden werden, es sei denn, das Modul wird in die aktuelle Sitzung importiert.</span><span class="sxs-lookup"><span data-stu-id="b5c68-139">In PowerShell 3.0 and PowerShell 4.0, `Get-Help` can't find **About** articles in modules unless the module is imported into the current session.</span></span> <span data-ttu-id="b5c68-140">Dies ist ein bekanntes Problem.</span><span class="sxs-lookup"><span data-stu-id="b5c68-140">This is a known issue.</span></span> <span data-ttu-id="b5c68-141">Um **Informationen über** Artikel in einem Modul zu erhalten, importieren Sie das Modul entweder mithilfe des- `Import-Module` Cmdlets oder durch Ausführen eines Cmdlets, das im Modul enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="b5c68-141">To get **About** articles in a module, import the module, either by using the `Import-Module` cmdlet or by running a cmdlet that's included in the module.</span></span>

## <span data-ttu-id="b5c68-142">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="b5c68-142">EXAMPLES</span></span>

### <span data-ttu-id="b5c68-143">Beispiel 1: Anzeigen grundlegender Hilfe Informationen zu einem Cmdlet</span><span class="sxs-lookup"><span data-stu-id="b5c68-143">Example 1: Display basic help information about a cmdlet</span></span>

<span data-ttu-id="b5c68-144">In diesen Beispielen werden grundlegende Hilfe Informationen zum `Format-Table` Cmdlet angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b5c68-144">These examples display basic help information about the `Format-Table` cmdlet.</span></span>

```powershell
Get-Help Format-Table
Get-Help -Name Format-Table
Format-Table -?
```

<span data-ttu-id="b5c68-145">`Get-Help <cmdlet-name>` ist die einfachste und standardmäßige Syntax des `Get-Help` Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="b5c68-145">`Get-Help <cmdlet-name>` is the simplest and default syntax of `Get-Help` cmdlet.</span></span> <span data-ttu-id="b5c68-146">Sie können den **Name** -Parameter weglassen.</span><span class="sxs-lookup"><span data-stu-id="b5c68-146">You can omit the **Name** parameter.</span></span>

<span data-ttu-id="b5c68-147">Die Syntax `<cmdlet-name> -?` funktioniert nur für Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="b5c68-147">The syntax `<cmdlet-name> -?` works only for cmdlets.</span></span>

### <span data-ttu-id="b5c68-148">Beispiel 2: Anzeigen von grundlegenden Informationen auf einer Seite</span><span class="sxs-lookup"><span data-stu-id="b5c68-148">Example 2: Display basic information one page at a time</span></span>

<span data-ttu-id="b5c68-149">In diesen Beispielen werden grundlegende Hilfe Informationen zum- `Format-Table` Cmdlet nacheinander angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b5c68-149">These examples display basic help information about the `Format-Table` cmdlet one page at a time.</span></span>

```powershell
help Format-Table
man Format-Table
Get-Help Format-Table | Out-Host -Paging
```

<span data-ttu-id="b5c68-150">`help` ist eine Funktion, die das `Get-Help` Cmdlet intern ausführt und das Ergebnis jeweils eine Seite anzeigt.</span><span class="sxs-lookup"><span data-stu-id="b5c68-150">`help` is a function that runs `Get-Help` cmdlet internally and displays the result one page at a time.</span></span>

<span data-ttu-id="b5c68-151">`man` ist ein Alias für die- `help` Funktion.</span><span class="sxs-lookup"><span data-stu-id="b5c68-151">`man` is an alias for the `help` function.</span></span>

<span data-ttu-id="b5c68-152">`Get-Help Format-Table` sendet das Objekt über die Pipeline.</span><span class="sxs-lookup"><span data-stu-id="b5c68-152">`Get-Help Format-Table` sends the object down the pipeline.</span></span> <span data-ttu-id="b5c68-153">`Out-Host -Paging` empfängt die Ausgabe der Pipeline und zeigt Sie jeweils auf einer Seite an.</span><span class="sxs-lookup"><span data-stu-id="b5c68-153">`Out-Host -Paging` receives the output from the pipeline and displays it one page at a time.</span></span> <span data-ttu-id="b5c68-154">Weitere Informationen finden Sie unter [Out-Host](Out-Host.md).</span><span class="sxs-lookup"><span data-stu-id="b5c68-154">For more information, see [Out-Host](Out-Host.md).</span></span>

### <span data-ttu-id="b5c68-155">Beispiel 3: Anzeigen von weiteren Informationen zu einem Cmdlet</span><span class="sxs-lookup"><span data-stu-id="b5c68-155">Example 3: Display more information for a cmdlet</span></span>

<span data-ttu-id="b5c68-156">In diesen Beispielen werden ausführlichere Hilfe Informationen zum `Format-Table` Cmdlet angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b5c68-156">These examples display more detailed help information about the `Format-Table` cmdlet.</span></span>

```powershell
Get-Help Format-Table -Detailed
Get-Help Format-Table -Full
```

<span data-ttu-id="b5c68-157">Der **ausführliche** Parameter zeigt die ausführliche Ansicht des Hilfe Artikels an, die Parameter Beschreibungen und Beispiele enthält.</span><span class="sxs-lookup"><span data-stu-id="b5c68-157">The **Detailed** parameter displays the help article's detailed view that includes parameter descriptions and examples.</span></span>

<span data-ttu-id="b5c68-158">Der **vollständige** Parameter zeigt die vollständige Ansicht des Hilfe Artikels an, die Parameter Beschreibungen, Beispiele, Eingabe-und Ausgabe Objekttypen sowie weitere Hinweise enthält.</span><span class="sxs-lookup"><span data-stu-id="b5c68-158">The **Full** parameter displays the help article's full view that includes parameter descriptions, examples, input and output object types, and additional notes.</span></span>

<span data-ttu-id="b5c68-159">Die **detaillierten** und **vollständigen** Parameter sind nur für die Befehle wirksam, bei denen Hilfedateien auf dem Computer installiert sind.</span><span class="sxs-lookup"><span data-stu-id="b5c68-159">The **Detailed** and **Full** parameters are effective only for the commands that have help files installed on the computer.</span></span> <span data-ttu-id="b5c68-160">Die Parameter sind für die konzeptionellen Hilfeartikel ( **About_** ) nicht wirksam.</span><span class="sxs-lookup"><span data-stu-id="b5c68-160">The parameters aren't effective for the conceptual ( **about_** ) help articles.</span></span>

### <span data-ttu-id="b5c68-161">Beispiel 4: Anzeigen ausgewählter Teile eines Cmdlets mithilfe von Parametern</span><span class="sxs-lookup"><span data-stu-id="b5c68-161">Example 4: Display selected parts of a cmdlet by using parameters</span></span>

<span data-ttu-id="b5c68-162">In diesen Beispielen werden ausgewählte Teile der `Format-Table` Cmdlet-Hilfe angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b5c68-162">These examples display selected portions of the `Format-Table` cmdlet help.</span></span>

```powershell
Get-Help Format-Table -Examples
Get-Help Format-Table -Parameter *
Get-Help Format-Table -Parameter GroupBy
```

<span data-ttu-id="b5c68-163">Der Parameter " **examples** " zeigt den **Namen** und die **Synopsis** -Abschnitte der Hilfedatei sowie alle Beispiele an.</span><span class="sxs-lookup"><span data-stu-id="b5c68-163">The **Examples** parameter displays the help file's **NAME** and **SYNOPSIS** sections, and all the Examples.</span></span> <span data-ttu-id="b5c68-164">Sie können keine Beispiel Zahl angeben, da der **examples** -Parameter ein Switch-Parameter ist.</span><span class="sxs-lookup"><span data-stu-id="b5c68-164">You can't specify an Example number because the **Examples** parameter is a switch parameter.</span></span>

<span data-ttu-id="b5c68-165">Der **Parameter** Parameter zeigt nur die Beschreibungen der angegebenen Parameter an.</span><span class="sxs-lookup"><span data-stu-id="b5c68-165">The **Parameter** parameter displays only the descriptions of the specified parameters.</span></span> <span data-ttu-id="b5c68-166">Wenn Sie nur das Sternchen ()-Platzhalter `*` Zeichen angeben, werden die Beschreibungen aller Parameter angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b5c68-166">If you specify only the asterisk (`*`) wildcard character, it displays the descriptions of all parameters.</span></span>
<span data-ttu-id="b5c68-167">Wenn **Parameter** einen Parameternamen (z. b. **GroupBy** ) angibt, werden Informationen zu diesem Parameter angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b5c68-167">When **Parameter** specifies a parameter name such as **GroupBy** , information about that parameter is shown.</span></span>

<span data-ttu-id="b5c68-168">Diese Parameter sind für die konzeptionellen Hilfeartikel ( **About_** ) nicht wirksam.</span><span class="sxs-lookup"><span data-stu-id="b5c68-168">These parameters aren't effective for the conceptual ( **about_** ) help articles.</span></span>

### <span data-ttu-id="b5c68-169">Beispiel 5: Anzeigen der Online Version der Hilfe</span><span class="sxs-lookup"><span data-stu-id="b5c68-169">Example 5: Display online version of help</span></span>

<span data-ttu-id="b5c68-170">In diesem Beispiel wird die Online Version des Hilfe Artikels für das `Format-Table` Cmdlet in Ihrem Standard Webbrowser angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b5c68-170">This example displays the online version of the help article for the `Format-Table` cmdlet in your default web browser.</span></span>

```powershell
Get-Help Format-Table -Online
```

### <span data-ttu-id="b5c68-171">Beispiel 6: Anzeigen der Hilfe zum Hilfesystem</span><span class="sxs-lookup"><span data-stu-id="b5c68-171">Example 6: Display help about the help system</span></span>

<span data-ttu-id="b5c68-172">Das- `Get-Help` Cmdlet ohne Parameter zeigt Informationen zum PowerShell-Hilfesystem an.</span><span class="sxs-lookup"><span data-stu-id="b5c68-172">The `Get-Help` cmdlet without parameters displays information about the PowerShell help system.</span></span>

```powershell
Get-Help
```

### <span data-ttu-id="b5c68-173">Beispiel 7: Anzeigen der verfügbaren Hilfeartikel</span><span class="sxs-lookup"><span data-stu-id="b5c68-173">Example 7: Display available help articles</span></span>

<span data-ttu-id="b5c68-174">In diesem Beispiel wird eine Liste aller Hilfeartikel angezeigt, die auf Ihrem Computer verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="b5c68-174">This example displays a list of all help articles available on your computer.</span></span>

```powershell
Get-Help *
```

### <span data-ttu-id="b5c68-175">Beispiel 8: Anzeigen einer Liste von konzeptionellen Artikeln</span><span class="sxs-lookup"><span data-stu-id="b5c68-175">Example 8: Display a list of conceptual articles</span></span>

<span data-ttu-id="b5c68-176">In diesem Beispiel wird eine Liste mit den konzeptionellen Artikeln angezeigt, die in der PowerShell-Hilfe enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="b5c68-176">This example displays a list of the conceptual articles included in PowerShell help.</span></span> <span data-ttu-id="b5c68-177">Alle diese Artikel beginnen mit den Zeichen **About_**.</span><span class="sxs-lookup"><span data-stu-id="b5c68-177">All these articles begin with the characters **about_**.</span></span> <span data-ttu-id="b5c68-178">Zum Anzeigen einer bestimmten Hilfedatei geben Sie `Get-Help \<about_article-name\>` z `Get-Help about_Signing` . b. ein.</span><span class="sxs-lookup"><span data-stu-id="b5c68-178">To display a particular help file, type `Get-Help \<about_article-name\>`, for example, `Get-Help about_Signing`.</span></span>

<span data-ttu-id="b5c68-179">Nur die konzeptionellen Artikel, in denen Hilfedateien auf Ihrem Computer installiert sind, werden angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b5c68-179">Only the conceptual articles that have help files installed on your computer are displayed.</span></span> <span data-ttu-id="b5c68-180">Informationen zum herunterladen und Installieren von Hilfedateien in PowerShell 3,0 finden Sie unter [Update-Help](Update-Help.md).</span><span class="sxs-lookup"><span data-stu-id="b5c68-180">For information about downloading and installing help files in PowerShell 3.0, see [Update-Help](Update-Help.md).</span></span>

```powershell
Get-Help about_*
```

### <span data-ttu-id="b5c68-181">Beispiel 9: Suchen nach einem Wort in der Cmdlet-Hilfe</span><span class="sxs-lookup"><span data-stu-id="b5c68-181">Example 9: Search for a word in cmdlet help</span></span>

<span data-ttu-id="b5c68-182">Dieses Beispiel zeigt, wie Sie in einem Cmdlet-Hilfeartikel nach einem Wort suchen.</span><span class="sxs-lookup"><span data-stu-id="b5c68-182">This example shows how to search for a word in a cmdlet help article.</span></span>

```powershell
Get-Help Add-Member -Full | Out-String -Stream | Select-String -Pattern Clixml
```

```Output
the Export-Clixml cmdlet to save the instance of the object, including the additional members...
can use the Import-Clixml cmdlet to re-create the instance of the object from the information...
Export-Clixml
Import-Clixml
```

<span data-ttu-id="b5c68-183">`Get-Help` verwendet den **Full** -Parameter, um Hilfe Informationen für zu erhalten `Add-Member` .</span><span class="sxs-lookup"><span data-stu-id="b5c68-183">`Get-Help` uses the **Full** parameter to get help information for `Add-Member`.</span></span> <span data-ttu-id="b5c68-184">Das **mamlcommandhelpinfo** -Objekt wird über die Pipeline gesendet.</span><span class="sxs-lookup"><span data-stu-id="b5c68-184">The **MamlCommandHelpInfo** object is sent down the pipeline.</span></span> <span data-ttu-id="b5c68-185">`Out-String` verwendet den **Stream** -Parameter, um das Objekt in eine Zeichenfolge zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="b5c68-185">`Out-String` uses the **Stream** parameter to convert the object into a string.</span></span> <span data-ttu-id="b5c68-186">`Select-String` verwendet den **Pattern** -Parameter, um die Zeichenfolge nach **CliXML** zu durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="b5c68-186">`Select-String` uses the **Pattern** parameter to search the string for **Clixml**.</span></span>

### <span data-ttu-id="b5c68-187">Beispiel 10: Anzeigen einer Liste von Artikeln, die ein Wort enthalten</span><span class="sxs-lookup"><span data-stu-id="b5c68-187">Example 10: Display a list of articles that include a word</span></span>

<span data-ttu-id="b5c68-188">In diesem Beispiel wird eine Liste von Artikeln angezeigt, die das Wort **Remoting** enthalten.</span><span class="sxs-lookup"><span data-stu-id="b5c68-188">This example displays a list of articles that include the word **remoting**.</span></span>

<span data-ttu-id="b5c68-189">Wenn Sie ein Wort eingeben, das in keinem Artikel Titel enthalten ist, wird `Get-Help` eine Liste mit Artikeln angezeigt, die dieses Wort enthalten.</span><span class="sxs-lookup"><span data-stu-id="b5c68-189">When you enter a word that doesn't appear in any article title, `Get-Help` displays a list of articles that include that word.</span></span>

```powershell
Get-Help -Name remoting
```

```Output
Name                              Category  Module                    Synopsis
----                              --------  ------                    --------
Install-PowerShellRemoting.ps1    External                            Install-PowerShellRemoting.ps1
Disable-PSRemoting                Cmdlet    Microsoft.PowerShell.Core Prevents remote users...
Enable-PSRemoting                 Cmdlet    Microsoft.PowerShell.Core Configures the computer...
```

### <span data-ttu-id="b5c68-190">Beispiel 11: Anzeige Anbieter spezifischer Hilfe</span><span class="sxs-lookup"><span data-stu-id="b5c68-190">Example 11: Display provider-specific help</span></span>

<span data-ttu-id="b5c68-191">Dieses Beispiel zeigt zwei Möglichkeiten, die anbieterspezifische Hilfe für zu erhalten `Get-Item` .</span><span class="sxs-lookup"><span data-stu-id="b5c68-191">This example shows two ways of getting the provider-specific help for `Get-Item`.</span></span> <span data-ttu-id="b5c68-192">Diese Befehle erhalten Hilfe, in der erläutert wird, wie das `Get-Item` Cmdlet im **DataCollection** -Knoten des PowerShell-SQL Server Anbieters verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b5c68-192">These commands get help that explains how to use the `Get-Item` cmdlet in the PowerShell SQL Server provider's **DataCollection** node.</span></span>

<span data-ttu-id="b5c68-193">Im ersten Beispiel wird der `Get-Help` **path** -Parameter verwendet, um den Pfad des SQL Server Anbieters anzugeben.</span><span class="sxs-lookup"><span data-stu-id="b5c68-193">The first example uses the `Get-Help` **Path** parameter to specify the SQL Server provider's path.</span></span>
<span data-ttu-id="b5c68-194">Da der Pfad des Anbieters angegeben ist, können Sie den Befehl von einem beliebigen Pfad Speicherort aus ausführen.</span><span class="sxs-lookup"><span data-stu-id="b5c68-194">Because the provider's path is specified, you can run the command from any path location.</span></span>

<span data-ttu-id="b5c68-195">Im zweiten Beispiel wird verwendet `Set-Location` , um zum Pfad des SQL Server Anbieters zu navigieren.</span><span class="sxs-lookup"><span data-stu-id="b5c68-195">The second example uses `Set-Location` to navigate to the SQL Server provider's path.</span></span> <span data-ttu-id="b5c68-196">An diesem Speicherort wird der **path** -Parameter nicht benötigt, um `Get-Help` die anbieterspezifische Hilfe zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="b5c68-196">From that location, the **Path** parameter isn't needed for `Get-Help` to get the provider-specific help.</span></span>

```powershell
Get-Help Get-Item -Path SQLSERVER:\DataCollection
```

```Output
NAME

    Get-Item

SYNOPSIS

    Gets a collection of Server objects for the local computer and any computers

    to which you have made a SQL Server PowerShell connection.
    ...
```

```powershell
Set-Location SQLSERVER:\DataCollection
SQLSERVER:\DataCollection> Get-Help Get-Item
```

```Output
NAME

    Get-Item

SYNOPSIS

    Gets a collection of Server objects for the local computer and any computers

    to which you have made a SQL Server PowerShell connection.
    ...
```

### <span data-ttu-id="b5c68-197">Beispiel 12: Anzeigen der Hilfe für ein Skript</span><span class="sxs-lookup"><span data-stu-id="b5c68-197">Example 12: Display help for a script</span></span>

<span data-ttu-id="b5c68-198">In diesem Beispiel wird die Hilfe für das abgerufen `MyScript.ps1 script` .</span><span class="sxs-lookup"><span data-stu-id="b5c68-198">This example gets help for the `MyScript.ps1 script`.</span></span> <span data-ttu-id="b5c68-199">Informationen zum Schreiben von Hilfe für ihre Funktionen und Skripts finden Sie unter [about_Comment_Based_Help](./About/about_Comment_Based_Help.md).</span><span class="sxs-lookup"><span data-stu-id="b5c68-199">For information about how to write help for your functions and scripts, see [about_Comment_Based_Help](./About/about_Comment_Based_Help.md).</span></span>

```powershell
Get-Help -Name C:\PS-Test\MyScript.ps1
```

## <span data-ttu-id="b5c68-200">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b5c68-200">PARAMETERS</span></span>

### <span data-ttu-id="b5c68-201">-Kategorie</span><span class="sxs-lookup"><span data-stu-id="b5c68-201">-Category</span></span>

<span data-ttu-id="b5c68-202">Zeigt nur für Elemente in der angegebenen Kategorie und ihre Aliase Hilfe an.</span><span class="sxs-lookup"><span data-stu-id="b5c68-202">Displays help only for items in the specified category and their aliases.</span></span> <span data-ttu-id="b5c68-203">Konzeptionelle Artikel befinden sich in der Kategorie **HelpFile** .</span><span class="sxs-lookup"><span data-stu-id="b5c68-203">Conceptual articles are in the **HelpFile** category.</span></span>

<span data-ttu-id="b5c68-204">Die zulässigen Werte für diesen Parameter lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="b5c68-204">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="b5c68-205">Alias</span><span class="sxs-lookup"><span data-stu-id="b5c68-205">Alias</span></span>
- <span data-ttu-id="b5c68-206">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="b5c68-206">Cmdlet</span></span>
- <span data-ttu-id="b5c68-207">Anbieter</span><span class="sxs-lookup"><span data-stu-id="b5c68-207">Provider</span></span>
- <span data-ttu-id="b5c68-208">Allgemein</span><span class="sxs-lookup"><span data-stu-id="b5c68-208">General</span></span>
- <span data-ttu-id="b5c68-209">Häufig gestellte Fragen</span><span class="sxs-lookup"><span data-stu-id="b5c68-209">FAQ</span></span>
- <span data-ttu-id="b5c68-210">Glossar</span><span class="sxs-lookup"><span data-stu-id="b5c68-210">Glossary</span></span>
- <span data-ttu-id="b5c68-211">HelpFile</span><span class="sxs-lookup"><span data-stu-id="b5c68-211">HelpFile</span></span>
- <span data-ttu-id="b5c68-212">ScriptCommand</span><span class="sxs-lookup"><span data-stu-id="b5c68-212">ScriptCommand</span></span>
- <span data-ttu-id="b5c68-213">Funktion</span><span class="sxs-lookup"><span data-stu-id="b5c68-213">Function</span></span>
- <span data-ttu-id="b5c68-214">Filter</span><span class="sxs-lookup"><span data-stu-id="b5c68-214">Filter</span></span>
- <span data-ttu-id="b5c68-215">Externalscript</span><span class="sxs-lookup"><span data-stu-id="b5c68-215">ExternalScript</span></span>
- <span data-ttu-id="b5c68-216">Alle</span><span class="sxs-lookup"><span data-stu-id="b5c68-216">All</span></span>
- <span data-ttu-id="b5c68-217">Defaulthelp</span><span class="sxs-lookup"><span data-stu-id="b5c68-217">DefaultHelp</span></span>
- <span data-ttu-id="b5c68-218">Workflow</span><span class="sxs-lookup"><span data-stu-id="b5c68-218">Workflow</span></span>
- <span data-ttu-id="b5c68-219">DscResource</span><span class="sxs-lookup"><span data-stu-id="b5c68-219">DscResource</span></span>
- <span data-ttu-id="b5c68-220">Klasse</span><span class="sxs-lookup"><span data-stu-id="b5c68-220">Class</span></span>
- <span data-ttu-id="b5c68-221">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="b5c68-221">Configuration</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:
Accepted values: Alias, Cmdlet, Provider, General, FAQ, Glossary, HelpFile, ScriptCommand, Function, Filter, ExternalScript, All, DefaultHelp, Workflow, DscResource, Class, Configuration

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b5c68-222">-Komponente</span><span class="sxs-lookup"><span data-stu-id="b5c68-222">-Component</span></span>

<span data-ttu-id="b5c68-223">Zeigt Befehle mit dem angegebenen Komponenten Wert an, z. b. **Exchange**.</span><span class="sxs-lookup"><span data-stu-id="b5c68-223">Displays commands with the specified component value, such as **Exchange**.</span></span> <span data-ttu-id="b5c68-224">Geben Sie einen Komponentennamen ein.</span><span class="sxs-lookup"><span data-stu-id="b5c68-224">Enter a component name.</span></span>
<span data-ttu-id="b5c68-225">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="b5c68-225">Wildcard characters are permitted.</span></span> <span data-ttu-id="b5c68-226">Dieser Parameter hat keine Auswirkung auf die Anzeige der konzeptionellen Hilfe ( **About_** ).</span><span class="sxs-lookup"><span data-stu-id="b5c68-226">This parameter has no effect on displays of conceptual ( **About_** ) help.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="b5c68-227">-Detailed</span><span class="sxs-lookup"><span data-stu-id="b5c68-227">-Detailed</span></span>

<span data-ttu-id="b5c68-228">Fügt der Anzeige der grundlegende Hilfe Parameterbeschreibungen und Beispiele hinzu.</span><span class="sxs-lookup"><span data-stu-id="b5c68-228">Adds parameter descriptions and examples to the basic help display.</span></span> <span data-ttu-id="b5c68-229">Dieser Parameter ist nur wirksam, wenn die Hilfedateien auf dem Computer installiert sind.</span><span class="sxs-lookup"><span data-stu-id="b5c68-229">This parameter is effective only when the help files are installed on the computer.</span></span> <span data-ttu-id="b5c68-230">Dies hat keine Auswirkung auf die Anzeige der konzeptionellen Hilfe ( **About_** ).</span><span class="sxs-lookup"><span data-stu-id="b5c68-230">It has no effect on displays of conceptual ( **About_** ) help.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: DetailedView
Aliases:

Required: True
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b5c68-231">-Examples</span><span class="sxs-lookup"><span data-stu-id="b5c68-231">-Examples</span></span>

<span data-ttu-id="b5c68-232">Zeigt nur den Namen, die Zusammenfassung und Beispiele an.</span><span class="sxs-lookup"><span data-stu-id="b5c68-232">Displays only the name, synopsis, and examples.</span></span> <span data-ttu-id="b5c68-233">Geben Sie ein, um nur die Beispiele anzuzeigen `(Get-Help \<cmdlet-name\>).Examples` .</span><span class="sxs-lookup"><span data-stu-id="b5c68-233">To display only the examples, type `(Get-Help \<cmdlet-name\>).Examples`.</span></span>

<span data-ttu-id="b5c68-234">Dieser Parameter ist nur wirksam, wenn die Hilfedateien auf dem Computer installiert sind.</span><span class="sxs-lookup"><span data-stu-id="b5c68-234">This parameter is effective only when the help files are installed on the computer.</span></span> <span data-ttu-id="b5c68-235">Dies hat keine Auswirkung auf die Anzeige der konzeptionellen Hilfe ( **About_** ).</span><span class="sxs-lookup"><span data-stu-id="b5c68-235">It has no effect on displays of conceptual ( **About_** ) help.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Examples
Aliases:

Required: True
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b5c68-236">-Full</span><span class="sxs-lookup"><span data-stu-id="b5c68-236">-Full</span></span>

<span data-ttu-id="b5c68-237">Zeigt den gesamten Hilfeartikel für ein Cmdlet an.</span><span class="sxs-lookup"><span data-stu-id="b5c68-237">Displays the entire help article for a cmdlet.</span></span> <span data-ttu-id="b5c68-238">**Vollständig** umfasst Parameter Beschreibungen und-Attribute, Beispiele, Eingabe-und Ausgabe Objekttypen sowie weitere Hinweise.</span><span class="sxs-lookup"><span data-stu-id="b5c68-238">**Full** includes parameter descriptions and attributes, examples, input and output object types, and additional notes.</span></span>

<span data-ttu-id="b5c68-239">Dieser Parameter ist nur wirksam, wenn die Hilfedateien auf dem Computer installiert sind.</span><span class="sxs-lookup"><span data-stu-id="b5c68-239">This parameter is effective only when the help files are installed on the computer.</span></span> <span data-ttu-id="b5c68-240">Dies hat keine Auswirkung auf die Anzeige der konzeptionellen Hilfe ( **About_** ).</span><span class="sxs-lookup"><span data-stu-id="b5c68-240">It has no effect on displays of conceptual ( **About_** ) help.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: AllUsersView
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b5c68-241">-Funktionalität</span><span class="sxs-lookup"><span data-stu-id="b5c68-241">-Functionality</span></span>

<span data-ttu-id="b5c68-242">Zeigt Hilfe für Elemente mit der angegebenen Funktionalität an.</span><span class="sxs-lookup"><span data-stu-id="b5c68-242">Displays help for items with the specified functionality.</span></span> <span data-ttu-id="b5c68-243">Geben Sie die Funktionalität ein.</span><span class="sxs-lookup"><span data-stu-id="b5c68-243">Enter the functionality.</span></span> <span data-ttu-id="b5c68-244">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="b5c68-244">Wildcard characters are permitted.</span></span> <span data-ttu-id="b5c68-245">Dieser Parameter hat keine Auswirkung auf die Anzeige der konzeptionellen Hilfe ( **About_** ).</span><span class="sxs-lookup"><span data-stu-id="b5c68-245">This parameter has no effect on displays of conceptual ( **About_** ) help.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="b5c68-246">-Name</span><span class="sxs-lookup"><span data-stu-id="b5c68-246">-Name</span></span>

<span data-ttu-id="b5c68-247">Ruft Hilfe zum angegebenen Befehl oder Konzept ab.</span><span class="sxs-lookup"><span data-stu-id="b5c68-247">Gets help about the specified command or concept.</span></span> <span data-ttu-id="b5c68-248">Geben Sie den Namen eines Cmdlets, einer Funktion, eines Anbieters, eines Skripts oder eines Workflows ein, z `Get-Member` . b. einen konzeptionellen Artikelnamen, z `about_Objects` . b. oder einen Alias, z `ls` . b..</span><span class="sxs-lookup"><span data-stu-id="b5c68-248">Enter the name of a cmdlet, function, provider, script, or workflow, such as `Get-Member`, a conceptual article name, such as `about_Objects`, or an alias, such as `ls`.</span></span> <span data-ttu-id="b5c68-249">Platzhalter Zeichen sind in Cmdlet-und Anbieter Namen zulässig, Sie können jedoch keine Platzhalter Zeichen verwenden, um die Namen der Hilfe-und Skript Hilfeartikel zu finden.</span><span class="sxs-lookup"><span data-stu-id="b5c68-249">Wildcard characters are permitted in cmdlet and provider names, but you can't use wildcard characters to find the names of function help and script help articles.</span></span>

<span data-ttu-id="b5c68-250">Um Hilfe für ein Skript zu erhalten, das sich nicht in einem Pfad befindet, der in der `$env:Path` Umgebungsvariablen aufgelistet ist, geben Sie den Pfad und den Dateinamen des Skripts ein.</span><span class="sxs-lookup"><span data-stu-id="b5c68-250">To get help for a script that isn't located in a path that's listed in the `$env:Path` environment variable, type the script's path and file name.</span></span>

<span data-ttu-id="b5c68-251">Wenn Sie den genauen Namen eines Hilfe Artikels eingeben, wird `Get-Help` der Artikel Inhalt von angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b5c68-251">If you enter the exact name of a help article, `Get-Help` displays the article contents.</span></span>

<span data-ttu-id="b5c68-252">Wenn Sie ein Word-oder Word-Muster eingeben, das in mehreren Hilfeartikel Titeln angezeigt wird, `Get-Help` zeigt eine Liste der übereinstimmenden Titel an.</span><span class="sxs-lookup"><span data-stu-id="b5c68-252">If you enter a word or word pattern that appears in several help article titles, `Get-Help` displays a list of the matching titles.</span></span>

<span data-ttu-id="b5c68-253">Wenn Sie Text eingeben, der mit keinem der Hilfeartikel Titel identisch ist, wird `Get-Help` eine Liste von Artikeln angezeigt, die diesen Text im Inhalt enthalten.</span><span class="sxs-lookup"><span data-stu-id="b5c68-253">If you enter any text that doesn't match any help article titles, `Get-Help` displays a list of articles that include that text in their contents.</span></span>

<span data-ttu-id="b5c68-254">Die Namen von konzeptionellen Artikeln (z `about_Objects` . b.) müssen in englischer Sprache eingegeben werden, auch in nicht englischsprachigen Versionen von PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b5c68-254">The names of conceptual articles, such as `about_Objects`, must be entered in English, even in non-English versions of PowerShell.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="b5c68-255">-Online</span><span class="sxs-lookup"><span data-stu-id="b5c68-255">-Online</span></span>

<span data-ttu-id="b5c68-256">Zeigt die Online Version eines Hilfe Artikels im Standardbrowser an.</span><span class="sxs-lookup"><span data-stu-id="b5c68-256">Displays the online version of a help article in the default browser.</span></span> <span data-ttu-id="b5c68-257">Dieser Parameter ist nur für Cmdlet-, Function-, Workflow-und Skript-Hilfeartikel gültig.</span><span class="sxs-lookup"><span data-stu-id="b5c68-257">This parameter is valid only for cmdlet, function, workflow, and script help articles.</span></span> <span data-ttu-id="b5c68-258">Der **Online-** Parameter kann nicht mit `Get-Help` in einer Remote Sitzung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b5c68-258">You can't use the **Online** parameter with `Get-Help` in a remote session.</span></span>

<span data-ttu-id="b5c68-259">Weitere Informationen zur Unterstützung dieser Funktion in Hilfe Artikeln, die Sie schreiben, finden Sie unter [about_Comment_Based_Help](./About/about_Comment_Based_Help.md)und [unterstützen der Online Hilfe](/powershell/scripting/developer/module/supporting-online-help)und [Schreiben der Hilfe für PowerShell-Cmdlets](/powershell/scripting/developer/help/writing-help-for-windows-powershell-cmdlets).</span><span class="sxs-lookup"><span data-stu-id="b5c68-259">For information about supporting this feature in help articles that you write, see [about_Comment_Based_Help](./About/about_Comment_Based_Help.md), and [Supporting Online Help](/powershell/scripting/developer/module/supporting-online-help), and [Writing Help for PowerShell Cmdlets](/powershell/scripting/developer/help/writing-help-for-windows-powershell-cmdlets).</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Online
Aliases:

Required: True
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b5c68-260">-Parameter</span><span class="sxs-lookup"><span data-stu-id="b5c68-260">-Parameter</span></span>

<span data-ttu-id="b5c68-261">Zeigt nur die ausführlichen Beschreibungen der angegebenen Parameter an.</span><span class="sxs-lookup"><span data-stu-id="b5c68-261">Displays only the detailed descriptions of the specified parameters.</span></span> <span data-ttu-id="b5c68-262">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="b5c68-262">Wildcards are permitted.</span></span> <span data-ttu-id="b5c68-263">Dieser Parameter hat keine Auswirkung auf die Anzeige der konzeptionellen Hilfe ( **About_** ).</span><span class="sxs-lookup"><span data-stu-id="b5c68-263">This parameter has no effect on displays of conceptual ( **About_** ) help.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Parameters
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="b5c68-264">-Path</span><span class="sxs-lookup"><span data-stu-id="b5c68-264">-Path</span></span>

<span data-ttu-id="b5c68-265">Ruft Hilfe ab, die die Funktionsweise des Cmdlets im angegebenen Anbieterpfad erläutert.</span><span class="sxs-lookup"><span data-stu-id="b5c68-265">Gets help that explains how the cmdlet works in the specified provider path.</span></span> <span data-ttu-id="b5c68-266">Geben Sie einen PowerShell-Anbieter Pfad ein.</span><span class="sxs-lookup"><span data-stu-id="b5c68-266">Enter a PowerShell provider path.</span></span>

<span data-ttu-id="b5c68-267">Dieser Parameter ruft eine angepasste Version eines Cmdlet-Hilfe Artikels ab, in der erläutert wird, wie das Cmdlet im angegebenen PowerShell-Anbieter Pfad funktioniert.</span><span class="sxs-lookup"><span data-stu-id="b5c68-267">This parameter gets a customized version of a cmdlet help article that explains how the cmdlet works in the specified PowerShell provider path.</span></span> <span data-ttu-id="b5c68-268">Dieser Parameter ist nur für Hilfe zu einem Anbieter-Cmdlet und nur dann gültig, wenn der Anbieter eine benutzerdefinierte Version des Hilfe Artikels des Provider-Cmdlets in der Hilfedatei enthält.</span><span class="sxs-lookup"><span data-stu-id="b5c68-268">This parameter is effective only for help about a provider cmdlet and only when the provider includes a custom version of the provider cmdlet help article in its help file.</span></span> <span data-ttu-id="b5c68-269">Um diesen Parameter zu verwenden, installieren Sie die Hilfedatei für das Modul, das den Anbieter enthält.</span><span class="sxs-lookup"><span data-stu-id="b5c68-269">To use this parameter, install the help file for the module that includes the provider.</span></span>

<span data-ttu-id="b5c68-270">Um die Hilfe zum benutzerdefinierten Cmdlet für einen Anbieter Pfad anzuzeigen, wechseln Sie zum Speicherort des Anbieter Pfads, und geben Sie einen Befehl ein, `Get-Help` oder verwenden Sie aus einem beliebigen Pfad den **Pfad** Parameter von, `Get-Help` um den Anbieter Pfad anzugeben.</span><span class="sxs-lookup"><span data-stu-id="b5c68-270">To see the custom cmdlet help for a provider path, go to the provider path location and enter a `Get-Help` command or, from any path location, use the **Path** parameter of `Get-Help` to specify the provider path.</span></span> <span data-ttu-id="b5c68-271">Die benutzerdefinierte Cmdlet-Hilfe finden Sie auch online im Abschnitt Anbieter Hilfe der Hilfeartikel.</span><span class="sxs-lookup"><span data-stu-id="b5c68-271">You can also find custom cmdlet help online in the provider help section of the help articles.</span></span>

<span data-ttu-id="b5c68-272">Weitere Informationen zu PowerShell-Anbietern finden Sie unter [about_Providers](./About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="b5c68-272">For more information about PowerShell providers, see [about_Providers](./About/about_Providers.md).</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="b5c68-273">-Rolle</span><span class="sxs-lookup"><span data-stu-id="b5c68-273">-Role</span></span>

<span data-ttu-id="b5c68-274">Zeigt Hilfe an, die für die angegebene Benutzerrolle angepasst wurde.</span><span class="sxs-lookup"><span data-stu-id="b5c68-274">Displays help customized for the specified user role.</span></span> <span data-ttu-id="b5c68-275">Geben Sie eine Rolle ein.</span><span class="sxs-lookup"><span data-stu-id="b5c68-275">Enter a role.</span></span> <span data-ttu-id="b5c68-276">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="b5c68-276">Wildcard characters are permitted.</span></span>

<span data-ttu-id="b5c68-277">Geben Sie die Rolle ein, die der Benutzer in einer Organisation inne hat.</span><span class="sxs-lookup"><span data-stu-id="b5c68-277">Enter the role that the user plays in an organization.</span></span> <span data-ttu-id="b5c68-278">Einige Cmdlets zeigen basierend auf dem Wert dieses Parameters unterschiedlichen Text in ihren Hilfedateien an.</span><span class="sxs-lookup"><span data-stu-id="b5c68-278">Some cmdlets display different text in their help files based on the value of this parameter.</span></span> <span data-ttu-id="b5c68-279">Dieser Parameter hat keine Auswirkungen auf die Hilfe für die Haupt-Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="b5c68-279">This parameter has no effect on help for the core cmdlets.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="b5c68-280">-ShowWindow</span><span class="sxs-lookup"><span data-stu-id="b5c68-280">-ShowWindow</span></span>

<span data-ttu-id="b5c68-281">Zeigt das Hilfethema zur besseren Lesbarkeit in einem Fenster an.</span><span class="sxs-lookup"><span data-stu-id="b5c68-281">Displays the help topic in a window for easier reading.</span></span> <span data-ttu-id="b5c68-282">Das Fenster enthält eine **Suchfunktion suchen und** ein **Einstellungs** Feld, mit dem Sie Optionen für die Anzeige festlegen können, einschließlich Optionen, um nur ausgewählte Abschnitte eines Hilfe Themas anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="b5c68-282">The window includes a **Find** search feature and a **Settings** box that lets you set options for the display, including options to display only selected sections of a help topic.</span></span>

<span data-ttu-id="b5c68-283">Der **ShowWindow** -Parameter unterstützt Hilfe Themen für Befehle (Cmdlets, Funktionen, CIM-Befehle, Skripts) und konzeptionelle **Informationen zu** Artikeln.</span><span class="sxs-lookup"><span data-stu-id="b5c68-283">The **ShowWindow** parameter supports help topics for commands (cmdlets, functions, CIM commands, scripts) and conceptual **About** articles.</span></span> <span data-ttu-id="b5c68-284">Die Anbieterhilfe wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b5c68-284">It does not support provider help.</span></span>

<span data-ttu-id="b5c68-285">Dieser Parameter wurde in PowerShell 7,0 erneut eingeführt.</span><span class="sxs-lookup"><span data-stu-id="b5c68-285">This parameter was reintroduced in PowerShell 7.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ShowWindow
Aliases:

Required: True
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b5c68-286">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="b5c68-286">CommonParameters</span></span>

<span data-ttu-id="b5c68-287">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="b5c68-287">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b5c68-288">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="b5c68-288">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b5c68-289">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="b5c68-289">INPUTS</span></span>

### <span data-ttu-id="b5c68-290">Keine</span><span class="sxs-lookup"><span data-stu-id="b5c68-290">None</span></span>

<span data-ttu-id="b5c68-291">Objekte können nicht über die Pipeline an gesendet werden `Get-Help` .</span><span class="sxs-lookup"><span data-stu-id="b5c68-291">You can't send objects down the pipeline to `Get-Help`.</span></span>

## <span data-ttu-id="b5c68-292">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="b5c68-292">OUTPUTS</span></span>

### <span data-ttu-id="b5c68-293">Extendedcmdlethelpinfo</span><span class="sxs-lookup"><span data-stu-id="b5c68-293">ExtendedCmdletHelpInfo</span></span>

<span data-ttu-id="b5c68-294">Wenn Sie `Get-Help` mit einem Befehl ausführen, der keine Hilfedatei enthält, `Get-Help` gibt ein **extendedcmdlethelpinfo** -Objekt zurück, das die automatisch generierte Hilfe darstellt.</span><span class="sxs-lookup"><span data-stu-id="b5c68-294">If you run `Get-Help` on a command that doesn't have a help file, `Get-Help` returns an **ExtendedCmdletHelpInfo** object that represents autogenerated help.</span></span>

### <span data-ttu-id="b5c68-295">System.String</span><span class="sxs-lookup"><span data-stu-id="b5c68-295">System.String</span></span>

<span data-ttu-id="b5c68-296">Wenn Sie einen konzeptionellen Hilfeartikel erhalten, `Get-Help` gibt ihn als Zeichenfolge zurück.</span><span class="sxs-lookup"><span data-stu-id="b5c68-296">If you get a conceptual help article, `Get-Help` returns it as a string.</span></span>

### <span data-ttu-id="b5c68-297">MamlCommandHelpInfo</span><span class="sxs-lookup"><span data-stu-id="b5c68-297">MamlCommandHelpInfo</span></span>

<span data-ttu-id="b5c68-298">Wenn Sie einen Befehl mit einer Hilfedatei erhalten, `Get-Help` gibt ein **mamlcommandhelpinfo** -Objekt zurück.</span><span class="sxs-lookup"><span data-stu-id="b5c68-298">If you get a command that has a help file, `Get-Help` returns a **MamlCommandHelpInfo** object.</span></span>

## <span data-ttu-id="b5c68-299">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="b5c68-299">NOTES</span></span>

<span data-ttu-id="b5c68-300">PowerShell 3,0 enthält keine Hilfedateien.</span><span class="sxs-lookup"><span data-stu-id="b5c68-300">PowerShell 3.0 doesn't include help files.</span></span> <span data-ttu-id="b5c68-301">`Get-Help`Verwenden Sie das-Cmdlet, um die von gelesenen Hilfedateien herunterzuladen und zu installieren `Update-Help` .</span><span class="sxs-lookup"><span data-stu-id="b5c68-301">To download and install the help files that `Get-Help` reads, use the `Update-Help` cmdlet.</span></span> <span data-ttu-id="b5c68-302">Sie können das `Update-Help` Cmdlet zum herunterladen und Installieren von Hilfedateien für die Kern Befehle verwenden, die in PowerShell enthalten sind, sowie für alle Module, die Sie installieren.</span><span class="sxs-lookup"><span data-stu-id="b5c68-302">You can use the `Update-Help` cmdlet to download and install help files for the core commands that come with PowerShell and for any modules that you install.</span></span> <span data-ttu-id="b5c68-303">Sie können damit auch die Hilfedateien aktualisieren, sodass die Hilfedateien auf Ihrem Computer immer auf dem neuesten Stand sind.</span><span class="sxs-lookup"><span data-stu-id="b5c68-303">You can also use it to update the help files so that the help on your computer is never outdated.</span></span>

<span data-ttu-id="b5c68-304">Unter Erste Schritte [mit Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell)können Sie auch die Hilfeartikel zu den Befehlen von PowerShell Online lesen.</span><span class="sxs-lookup"><span data-stu-id="b5c68-304">You can also read the help articles about the commands that come with PowerShell online starting at [Getting Started with Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell).</span></span>

<span data-ttu-id="b5c68-305">`Get-Help` zeigt die Hilfe im Gebiets Schema an, das für das Windows-Betriebssystem oder in der Fall Back Sprache für dieses Gebiets Schema festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="b5c68-305">`Get-Help` displays help in the locale set for the Windows operating system or in the fallback language for that locale.</span></span> <span data-ttu-id="b5c68-306">Wenn Sie keine Hilfedateien für das primäre oder das Ausweich Gebiets Schema haben, `Get-Help` verhält sich so, als ob keine Hilfedateien auf dem Computer vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="b5c68-306">If you don't have help files for the primary or fallback locale, `Get-Help` behaves as if there are no help files on the computer.</span></span> <span data-ttu-id="b5c68-307">Um Hilfe für ein anderes Gebiets Schema zu erhalten, verwenden Sie **Region** und **Sprache** in der Systemsteuerung, um die Einstellungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="b5c68-307">To get help for a different locale, use **Region** and **Language** in Control Panel to change the settings.</span></span> <span data-ttu-id="b5c68-308">Unter Windows 10, **Einstellungen** , **Zeit & Sprache**.</span><span class="sxs-lookup"><span data-stu-id="b5c68-308">On Windows 10, **Settings** , **Time & Language**.</span></span>

<span data-ttu-id="b5c68-309">Die vollständige Ansicht der Hilfe enthält eine Tabelle mit Informationen zu den Parametern.</span><span class="sxs-lookup"><span data-stu-id="b5c68-309">The full view of help includes a table of information about the parameters.</span></span> <span data-ttu-id="b5c68-310">Die Tabelle enthält die folgenden Felder:</span><span class="sxs-lookup"><span data-stu-id="b5c68-310">The table includes the following fields:</span></span>

- <span data-ttu-id="b5c68-311">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="b5c68-311">**Required**.</span></span> <span data-ttu-id="b5c68-312">Gibt an, ob der Parameter erforderlich (true) oder optional ist (false).</span><span class="sxs-lookup"><span data-stu-id="b5c68-312">Indicates whether the parameter is required (true) or optional (false).</span></span>

- <span data-ttu-id="b5c68-313">**Position**.</span><span class="sxs-lookup"><span data-stu-id="b5c68-313">**Position**.</span></span> <span data-ttu-id="b5c68-314">Gibt an, ob der Parameter benannt oder Positions basiert (numerisch) ist.</span><span class="sxs-lookup"><span data-stu-id="b5c68-314">Indicates whether the parameter is named or positional (numeric).</span></span> <span data-ttu-id="b5c68-315">Positionsparameter müssen an einer angegebenen Position im Befehl verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b5c68-315">Positional parameters must appear in a specified place in the command.</span></span>

- <span data-ttu-id="b5c68-316">Mit dem **Namen** wird angegeben, dass der Parameter Name erforderlich ist, aber der Parameter kann an beliebiger Stelle im Befehl angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="b5c68-316">**Named** indicates that the parameter name is required, but that the parameter can appear anywhere in the command.</span></span>

- <span data-ttu-id="b5c68-317">**Numeric** gibt an, dass der Parameter Name optional ist, aber wenn der Name ausgelassen wird, muss der Parameter an der Stelle liegen, die durch die Zahl angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="b5c68-317">**Numeric** indicates that the parameter name is optional, but when the name is omitted, the parameter must be in the place specified by the number.</span></span> <span data-ttu-id="b5c68-318">`2`Gibt z. b. an, dass der Parameter, wenn der Parameter Name weggelassen wird, der zweite oder einzige unbenannte Parameter im Befehl sein muss.</span><span class="sxs-lookup"><span data-stu-id="b5c68-318">For example, `2` indicates that when the parameter name is omitted, the parameter must be the second or only unnamed parameter in the command.</span></span> <span data-ttu-id="b5c68-319">Wenn der Parametername verwendet wird, kann der Parameter an einer beliebigen Stelle im Befehl stehen.</span><span class="sxs-lookup"><span data-stu-id="b5c68-319">When the parameter name is used, the parameter can appear anywhere in the command.</span></span>

- <span data-ttu-id="b5c68-320">**Standardwert**.</span><span class="sxs-lookup"><span data-stu-id="b5c68-320">**Default value**.</span></span> <span data-ttu-id="b5c68-321">Der Parameterwert oder das Standardverhalten, das von PowerShell verwendet wird, wenn Sie den Parameter nicht in den Befehl einschließen.</span><span class="sxs-lookup"><span data-stu-id="b5c68-321">The parameter value or default behavior that PowerShell uses if you don't include the parameter in the command.</span></span>

- <span data-ttu-id="b5c68-322">Akzeptiert Pipeline Eingaben.</span><span class="sxs-lookup"><span data-stu-id="b5c68-322">Accepts pipeline input.</span></span> <span data-ttu-id="b5c68-323">Gibt an, ob Sie Objekte über eine Pipeline an den Parameter senden können (true) oder nicht (false).</span><span class="sxs-lookup"><span data-stu-id="b5c68-323">Indicates whether you can (true) or can't (false) send objects to the parameter through a pipeline.</span></span> <span data-ttu-id="b5c68-324">**Nach Eigenschaftsname** bedeutet, dass das Pipeline Objekt über eine Eigenschaft verfügen muss, die den gleichen Namen wie der Parameter Name hat.</span><span class="sxs-lookup"><span data-stu-id="b5c68-324">**By Property Name** means that the pipelined object must have a property that has the same name as the parameter name.</span></span>

- <span data-ttu-id="b5c68-325">**Akzeptiert** Platzhalter Zeichen.</span><span class="sxs-lookup"><span data-stu-id="b5c68-325">**Accepts wildcard characters**.</span></span> <span data-ttu-id="b5c68-326">Gibt an, ob der Wert eines Parameters Platzhalter Zeichen enthalten kann, z. b. ein Sternchen ( `*` ) oder ein Fragezeichen ( `?` ).</span><span class="sxs-lookup"><span data-stu-id="b5c68-326">Indicates whether the value of a parameter can include wildcard characters, such as an asterisk (`*`) or question mark (`?`).</span></span>

## <span data-ttu-id="b5c68-327">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="b5c68-327">RELATED LINKS</span></span>

[<span data-ttu-id="b5c68-328">about_Command_Syntax</span><span class="sxs-lookup"><span data-stu-id="b5c68-328">about_Command_Syntax</span></span>](About/about_Command_Syntax.md)

[<span data-ttu-id="b5c68-329">about_Comment_Based_Help</span><span class="sxs-lookup"><span data-stu-id="b5c68-329">about_Comment_Based_Help</span></span>](./About/about_Comment_Based_Help.md)

[<span data-ttu-id="b5c68-330">Get-Command</span><span class="sxs-lookup"><span data-stu-id="b5c68-330">Get-Command</span></span>](Get-Command.md)

[<span data-ttu-id="b5c68-331">Unterstützung einer aktualisierbaren Hilfe</span><span class="sxs-lookup"><span data-stu-id="b5c68-331">Supporting Updatable Help</span></span>](/powershell/scripting/developer/module/supporting-updatable-help)

[<span data-ttu-id="b5c68-332">Update-Help</span><span class="sxs-lookup"><span data-stu-id="b5c68-332">Update-Help</span></span>](Update-Help.md)

[<span data-ttu-id="b5c68-333">Schreiben von kommentarbasierten Hilfethemen</span><span class="sxs-lookup"><span data-stu-id="b5c68-333">Writing Comment-Based Help Topics</span></span>](/powershell/scripting/developer/help/writing-comment-based-help-topics)

[<span data-ttu-id="b5c68-334">Schreiben einer Hilfe für PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="b5c68-334">Writing Help for PowerShell Cmdlets</span></span>](/powershell/scripting/developer/help/writing-help-for-windows-powershell-cmdlets)

