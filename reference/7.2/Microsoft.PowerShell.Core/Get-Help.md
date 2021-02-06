---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 09/03/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-help?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Help
ms.openlocfilehash: 82721b3d079c795e0ce6fcae1fba0eab93344b52
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601109"
---
# <span data-ttu-id="0dafc-102">Get-Help</span><span class="sxs-lookup"><span data-stu-id="0dafc-102">Get-Help</span></span>

## <span data-ttu-id="0dafc-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="0dafc-103">SYNOPSIS</span></span>
<span data-ttu-id="0dafc-104">Zeigt Informationen zu PowerShell-Befehlen und-Konzepten an.</span><span class="sxs-lookup"><span data-stu-id="0dafc-104">Displays information about PowerShell commands and concepts.</span></span>

## <span data-ttu-id="0dafc-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="0dafc-105">SYNTAX</span></span>

### <span data-ttu-id="0dafc-106">Allusersview (Standard)</span><span class="sxs-lookup"><span data-stu-id="0dafc-106">AllUsersView (Default)</span></span>

```
Get-Help [[-Name] <String>] [-Path <String>] [-Category <String[]>] [-Full] [-Component <String[]>]
 [-Functionality <String[]>] [-Role <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="0dafc-107">Detailedview</span><span class="sxs-lookup"><span data-stu-id="0dafc-107">DetailedView</span></span>

```
Get-Help [[-Name] <String>] [-Path <String>] [-Category <String[]>] -Detailed
 [-Component <String[]>] [-Functionality <String[]>] [-Role <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="0dafc-108">Beispiele</span><span class="sxs-lookup"><span data-stu-id="0dafc-108">Examples</span></span>

```
Get-Help [[-Name] <String>] [-Path <String>] [-Category <String[]>] -Examples
 [-Component <String[]>] [-Functionality <String[]>] [-Role <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="0dafc-109">Parameter</span><span class="sxs-lookup"><span data-stu-id="0dafc-109">Parameters</span></span>

```
Get-Help [[-Name] <String>] [-Path <String>] [-Category <String[]>] -Parameter <String[]>
 [-Component <String[]>] [-Functionality <String[]>] [-Role <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="0dafc-110">Online</span><span class="sxs-lookup"><span data-stu-id="0dafc-110">Online</span></span>

```
Get-Help [[-Name] <String>] [-Path <String>] [-Category <String[]>] [-Component <String[]>]
 [-Functionality <String[]>] [-Role <String[]>] -Online [<CommonParameters>]
```

### <span data-ttu-id="0dafc-111">ShowWindow</span><span class="sxs-lookup"><span data-stu-id="0dafc-111">ShowWindow</span></span>

```
Get-Help [[-Name] <String>] [-Path <String>] [-Category <String[]>] [-Component <String[]>]
 [-Functionality <String[]>] [-Role <String[]>] -ShowWindow [<CommonParameters>]
```

## <span data-ttu-id="0dafc-112">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0dafc-112">DESCRIPTION</span></span>

<span data-ttu-id="0dafc-113">Das `Get-Help` -Cmdlet zeigt Informationen zu PowerShell-Konzepten und-Befehlen an, einschließlich Cmdlets, Funktionen, Common Information Model (CIM)-Befehlen, Workflows, Anbietern, Aliase und Skripts.</span><span class="sxs-lookup"><span data-stu-id="0dafc-113">The `Get-Help` cmdlet displays information about PowerShell concepts and commands, including cmdlets, functions, Common Information Model (CIM) commands, workflows, providers, aliases, and scripts.</span></span>

<span data-ttu-id="0dafc-114">Um Hilfe zu einem PowerShell-Cmdlet zu erhalten, geben Sie `Get-Help` gefolgt vom Namen des Cmdlets ein, z `Get-Help Get-Process` . b.:.</span><span class="sxs-lookup"><span data-stu-id="0dafc-114">To get help for a PowerShell cmdlet, type `Get-Help` followed by the cmdlet name, such as: `Get-Help Get-Process`.</span></span>

<span data-ttu-id="0dafc-115">Konzeptionelle Hilfeartikel in PowerShell beginnen mit **About_**, z. b. **about_Comparison_Operators**.</span><span class="sxs-lookup"><span data-stu-id="0dafc-115">Conceptual help articles in PowerShell begin with **about_**, such as **about_Comparison_Operators**.</span></span> <span data-ttu-id="0dafc-116">Wenn Sie alle **About_** Artikel anzeigen möchten, geben Sie ein `Get-Help about_*` .</span><span class="sxs-lookup"><span data-stu-id="0dafc-116">To see all **about_** articles, type `Get-Help about_*`.</span></span> <span data-ttu-id="0dafc-117">Um einen bestimmten Artikel anzuzeigen, geben Sie ein `Get-Help about_<article-name>` , z `Get-Help about_Comparison_Operators` . b..</span><span class="sxs-lookup"><span data-stu-id="0dafc-117">To see a particular article, type `Get-Help about_<article-name>`, such as `Get-Help about_Comparison_Operators`.</span></span>

<span data-ttu-id="0dafc-118">Um Hilfe zu einem PowerShell-Anbieter zu erhalten, geben Sie `Get-Help` gefolgt vom Anbieter Namen ein.</span><span class="sxs-lookup"><span data-stu-id="0dafc-118">To get help for a PowerShell provider, type `Get-Help` followed by the provider name.</span></span> <span data-ttu-id="0dafc-119">Wenn Sie z. b. Hilfe zum Zertifikat Anbieter benötigen, geben Sie ein `Get-Help Certificate` .</span><span class="sxs-lookup"><span data-stu-id="0dafc-119">For example, to get help for the Certificate provider, type `Get-Help Certificate`.</span></span>

<span data-ttu-id="0dafc-120">Sie können auch `help` oder eingeben `man` , das jeweils jeweils einen Bildschirm anzeigt.</span><span class="sxs-lookup"><span data-stu-id="0dafc-120">You can also type `help` or `man`, which displays one screen of text at a time.</span></span> <span data-ttu-id="0dafc-121">Oder, `<cmdlet-name> -?` das ist mit identisch `Get-Help` , funktioniert aber nur für Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="0dafc-121">Or, `<cmdlet-name> -?`, that is identical to `Get-Help`, but only works for cmdlets.</span></span>

<span data-ttu-id="0dafc-122">`Get-Help` Ruft den Hilfe Inhalt ab, der von Hilfedateien auf Ihrem Computer angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="0dafc-122">`Get-Help` gets the help content that it displays from help files on your computer.</span></span> <span data-ttu-id="0dafc-123">Ohne die Hilfedateien `Get-Help` zeigt nur grundlegende Informationen zu Cmdlets an.</span><span class="sxs-lookup"><span data-stu-id="0dafc-123">Without the help files, `Get-Help` displays only basic information about cmdlets.</span></span> <span data-ttu-id="0dafc-124">Einige PowerShell-Module enthalten Hilfedateien.</span><span class="sxs-lookup"><span data-stu-id="0dafc-124">Some PowerShell modules include help files.</span></span> <span data-ttu-id="0dafc-125">Ab PowerShell 3,0 enthalten die Module, die im Lieferumfang des Windows-Betriebssystems enthalten sind, keine Hilfedateien.</span><span class="sxs-lookup"><span data-stu-id="0dafc-125">Beginning in PowerShell 3.0, the modules that come with the Windows operating system don't include help files.</span></span> <span data-ttu-id="0dafc-126">Verwenden Sie das-Cmdlet, um die Hilfedateien für ein Modul in PowerShell 3,0 herunterzuladen oder zu aktualisieren `Update-Help` .</span><span class="sxs-lookup"><span data-stu-id="0dafc-126">To download or update the help files for a module in PowerShell 3.0, use the `Update-Help` cmdlet.</span></span>

<span data-ttu-id="0dafc-127">Sie können die PowerShell-Hilfedokumente auch online im Microsoft-Dokumentation anzeigen. Um die Online Version einer Hilfedatei zu erhalten, verwenden Sie den **Online-** Parameter, z `Get-Help Get-Process -Online` . b.:.</span><span class="sxs-lookup"><span data-stu-id="0dafc-127">You can also view the PowerShell help documents online in the Microsoft Docs. To get the online version of a help file, use the **Online** parameter, such as: `Get-Help Get-Process -Online`.</span></span> <span data-ttu-id="0dafc-128">Informationen zum Lesen der gesamten PowerShell-Dokumentation finden Sie in der Microsoft-Dokumentation [PowerShell-Dokumentation](/powershell).</span><span class="sxs-lookup"><span data-stu-id="0dafc-128">To read all the PowerShell documentation, see the Microsoft Docs [PowerShell Documentation](/powershell).</span></span>

<span data-ttu-id="0dafc-129">Wenn Sie eingeben `Get-Help` , gefolgt vom exakten Namen eines Hilfe Artikels oder durch ein Wort, das für einen Hilfeartikel eindeutig ist, `Get-Help` zeigt den Inhalt des Artikels an.</span><span class="sxs-lookup"><span data-stu-id="0dafc-129">If you type `Get-Help` followed by the exact name of a help article, or by a word unique to a help article, `Get-Help` displays the article's content.</span></span> <span data-ttu-id="0dafc-130">Wenn Sie den genauen Namen eines befehlsalias angeben, wird `Get-Help` die Hilfe für den ursprünglichen Befehl angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0dafc-130">If you specify the exact name of a command alias, `Get-Help` displays the help for the original command.</span></span> <span data-ttu-id="0dafc-131">Wenn Sie ein Word-oder Word-Muster eingeben, das in mehreren Hilfeartikel Titeln angezeigt wird, `Get-Help` zeigt eine Liste der übereinstimmenden Titel an.</span><span class="sxs-lookup"><span data-stu-id="0dafc-131">If you enter a word or word pattern that appears in several help article titles, `Get-Help` displays a list of the matching titles.</span></span> <span data-ttu-id="0dafc-132">Wenn Sie Text eingeben, der nicht in den Titeln von Hilfe Artikeln enthalten ist, wird `Get-Help` von eine Liste mit Artikeln angezeigt, die diesen Text im Inhalt enthalten.</span><span class="sxs-lookup"><span data-stu-id="0dafc-132">If you enter any text that doesn't appear in any help article titles, `Get-Help` displays a list of articles that include that text in their contents.</span></span>

<span data-ttu-id="0dafc-133">`Get-Help` kann Hilfeartikel für alle unterstützten Sprachen und Gebiets Schemas erhalten.</span><span class="sxs-lookup"><span data-stu-id="0dafc-133">`Get-Help` can get help articles for all supported languages and locales.</span></span> <span data-ttu-id="0dafc-134">`Get-Help` sucht zuerst nach Hilfedateien im Gebiets Schema, das für Windows festgelegt ist, und dann im übergeordneten Gebiets Schema, z. b. **PT** für **pt-br**, und dann in einem Fall Back Gebiets Schema.</span><span class="sxs-lookup"><span data-stu-id="0dafc-134">`Get-Help` first looks for help files in the locale set for Windows, then in the parent locale, such as **pt** for **pt-BR**, and then in a fallback locale.</span></span> <span data-ttu-id="0dafc-135">Wenn in PowerShell 3,0 `Get-Help` keine Hilfe im Fall Back Gebiets Schema gefunden wird, sucht es nach Hilfe Artikeln in englischer Sprache ( **en-US**), bevor eine Fehlermeldung zurückgegeben oder automatisch generierte Hilfe angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="0dafc-135">Beginning in PowerShell 3.0, if `Get-Help` doesn't find help in the fallback locale, it looks for help articles in English, **en-US**, before it returns an error message or displaying autogenerated help.</span></span>

<span data-ttu-id="0dafc-136">Informationen zu den Symbolen, die `Get-Help` im Befehlssyntax Diagramm angezeigt werden, finden Sie unter [about_Command_Syntax](./About/about_Command_Syntax.md).</span><span class="sxs-lookup"><span data-stu-id="0dafc-136">For information about the symbols that `Get-Help` displays in the command syntax diagram, see [about_Command_Syntax](./About/about_Command_Syntax.md).</span></span>
<span data-ttu-id="0dafc-137">Weitere Informationen zu Parameter Attributen, wie z. b. **Required** und **Position**, finden Sie unter [about_Parameters](./About/about_Parameters.md).</span><span class="sxs-lookup"><span data-stu-id="0dafc-137">For information about parameter attributes, such as **Required** and **Position**, see [about_Parameters](./About/about_Parameters.md).</span></span>

>[!NOTE]
> <span data-ttu-id="0dafc-138">In PowerShell 3,0 und PowerShell 4,0 `Get-Help` können Artikel nicht  in Modulen gefunden werden, es sei denn, das Modul wird in die aktuelle Sitzung importiert.</span><span class="sxs-lookup"><span data-stu-id="0dafc-138">In PowerShell 3.0 and PowerShell 4.0, `Get-Help` can't find **About** articles in modules unless the module is imported into the current session.</span></span> <span data-ttu-id="0dafc-139">Dies ist ein bekanntes Problem.</span><span class="sxs-lookup"><span data-stu-id="0dafc-139">This is a known issue.</span></span> <span data-ttu-id="0dafc-140">Um **Informationen über** Artikel in einem Modul zu erhalten, importieren Sie das Modul entweder mithilfe des- `Import-Module` Cmdlets oder durch Ausführen eines Cmdlets, das im Modul enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="0dafc-140">To get **About** articles in a module, import the module, either by using the `Import-Module` cmdlet or by running a cmdlet that's included in the module.</span></span>

## <span data-ttu-id="0dafc-141">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="0dafc-141">EXAMPLES</span></span>

### <span data-ttu-id="0dafc-142">Beispiel 1: Anzeigen grundlegender Hilfe Informationen zu einem Cmdlet</span><span class="sxs-lookup"><span data-stu-id="0dafc-142">Example 1: Display basic help information about a cmdlet</span></span>

<span data-ttu-id="0dafc-143">In diesen Beispielen werden grundlegende Hilfe Informationen zum `Format-Table` Cmdlet angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0dafc-143">These examples display basic help information about the `Format-Table` cmdlet.</span></span>

```powershell
Get-Help Format-Table
Get-Help -Name Format-Table
Format-Table -?
```

<span data-ttu-id="0dafc-144">`Get-Help <cmdlet-name>` ist die einfachste und standardmäßige Syntax des `Get-Help` Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="0dafc-144">`Get-Help <cmdlet-name>` is the simplest and default syntax of `Get-Help` cmdlet.</span></span> <span data-ttu-id="0dafc-145">Sie können den **Name** -Parameter weglassen.</span><span class="sxs-lookup"><span data-stu-id="0dafc-145">You can omit the **Name** parameter.</span></span>

<span data-ttu-id="0dafc-146">Die Syntax `<cmdlet-name> -?` funktioniert nur für Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="0dafc-146">The syntax `<cmdlet-name> -?` works only for cmdlets.</span></span>

### <span data-ttu-id="0dafc-147">Beispiel 2: Anzeigen von grundlegenden Informationen auf einer Seite</span><span class="sxs-lookup"><span data-stu-id="0dafc-147">Example 2: Display basic information one page at a time</span></span>

<span data-ttu-id="0dafc-148">In diesen Beispielen werden grundlegende Hilfe Informationen zum- `Format-Table` Cmdlet nacheinander angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0dafc-148">These examples display basic help information about the `Format-Table` cmdlet one page at a time.</span></span>

```powershell
help Format-Table
man Format-Table
Get-Help Format-Table | Out-Host -Paging
```

<span data-ttu-id="0dafc-149">`help` ist eine Funktion, die das `Get-Help` Cmdlet intern ausführt und das Ergebnis jeweils eine Seite anzeigt.</span><span class="sxs-lookup"><span data-stu-id="0dafc-149">`help` is a function that runs `Get-Help` cmdlet internally and displays the result one page at a time.</span></span>

<span data-ttu-id="0dafc-150">`man` ist ein Alias für die- `help` Funktion.</span><span class="sxs-lookup"><span data-stu-id="0dafc-150">`man` is an alias for the `help` function.</span></span>

<span data-ttu-id="0dafc-151">`Get-Help Format-Table` sendet das Objekt über die Pipeline.</span><span class="sxs-lookup"><span data-stu-id="0dafc-151">`Get-Help Format-Table` sends the object down the pipeline.</span></span> <span data-ttu-id="0dafc-152">`Out-Host -Paging` empfängt die Ausgabe der Pipeline und zeigt Sie jeweils auf einer Seite an.</span><span class="sxs-lookup"><span data-stu-id="0dafc-152">`Out-Host -Paging` receives the output from the pipeline and displays it one page at a time.</span></span> <span data-ttu-id="0dafc-153">Weitere Informationen finden Sie unter [Out-Host](Out-Host.md).</span><span class="sxs-lookup"><span data-stu-id="0dafc-153">For more information, see [Out-Host](Out-Host.md).</span></span>

### <span data-ttu-id="0dafc-154">Beispiel 3: Anzeigen von weiteren Informationen zu einem Cmdlet</span><span class="sxs-lookup"><span data-stu-id="0dafc-154">Example 3: Display more information for a cmdlet</span></span>

<span data-ttu-id="0dafc-155">In diesen Beispielen werden ausführlichere Hilfe Informationen zum `Format-Table` Cmdlet angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0dafc-155">These examples display more detailed help information about the `Format-Table` cmdlet.</span></span>

```powershell
Get-Help Format-Table -Detailed
Get-Help Format-Table -Full
```

<span data-ttu-id="0dafc-156">Der **ausführliche** Parameter zeigt die ausführliche Ansicht des Hilfe Artikels an, die Parameter Beschreibungen und Beispiele enthält.</span><span class="sxs-lookup"><span data-stu-id="0dafc-156">The **Detailed** parameter displays the help article's detailed view that includes parameter descriptions and examples.</span></span>

<span data-ttu-id="0dafc-157">Der **vollständige** Parameter zeigt die vollständige Ansicht des Hilfe Artikels an, die Parameter Beschreibungen, Beispiele, Eingabe-und Ausgabe Objekttypen sowie weitere Hinweise enthält.</span><span class="sxs-lookup"><span data-stu-id="0dafc-157">The **Full** parameter displays the help article's full view that includes parameter descriptions, examples, input and output object types, and additional notes.</span></span>

<span data-ttu-id="0dafc-158">Die **detaillierten** und **vollständigen** Parameter sind nur für die Befehle wirksam, bei denen Hilfedateien auf dem Computer installiert sind.</span><span class="sxs-lookup"><span data-stu-id="0dafc-158">The **Detailed** and **Full** parameters are effective only for the commands that have help files installed on the computer.</span></span> <span data-ttu-id="0dafc-159">Die Parameter sind für die konzeptionellen Hilfeartikel (**About_**) nicht wirksam.</span><span class="sxs-lookup"><span data-stu-id="0dafc-159">The parameters aren't effective for the conceptual (**about_**) help articles.</span></span>

### <span data-ttu-id="0dafc-160">Beispiel 4: Anzeigen ausgewählter Teile eines Cmdlets mithilfe von Parametern</span><span class="sxs-lookup"><span data-stu-id="0dafc-160">Example 4: Display selected parts of a cmdlet by using parameters</span></span>

<span data-ttu-id="0dafc-161">In diesen Beispielen werden ausgewählte Teile der `Format-Table` Cmdlet-Hilfe angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0dafc-161">These examples display selected portions of the `Format-Table` cmdlet help.</span></span>

```powershell
Get-Help Format-Table -Examples
Get-Help Format-Table -Parameter *
Get-Help Format-Table -Parameter GroupBy
```

<span data-ttu-id="0dafc-162">Der Parameter " **examples** " zeigt den **Namen** und die **Synopsis** -Abschnitte der Hilfedatei sowie alle Beispiele an.</span><span class="sxs-lookup"><span data-stu-id="0dafc-162">The **Examples** parameter displays the help file's **NAME** and **SYNOPSIS** sections, and all the Examples.</span></span> <span data-ttu-id="0dafc-163">Sie können keine Beispiel Zahl angeben, da der **examples** -Parameter ein Switch-Parameter ist.</span><span class="sxs-lookup"><span data-stu-id="0dafc-163">You can't specify an Example number because the **Examples** parameter is a switch parameter.</span></span>

<span data-ttu-id="0dafc-164">Der **Parameter** Parameter zeigt nur die Beschreibungen der angegebenen Parameter an.</span><span class="sxs-lookup"><span data-stu-id="0dafc-164">The **Parameter** parameter displays only the descriptions of the specified parameters.</span></span> <span data-ttu-id="0dafc-165">Wenn Sie nur das Sternchen ()-Platzhalter `*` Zeichen angeben, werden die Beschreibungen aller Parameter angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0dafc-165">If you specify only the asterisk (`*`) wildcard character, it displays the descriptions of all parameters.</span></span>
<span data-ttu-id="0dafc-166">Wenn **Parameter** einen Parameternamen (z. b. **GroupBy**) angibt, werden Informationen zu diesem Parameter angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0dafc-166">When **Parameter** specifies a parameter name such as **GroupBy**, information about that parameter is shown.</span></span>

<span data-ttu-id="0dafc-167">Diese Parameter sind für die konzeptionellen Hilfeartikel (**About_**) nicht wirksam.</span><span class="sxs-lookup"><span data-stu-id="0dafc-167">These parameters aren't effective for the conceptual (**about_**) help articles.</span></span>

### <span data-ttu-id="0dafc-168">Beispiel 5: Anzeigen der Online Version der Hilfe</span><span class="sxs-lookup"><span data-stu-id="0dafc-168">Example 5: Display online version of help</span></span>

<span data-ttu-id="0dafc-169">In diesem Beispiel wird die Online Version des Hilfe Artikels für das `Format-Table` Cmdlet in Ihrem Standard Webbrowser angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0dafc-169">This example displays the online version of the help article for the `Format-Table` cmdlet in your default web browser.</span></span>

```powershell
Get-Help Format-Table -Online
```

### <span data-ttu-id="0dafc-170">Beispiel 6: Anzeigen der Hilfe zum Hilfesystem</span><span class="sxs-lookup"><span data-stu-id="0dafc-170">Example 6: Display help about the help system</span></span>

<span data-ttu-id="0dafc-171">Das- `Get-Help` Cmdlet ohne Parameter zeigt Informationen zum PowerShell-Hilfesystem an.</span><span class="sxs-lookup"><span data-stu-id="0dafc-171">The `Get-Help` cmdlet without parameters displays information about the PowerShell help system.</span></span>

```powershell
Get-Help
```

### <span data-ttu-id="0dafc-172">Beispiel 7: Anzeigen der verfügbaren Hilfeartikel</span><span class="sxs-lookup"><span data-stu-id="0dafc-172">Example 7: Display available help articles</span></span>

<span data-ttu-id="0dafc-173">In diesem Beispiel wird eine Liste aller Hilfeartikel angezeigt, die auf Ihrem Computer verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="0dafc-173">This example displays a list of all help articles available on your computer.</span></span>

```powershell
Get-Help *
```

### <span data-ttu-id="0dafc-174">Beispiel 8: Anzeigen einer Liste von konzeptionellen Artikeln</span><span class="sxs-lookup"><span data-stu-id="0dafc-174">Example 8: Display a list of conceptual articles</span></span>

<span data-ttu-id="0dafc-175">In diesem Beispiel wird eine Liste mit den konzeptionellen Artikeln angezeigt, die in der PowerShell-Hilfe enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="0dafc-175">This example displays a list of the conceptual articles included in PowerShell help.</span></span> <span data-ttu-id="0dafc-176">Alle diese Artikel beginnen mit den Zeichen **About_**.</span><span class="sxs-lookup"><span data-stu-id="0dafc-176">All these articles begin with the characters **about_**.</span></span> <span data-ttu-id="0dafc-177">Zum Anzeigen einer bestimmten Hilfedatei geben Sie `Get-Help \<about_article-name\>` z `Get-Help about_Signing` . b. ein.</span><span class="sxs-lookup"><span data-stu-id="0dafc-177">To display a particular help file, type `Get-Help \<about_article-name\>`, for example, `Get-Help about_Signing`.</span></span>

<span data-ttu-id="0dafc-178">Nur die konzeptionellen Artikel, in denen Hilfedateien auf Ihrem Computer installiert sind, werden angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0dafc-178">Only the conceptual articles that have help files installed on your computer are displayed.</span></span> <span data-ttu-id="0dafc-179">Informationen zum herunterladen und Installieren von Hilfedateien in PowerShell 3,0 finden Sie unter [Update-Help](Update-Help.md).</span><span class="sxs-lookup"><span data-stu-id="0dafc-179">For information about downloading and installing help files in PowerShell 3.0, see [Update-Help](Update-Help.md).</span></span>

```powershell
Get-Help about_*
```

### <span data-ttu-id="0dafc-180">Beispiel 9: Suchen nach einem Wort in der Cmdlet-Hilfe</span><span class="sxs-lookup"><span data-stu-id="0dafc-180">Example 9: Search for a word in cmdlet help</span></span>

<span data-ttu-id="0dafc-181">Dieses Beispiel zeigt, wie Sie in einem Cmdlet-Hilfeartikel nach einem Wort suchen.</span><span class="sxs-lookup"><span data-stu-id="0dafc-181">This example shows how to search for a word in a cmdlet help article.</span></span>

```powershell
Get-Help Add-Member -Full | Out-String -Stream | Select-String -Pattern Clixml
```

```Output
the Export-Clixml cmdlet to save the instance of the object, including the additional members...
can use the Import-Clixml cmdlet to re-create the instance of the object from the information...
Export-Clixml
Import-Clixml
```

<span data-ttu-id="0dafc-182">`Get-Help` verwendet den **Full** -Parameter, um Hilfe Informationen für zu erhalten `Add-Member` .</span><span class="sxs-lookup"><span data-stu-id="0dafc-182">`Get-Help` uses the **Full** parameter to get help information for `Add-Member`.</span></span> <span data-ttu-id="0dafc-183">Das **mamlcommandhelpinfo** -Objekt wird über die Pipeline gesendet.</span><span class="sxs-lookup"><span data-stu-id="0dafc-183">The **MamlCommandHelpInfo** object is sent down the pipeline.</span></span> <span data-ttu-id="0dafc-184">`Out-String` verwendet den **Stream** -Parameter, um das Objekt in eine Zeichenfolge zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="0dafc-184">`Out-String` uses the **Stream** parameter to convert the object into a string.</span></span> <span data-ttu-id="0dafc-185">`Select-String` verwendet den **Pattern** -Parameter, um die Zeichenfolge nach **CliXML** zu durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="0dafc-185">`Select-String` uses the **Pattern** parameter to search the string for **Clixml**.</span></span>

### <span data-ttu-id="0dafc-186">Beispiel 10: Anzeigen einer Liste von Artikeln, die ein Wort enthalten</span><span class="sxs-lookup"><span data-stu-id="0dafc-186">Example 10: Display a list of articles that include a word</span></span>

<span data-ttu-id="0dafc-187">In diesem Beispiel wird eine Liste von Artikeln angezeigt, die das Wort **Remoting** enthalten.</span><span class="sxs-lookup"><span data-stu-id="0dafc-187">This example displays a list of articles that include the word **remoting**.</span></span>

<span data-ttu-id="0dafc-188">Wenn Sie ein Wort eingeben, das in keinem Artikel Titel enthalten ist, wird `Get-Help` eine Liste mit Artikeln angezeigt, die dieses Wort enthalten.</span><span class="sxs-lookup"><span data-stu-id="0dafc-188">When you enter a word that doesn't appear in any article title, `Get-Help` displays a list of articles that include that word.</span></span>

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

### <span data-ttu-id="0dafc-189">Beispiel 11: Anzeige Anbieter spezifischer Hilfe</span><span class="sxs-lookup"><span data-stu-id="0dafc-189">Example 11: Display provider-specific help</span></span>

<span data-ttu-id="0dafc-190">Dieses Beispiel zeigt zwei Möglichkeiten, die anbieterspezifische Hilfe für zu erhalten `Get-Item` .</span><span class="sxs-lookup"><span data-stu-id="0dafc-190">This example shows two ways of getting the provider-specific help for `Get-Item`.</span></span> <span data-ttu-id="0dafc-191">Diese Befehle erhalten Hilfe, in der erläutert wird, wie das `Get-Item` Cmdlet im **DataCollection** -Knoten des PowerShell-SQL Server Anbieters verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="0dafc-191">These commands get help that explains how to use the `Get-Item` cmdlet in the PowerShell SQL Server provider's **DataCollection** node.</span></span>

<span data-ttu-id="0dafc-192">Im ersten Beispiel wird der `Get-Help` **path** -Parameter verwendet, um den Pfad des SQL Server Anbieters anzugeben.</span><span class="sxs-lookup"><span data-stu-id="0dafc-192">The first example uses the `Get-Help` **Path** parameter to specify the SQL Server provider's path.</span></span>
<span data-ttu-id="0dafc-193">Da der Pfad des Anbieters angegeben ist, können Sie den Befehl von einem beliebigen Pfad Speicherort aus ausführen.</span><span class="sxs-lookup"><span data-stu-id="0dafc-193">Because the provider's path is specified, you can run the command from any path location.</span></span>

<span data-ttu-id="0dafc-194">Im zweiten Beispiel wird verwendet `Set-Location` , um zum Pfad des SQL Server Anbieters zu navigieren.</span><span class="sxs-lookup"><span data-stu-id="0dafc-194">The second example uses `Set-Location` to navigate to the SQL Server provider's path.</span></span> <span data-ttu-id="0dafc-195">An diesem Speicherort wird der **path** -Parameter nicht benötigt, um `Get-Help` die anbieterspezifische Hilfe zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="0dafc-195">From that location, the **Path** parameter isn't needed for `Get-Help` to get the provider-specific help.</span></span>

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

### <span data-ttu-id="0dafc-196">Beispiel 12: Anzeigen der Hilfe für ein Skript</span><span class="sxs-lookup"><span data-stu-id="0dafc-196">Example 12: Display help for a script</span></span>

<span data-ttu-id="0dafc-197">In diesem Beispiel wird die Hilfe für das abgerufen `MyScript.ps1 script` .</span><span class="sxs-lookup"><span data-stu-id="0dafc-197">This example gets help for the `MyScript.ps1 script`.</span></span> <span data-ttu-id="0dafc-198">Informationen zum Schreiben von Hilfe für ihre Funktionen und Skripts finden Sie unter [about_Comment_Based_Help](./About/about_Comment_Based_Help.md).</span><span class="sxs-lookup"><span data-stu-id="0dafc-198">For information about how to write help for your functions and scripts, see [about_Comment_Based_Help](./About/about_Comment_Based_Help.md).</span></span>

```powershell
Get-Help -Name C:\PS-Test\MyScript.ps1
```

## <span data-ttu-id="0dafc-199">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="0dafc-199">PARAMETERS</span></span>

### <span data-ttu-id="0dafc-200">-Kategorie</span><span class="sxs-lookup"><span data-stu-id="0dafc-200">-Category</span></span>

<span data-ttu-id="0dafc-201">Zeigt nur für Elemente in der angegebenen Kategorie und ihre Aliase Hilfe an.</span><span class="sxs-lookup"><span data-stu-id="0dafc-201">Displays help only for items in the specified category and their aliases.</span></span> <span data-ttu-id="0dafc-202">Konzeptionelle Artikel befinden sich in der Kategorie **HelpFile** .</span><span class="sxs-lookup"><span data-stu-id="0dafc-202">Conceptual articles are in the **HelpFile** category.</span></span>

<span data-ttu-id="0dafc-203">Die zulässigen Werte für diesen Parameter lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="0dafc-203">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="0dafc-204">Alias</span><span class="sxs-lookup"><span data-stu-id="0dafc-204">Alias</span></span>
- <span data-ttu-id="0dafc-205">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="0dafc-205">Cmdlet</span></span>
- <span data-ttu-id="0dafc-206">Anbieter</span><span class="sxs-lookup"><span data-stu-id="0dafc-206">Provider</span></span>
- <span data-ttu-id="0dafc-207">Allgemein</span><span class="sxs-lookup"><span data-stu-id="0dafc-207">General</span></span>
- <span data-ttu-id="0dafc-208">Häufig gestellte Fragen</span><span class="sxs-lookup"><span data-stu-id="0dafc-208">FAQ</span></span>
- <span data-ttu-id="0dafc-209">Glossar</span><span class="sxs-lookup"><span data-stu-id="0dafc-209">Glossary</span></span>
- <span data-ttu-id="0dafc-210">HelpFile</span><span class="sxs-lookup"><span data-stu-id="0dafc-210">HelpFile</span></span>
- <span data-ttu-id="0dafc-211">ScriptCommand</span><span class="sxs-lookup"><span data-stu-id="0dafc-211">ScriptCommand</span></span>
- <span data-ttu-id="0dafc-212">Funktion</span><span class="sxs-lookup"><span data-stu-id="0dafc-212">Function</span></span>
- <span data-ttu-id="0dafc-213">Filter</span><span class="sxs-lookup"><span data-stu-id="0dafc-213">Filter</span></span>
- <span data-ttu-id="0dafc-214">Externalscript</span><span class="sxs-lookup"><span data-stu-id="0dafc-214">ExternalScript</span></span>
- <span data-ttu-id="0dafc-215">Alle</span><span class="sxs-lookup"><span data-stu-id="0dafc-215">All</span></span>
- <span data-ttu-id="0dafc-216">Defaulthelp</span><span class="sxs-lookup"><span data-stu-id="0dafc-216">DefaultHelp</span></span>
- <span data-ttu-id="0dafc-217">Workflow</span><span class="sxs-lookup"><span data-stu-id="0dafc-217">Workflow</span></span>
- <span data-ttu-id="0dafc-218">DscResource</span><span class="sxs-lookup"><span data-stu-id="0dafc-218">DscResource</span></span>
- <span data-ttu-id="0dafc-219">Class</span><span class="sxs-lookup"><span data-stu-id="0dafc-219">Class</span></span>
- <span data-ttu-id="0dafc-220">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="0dafc-220">Configuration</span></span>

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

### <span data-ttu-id="0dafc-221">-Komponente</span><span class="sxs-lookup"><span data-stu-id="0dafc-221">-Component</span></span>

<span data-ttu-id="0dafc-222">Zeigt Befehle mit dem angegebenen Komponenten Wert an, z. b. **Exchange**.</span><span class="sxs-lookup"><span data-stu-id="0dafc-222">Displays commands with the specified component value, such as **Exchange**.</span></span> <span data-ttu-id="0dafc-223">Geben Sie einen Komponentennamen ein.</span><span class="sxs-lookup"><span data-stu-id="0dafc-223">Enter a component name.</span></span>
<span data-ttu-id="0dafc-224">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="0dafc-224">Wildcard characters are permitted.</span></span> <span data-ttu-id="0dafc-225">Dieser Parameter hat keine Auswirkung auf die Anzeige der konzeptionellen Hilfe (**About_**).</span><span class="sxs-lookup"><span data-stu-id="0dafc-225">This parameter has no effect on displays of conceptual (**About_**) help.</span></span>

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

### <span data-ttu-id="0dafc-226">-Detailed</span><span class="sxs-lookup"><span data-stu-id="0dafc-226">-Detailed</span></span>

<span data-ttu-id="0dafc-227">Fügt der Anzeige der grundlegende Hilfe Parameterbeschreibungen und Beispiele hinzu.</span><span class="sxs-lookup"><span data-stu-id="0dafc-227">Adds parameter descriptions and examples to the basic help display.</span></span> <span data-ttu-id="0dafc-228">Dieser Parameter ist nur wirksam, wenn die Hilfedateien auf dem Computer installiert sind.</span><span class="sxs-lookup"><span data-stu-id="0dafc-228">This parameter is effective only when the help files are installed on the computer.</span></span> <span data-ttu-id="0dafc-229">Dies hat keine Auswirkung auf die Anzeige der konzeptionellen Hilfe (**About_**).</span><span class="sxs-lookup"><span data-stu-id="0dafc-229">It has no effect on displays of conceptual (**About_**) help.</span></span>

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

### <span data-ttu-id="0dafc-230">-Examples</span><span class="sxs-lookup"><span data-stu-id="0dafc-230">-Examples</span></span>

<span data-ttu-id="0dafc-231">Zeigt nur den Namen, die Zusammenfassung und Beispiele an.</span><span class="sxs-lookup"><span data-stu-id="0dafc-231">Displays only the name, synopsis, and examples.</span></span> <span data-ttu-id="0dafc-232">Geben Sie ein, um nur die Beispiele anzuzeigen `(Get-Help \<cmdlet-name\>).Examples` .</span><span class="sxs-lookup"><span data-stu-id="0dafc-232">To display only the examples, type `(Get-Help \<cmdlet-name\>).Examples`.</span></span>

<span data-ttu-id="0dafc-233">Dieser Parameter ist nur wirksam, wenn die Hilfedateien auf dem Computer installiert sind.</span><span class="sxs-lookup"><span data-stu-id="0dafc-233">This parameter is effective only when the help files are installed on the computer.</span></span> <span data-ttu-id="0dafc-234">Dies hat keine Auswirkung auf die Anzeige der konzeptionellen Hilfe (**About_**).</span><span class="sxs-lookup"><span data-stu-id="0dafc-234">It has no effect on displays of conceptual (**About_**) help.</span></span>

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

### <span data-ttu-id="0dafc-235">-Full</span><span class="sxs-lookup"><span data-stu-id="0dafc-235">-Full</span></span>

<span data-ttu-id="0dafc-236">Zeigt den gesamten Hilfeartikel für ein Cmdlet an.</span><span class="sxs-lookup"><span data-stu-id="0dafc-236">Displays the entire help article for a cmdlet.</span></span> <span data-ttu-id="0dafc-237">**Vollständig** umfasst Parameter Beschreibungen und-Attribute, Beispiele, Eingabe-und Ausgabe Objekttypen sowie weitere Hinweise.</span><span class="sxs-lookup"><span data-stu-id="0dafc-237">**Full** includes parameter descriptions and attributes, examples, input and output object types, and additional notes.</span></span>

<span data-ttu-id="0dafc-238">Dieser Parameter ist nur wirksam, wenn die Hilfedateien auf dem Computer installiert sind.</span><span class="sxs-lookup"><span data-stu-id="0dafc-238">This parameter is effective only when the help files are installed on the computer.</span></span> <span data-ttu-id="0dafc-239">Dies hat keine Auswirkung auf die Anzeige der konzeptionellen Hilfe (**About_**).</span><span class="sxs-lookup"><span data-stu-id="0dafc-239">It has no effect on displays of conceptual (**About_**) help.</span></span>

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

### <span data-ttu-id="0dafc-240">-Funktionalität</span><span class="sxs-lookup"><span data-stu-id="0dafc-240">-Functionality</span></span>

<span data-ttu-id="0dafc-241">Zeigt Hilfe für Elemente mit der angegebenen Funktionalität an.</span><span class="sxs-lookup"><span data-stu-id="0dafc-241">Displays help for items with the specified functionality.</span></span> <span data-ttu-id="0dafc-242">Geben Sie die Funktionalität ein.</span><span class="sxs-lookup"><span data-stu-id="0dafc-242">Enter the functionality.</span></span> <span data-ttu-id="0dafc-243">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="0dafc-243">Wildcard characters are permitted.</span></span> <span data-ttu-id="0dafc-244">Dieser Parameter hat keine Auswirkung auf die Anzeige der konzeptionellen Hilfe (**About_**).</span><span class="sxs-lookup"><span data-stu-id="0dafc-244">This parameter has no effect on displays of conceptual (**About_**) help.</span></span>

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

### <span data-ttu-id="0dafc-245">-Name</span><span class="sxs-lookup"><span data-stu-id="0dafc-245">-Name</span></span>

<span data-ttu-id="0dafc-246">Ruft Hilfe zum angegebenen Befehl oder Konzept ab.</span><span class="sxs-lookup"><span data-stu-id="0dafc-246">Gets help about the specified command or concept.</span></span> <span data-ttu-id="0dafc-247">Geben Sie den Namen eines Cmdlets, einer Funktion, eines Anbieters, eines Skripts oder eines Workflows ein, z `Get-Member` . b. einen konzeptionellen Artikelnamen, z `about_Objects` . b. oder einen Alias, z `ls` . b..</span><span class="sxs-lookup"><span data-stu-id="0dafc-247">Enter the name of a cmdlet, function, provider, script, or workflow, such as `Get-Member`, a conceptual article name, such as `about_Objects`, or an alias, such as `ls`.</span></span> <span data-ttu-id="0dafc-248">Platzhalter Zeichen sind in Cmdlet-und Anbieter Namen zulässig, Sie können jedoch keine Platzhalter Zeichen verwenden, um die Namen der Hilfe-und Skript Hilfeartikel zu finden.</span><span class="sxs-lookup"><span data-stu-id="0dafc-248">Wildcard characters are permitted in cmdlet and provider names, but you can't use wildcard characters to find the names of function help and script help articles.</span></span>

<span data-ttu-id="0dafc-249">Um Hilfe für ein Skript zu erhalten, das sich nicht in einem Pfad befindet, der in der `$env:Path` Umgebungsvariablen aufgelistet ist, geben Sie den Pfad und den Dateinamen des Skripts ein.</span><span class="sxs-lookup"><span data-stu-id="0dafc-249">To get help for a script that isn't located in a path that's listed in the `$env:Path` environment variable, type the script's path and file name.</span></span>

<span data-ttu-id="0dafc-250">Wenn Sie den genauen Namen eines Hilfe Artikels eingeben, wird `Get-Help` der Artikel Inhalt von angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0dafc-250">If you enter the exact name of a help article, `Get-Help` displays the article contents.</span></span>

<span data-ttu-id="0dafc-251">Wenn Sie ein Word-oder Word-Muster eingeben, das in mehreren Hilfeartikel Titeln angezeigt wird, `Get-Help` zeigt eine Liste der übereinstimmenden Titel an.</span><span class="sxs-lookup"><span data-stu-id="0dafc-251">If you enter a word or word pattern that appears in several help article titles, `Get-Help` displays a list of the matching titles.</span></span>

<span data-ttu-id="0dafc-252">Wenn Sie Text eingeben, der mit keinem der Hilfeartikel Titel identisch ist, wird `Get-Help` eine Liste von Artikeln angezeigt, die diesen Text im Inhalt enthalten.</span><span class="sxs-lookup"><span data-stu-id="0dafc-252">If you enter any text that doesn't match any help article titles, `Get-Help` displays a list of articles that include that text in their contents.</span></span>

<span data-ttu-id="0dafc-253">Die Namen von konzeptionellen Artikeln (z `about_Objects` . b.) müssen in englischer Sprache eingegeben werden, auch in nicht englischsprachigen Versionen von PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0dafc-253">The names of conceptual articles, such as `about_Objects`, must be entered in English, even in non-English versions of PowerShell.</span></span>

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

### <span data-ttu-id="0dafc-254">-Online</span><span class="sxs-lookup"><span data-stu-id="0dafc-254">-Online</span></span>

<span data-ttu-id="0dafc-255">Zeigt die Online Version eines Hilfe Artikels im Standardbrowser an.</span><span class="sxs-lookup"><span data-stu-id="0dafc-255">Displays the online version of a help article in the default browser.</span></span> <span data-ttu-id="0dafc-256">Dieser Parameter ist nur für Cmdlet-, Function-, Workflow-und Skript-Hilfeartikel gültig.</span><span class="sxs-lookup"><span data-stu-id="0dafc-256">This parameter is valid only for cmdlet, function, workflow, and script help articles.</span></span> <span data-ttu-id="0dafc-257">Der **Online-** Parameter kann nicht mit `Get-Help` in einer Remote Sitzung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0dafc-257">You can't use the **Online** parameter with `Get-Help` in a remote session.</span></span>

<span data-ttu-id="0dafc-258">Weitere Informationen zur Unterstützung dieser Funktion in Hilfe Artikeln, die Sie schreiben, finden Sie unter [about_Comment_Based_Help](./About/about_Comment_Based_Help.md)und [unterstützen der Online Hilfe](/powershell/scripting/developer/module/supporting-online-help)und [Schreiben der Hilfe für PowerShell-Cmdlets](/powershell/scripting/developer/help/writing-help-for-windows-powershell-cmdlets).</span><span class="sxs-lookup"><span data-stu-id="0dafc-258">For information about supporting this feature in help articles that you write, see [about_Comment_Based_Help](./About/about_Comment_Based_Help.md), and [Supporting Online Help](/powershell/scripting/developer/module/supporting-online-help), and [Writing Help for PowerShell Cmdlets](/powershell/scripting/developer/help/writing-help-for-windows-powershell-cmdlets).</span></span>

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

### <span data-ttu-id="0dafc-259">-Parameter</span><span class="sxs-lookup"><span data-stu-id="0dafc-259">-Parameter</span></span>

<span data-ttu-id="0dafc-260">Zeigt nur die ausführlichen Beschreibungen der angegebenen Parameter an.</span><span class="sxs-lookup"><span data-stu-id="0dafc-260">Displays only the detailed descriptions of the specified parameters.</span></span> <span data-ttu-id="0dafc-261">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="0dafc-261">Wildcards are permitted.</span></span> <span data-ttu-id="0dafc-262">Dieser Parameter hat keine Auswirkung auf die Anzeige der konzeptionellen Hilfe (**About_**).</span><span class="sxs-lookup"><span data-stu-id="0dafc-262">This parameter has no effect on displays of conceptual (**About_**) help.</span></span>

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

### <span data-ttu-id="0dafc-263">-Path</span><span class="sxs-lookup"><span data-stu-id="0dafc-263">-Path</span></span>

<span data-ttu-id="0dafc-264">Ruft Hilfe ab, die die Funktionsweise des Cmdlets im angegebenen Anbieterpfad erläutert.</span><span class="sxs-lookup"><span data-stu-id="0dafc-264">Gets help that explains how the cmdlet works in the specified provider path.</span></span> <span data-ttu-id="0dafc-265">Geben Sie einen PowerShell-Anbieter Pfad ein.</span><span class="sxs-lookup"><span data-stu-id="0dafc-265">Enter a PowerShell provider path.</span></span>

<span data-ttu-id="0dafc-266">Dieser Parameter ruft eine angepasste Version eines Cmdlet-Hilfe Artikels ab, in der erläutert wird, wie das Cmdlet im angegebenen PowerShell-Anbieter Pfad funktioniert.</span><span class="sxs-lookup"><span data-stu-id="0dafc-266">This parameter gets a customized version of a cmdlet help article that explains how the cmdlet works in the specified PowerShell provider path.</span></span> <span data-ttu-id="0dafc-267">Dieser Parameter ist nur für Hilfe zu einem Anbieter-Cmdlet und nur dann gültig, wenn der Anbieter eine benutzerdefinierte Version des Hilfe Artikels des Provider-Cmdlets in der Hilfedatei enthält.</span><span class="sxs-lookup"><span data-stu-id="0dafc-267">This parameter is effective only for help about a provider cmdlet and only when the provider includes a custom version of the provider cmdlet help article in its help file.</span></span> <span data-ttu-id="0dafc-268">Um diesen Parameter zu verwenden, installieren Sie die Hilfedatei für das Modul, das den Anbieter enthält.</span><span class="sxs-lookup"><span data-stu-id="0dafc-268">To use this parameter, install the help file for the module that includes the provider.</span></span>

<span data-ttu-id="0dafc-269">Um die Hilfe zum benutzerdefinierten Cmdlet für einen Anbieter Pfad anzuzeigen, wechseln Sie zum Speicherort des Anbieter Pfads, und geben Sie einen Befehl ein, `Get-Help` oder verwenden Sie aus einem beliebigen Pfad den **Pfad** Parameter von, `Get-Help` um den Anbieter Pfad anzugeben.</span><span class="sxs-lookup"><span data-stu-id="0dafc-269">To see the custom cmdlet help for a provider path, go to the provider path location and enter a `Get-Help` command or, from any path location, use the **Path** parameter of `Get-Help` to specify the provider path.</span></span> <span data-ttu-id="0dafc-270">Die benutzerdefinierte Cmdlet-Hilfe finden Sie auch online im Abschnitt Anbieter Hilfe der Hilfeartikel.</span><span class="sxs-lookup"><span data-stu-id="0dafc-270">You can also find custom cmdlet help online in the provider help section of the help articles.</span></span>

<span data-ttu-id="0dafc-271">Weitere Informationen zu PowerShell-Anbietern finden Sie unter [about_Providers](./About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="0dafc-271">For more information about PowerShell providers, see [about_Providers](./About/about_Providers.md).</span></span>

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

### <span data-ttu-id="0dafc-272">-Rolle</span><span class="sxs-lookup"><span data-stu-id="0dafc-272">-Role</span></span>

<span data-ttu-id="0dafc-273">Zeigt Hilfe an, die für die angegebene Benutzerrolle angepasst wurde.</span><span class="sxs-lookup"><span data-stu-id="0dafc-273">Displays help customized for the specified user role.</span></span> <span data-ttu-id="0dafc-274">Geben Sie eine Rolle ein.</span><span class="sxs-lookup"><span data-stu-id="0dafc-274">Enter a role.</span></span> <span data-ttu-id="0dafc-275">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="0dafc-275">Wildcard characters are permitted.</span></span>

<span data-ttu-id="0dafc-276">Geben Sie die Rolle ein, die der Benutzer in einer Organisation inne hat.</span><span class="sxs-lookup"><span data-stu-id="0dafc-276">Enter the role that the user plays in an organization.</span></span> <span data-ttu-id="0dafc-277">Einige Cmdlets zeigen basierend auf dem Wert dieses Parameters unterschiedlichen Text in ihren Hilfedateien an.</span><span class="sxs-lookup"><span data-stu-id="0dafc-277">Some cmdlets display different text in their help files based on the value of this parameter.</span></span> <span data-ttu-id="0dafc-278">Dieser Parameter hat keine Auswirkungen auf die Hilfe für die Haupt-Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="0dafc-278">This parameter has no effect on help for the core cmdlets.</span></span>

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

### <span data-ttu-id="0dafc-279">-ShowWindow</span><span class="sxs-lookup"><span data-stu-id="0dafc-279">-ShowWindow</span></span>

<span data-ttu-id="0dafc-280">Zeigt das Hilfethema zur besseren Lesbarkeit in einem Fenster an.</span><span class="sxs-lookup"><span data-stu-id="0dafc-280">Displays the help topic in a window for easier reading.</span></span> <span data-ttu-id="0dafc-281">Das Fenster enthält eine **Suchfunktion suchen und** ein **Einstellungs** Feld, mit dem Sie Optionen für die Anzeige festlegen können, einschließlich Optionen, um nur ausgewählte Abschnitte eines Hilfe Themas anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="0dafc-281">The window includes a **Find** search feature and a **Settings** box that lets you set options for the display, including options to display only selected sections of a help topic.</span></span>

<span data-ttu-id="0dafc-282">Der **ShowWindow** -Parameter unterstützt Hilfe Themen für Befehle (Cmdlets, Funktionen, CIM-Befehle, Skripts) und konzeptionelle **Informationen zu** Artikeln.</span><span class="sxs-lookup"><span data-stu-id="0dafc-282">The **ShowWindow** parameter supports help topics for commands (cmdlets, functions, CIM commands, scripts) and conceptual **About** articles.</span></span> <span data-ttu-id="0dafc-283">Die Anbieterhilfe wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="0dafc-283">It does not support provider help.</span></span>

<span data-ttu-id="0dafc-284">Dieser Parameter wurde in PowerShell 7,0 erneut eingeführt.</span><span class="sxs-lookup"><span data-stu-id="0dafc-284">This parameter was reintroduced in PowerShell 7.0.</span></span>

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

### <span data-ttu-id="0dafc-285">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="0dafc-285">CommonParameters</span></span>

<span data-ttu-id="0dafc-286">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="0dafc-286">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="0dafc-287">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="0dafc-287">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="0dafc-288">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="0dafc-288">INPUTS</span></span>

### <span data-ttu-id="0dafc-289">Keine</span><span class="sxs-lookup"><span data-stu-id="0dafc-289">None</span></span>

<span data-ttu-id="0dafc-290">Objekte können nicht über die Pipeline an gesendet werden `Get-Help` .</span><span class="sxs-lookup"><span data-stu-id="0dafc-290">You can't send objects down the pipeline to `Get-Help`.</span></span>

## <span data-ttu-id="0dafc-291">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="0dafc-291">OUTPUTS</span></span>

### <span data-ttu-id="0dafc-292">Extendedcmdlethelpinfo</span><span class="sxs-lookup"><span data-stu-id="0dafc-292">ExtendedCmdletHelpInfo</span></span>

<span data-ttu-id="0dafc-293">Wenn Sie `Get-Help` mit einem Befehl ausführen, der keine Hilfedatei enthält, `Get-Help` gibt ein **extendedcmdlethelpinfo** -Objekt zurück, das die automatisch generierte Hilfe darstellt.</span><span class="sxs-lookup"><span data-stu-id="0dafc-293">If you run `Get-Help` on a command that doesn't have a help file, `Get-Help` returns an **ExtendedCmdletHelpInfo** object that represents autogenerated help.</span></span>

### <span data-ttu-id="0dafc-294">System.String</span><span class="sxs-lookup"><span data-stu-id="0dafc-294">System.String</span></span>

<span data-ttu-id="0dafc-295">Wenn Sie einen konzeptionellen Hilfeartikel erhalten, `Get-Help` gibt ihn als Zeichenfolge zurück.</span><span class="sxs-lookup"><span data-stu-id="0dafc-295">If you get a conceptual help article, `Get-Help` returns it as a string.</span></span>

### <span data-ttu-id="0dafc-296">MamlCommandHelpInfo</span><span class="sxs-lookup"><span data-stu-id="0dafc-296">MamlCommandHelpInfo</span></span>

<span data-ttu-id="0dafc-297">Wenn Sie einen Befehl mit einer Hilfedatei erhalten, `Get-Help` gibt ein **mamlcommandhelpinfo** -Objekt zurück.</span><span class="sxs-lookup"><span data-stu-id="0dafc-297">If you get a command that has a help file, `Get-Help` returns a **MamlCommandHelpInfo** object.</span></span>

## <span data-ttu-id="0dafc-298">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="0dafc-298">NOTES</span></span>

<span data-ttu-id="0dafc-299">PowerShell 3,0 enthält keine Hilfedateien.</span><span class="sxs-lookup"><span data-stu-id="0dafc-299">PowerShell 3.0 doesn't include help files.</span></span> <span data-ttu-id="0dafc-300">`Get-Help`Verwenden Sie das-Cmdlet, um die von gelesenen Hilfedateien herunterzuladen und zu installieren `Update-Help` .</span><span class="sxs-lookup"><span data-stu-id="0dafc-300">To download and install the help files that `Get-Help` reads, use the `Update-Help` cmdlet.</span></span> <span data-ttu-id="0dafc-301">Sie können das `Update-Help` Cmdlet zum herunterladen und Installieren von Hilfedateien für die Kern Befehle verwenden, die in PowerShell enthalten sind, sowie für alle Module, die Sie installieren.</span><span class="sxs-lookup"><span data-stu-id="0dafc-301">You can use the `Update-Help` cmdlet to download and install help files for the core commands that come with PowerShell and for any modules that you install.</span></span> <span data-ttu-id="0dafc-302">Sie können damit auch die Hilfedateien aktualisieren, sodass die Hilfedateien auf Ihrem Computer immer auf dem neuesten Stand sind.</span><span class="sxs-lookup"><span data-stu-id="0dafc-302">You can also use it to update the help files so that the help on your computer is never outdated.</span></span>

<span data-ttu-id="0dafc-303">Unter Erste Schritte [mit Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell)können Sie auch die Hilfeartikel zu den Befehlen von PowerShell Online lesen.</span><span class="sxs-lookup"><span data-stu-id="0dafc-303">You can also read the help articles about the commands that come with PowerShell online starting at [Getting Started with Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell).</span></span>

<span data-ttu-id="0dafc-304">`Get-Help` zeigt die Hilfe im Gebiets Schema an, das für das Windows-Betriebssystem oder in der Fall Back Sprache für dieses Gebiets Schema festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="0dafc-304">`Get-Help` displays help in the locale set for the Windows operating system or in the fallback language for that locale.</span></span> <span data-ttu-id="0dafc-305">Wenn Sie keine Hilfedateien für das primäre oder das Ausweich Gebiets Schema haben, `Get-Help` verhält sich so, als ob keine Hilfedateien auf dem Computer vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="0dafc-305">If you don't have help files for the primary or fallback locale, `Get-Help` behaves as if there are no help files on the computer.</span></span> <span data-ttu-id="0dafc-306">Um Hilfe für ein anderes Gebiets Schema zu erhalten, verwenden Sie **Region** und **Sprache** in der Systemsteuerung, um die Einstellungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="0dafc-306">To get help for a different locale, use **Region** and **Language** in Control Panel to change the settings.</span></span> <span data-ttu-id="0dafc-307">Unter Windows 10, **Einstellungen**, **Zeit & Sprache**.</span><span class="sxs-lookup"><span data-stu-id="0dafc-307">On Windows 10, **Settings**, **Time & Language**.</span></span>

<span data-ttu-id="0dafc-308">Die vollständige Ansicht der Hilfe enthält eine Tabelle mit Informationen zu den Parametern.</span><span class="sxs-lookup"><span data-stu-id="0dafc-308">The full view of help includes a table of information about the parameters.</span></span> <span data-ttu-id="0dafc-309">Die Tabelle enthält die folgenden Felder:</span><span class="sxs-lookup"><span data-stu-id="0dafc-309">The table includes the following fields:</span></span>

- <span data-ttu-id="0dafc-310">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="0dafc-310">**Required**.</span></span> <span data-ttu-id="0dafc-311">Gibt an, ob der Parameter erforderlich (true) oder optional ist (false).</span><span class="sxs-lookup"><span data-stu-id="0dafc-311">Indicates whether the parameter is required (true) or optional (false).</span></span>

- <span data-ttu-id="0dafc-312">**Position**.</span><span class="sxs-lookup"><span data-stu-id="0dafc-312">**Position**.</span></span> <span data-ttu-id="0dafc-313">Gibt an, ob der Parameter benannt oder Positions basiert (numerisch) ist.</span><span class="sxs-lookup"><span data-stu-id="0dafc-313">Indicates whether the parameter is named or positional (numeric).</span></span> <span data-ttu-id="0dafc-314">Positionsparameter müssen an einer angegebenen Position im Befehl verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0dafc-314">Positional parameters must appear in a specified place in the command.</span></span>

- <span data-ttu-id="0dafc-315">Mit dem **Namen** wird angegeben, dass der Parameter Name erforderlich ist, aber der Parameter kann an beliebiger Stelle im Befehl angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="0dafc-315">**Named** indicates that the parameter name is required, but that the parameter can appear anywhere in the command.</span></span>

- <span data-ttu-id="0dafc-316">**Numeric** gibt an, dass der Parameter Name optional ist, aber wenn der Name ausgelassen wird, muss der Parameter an der Stelle liegen, die durch die Zahl angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="0dafc-316">**Numeric** indicates that the parameter name is optional, but when the name is omitted, the parameter must be in the place specified by the number.</span></span> <span data-ttu-id="0dafc-317">`2`Gibt z. b. an, dass der Parameter, wenn der Parameter Name weggelassen wird, der zweite oder einzige unbenannte Parameter im Befehl sein muss.</span><span class="sxs-lookup"><span data-stu-id="0dafc-317">For example, `2` indicates that when the parameter name is omitted, the parameter must be the second or only unnamed parameter in the command.</span></span> <span data-ttu-id="0dafc-318">Wenn der Parametername verwendet wird, kann der Parameter an einer beliebigen Stelle im Befehl stehen.</span><span class="sxs-lookup"><span data-stu-id="0dafc-318">When the parameter name is used, the parameter can appear anywhere in the command.</span></span>

- <span data-ttu-id="0dafc-319">**Standardwert**.</span><span class="sxs-lookup"><span data-stu-id="0dafc-319">**Default value**.</span></span> <span data-ttu-id="0dafc-320">Der Parameterwert oder das Standardverhalten, das von PowerShell verwendet wird, wenn Sie den Parameter nicht in den Befehl einschließen.</span><span class="sxs-lookup"><span data-stu-id="0dafc-320">The parameter value or default behavior that PowerShell uses if you don't include the parameter in the command.</span></span>

- <span data-ttu-id="0dafc-321">Akzeptiert Pipeline Eingaben.</span><span class="sxs-lookup"><span data-stu-id="0dafc-321">Accepts pipeline input.</span></span> <span data-ttu-id="0dafc-322">Gibt an, ob Sie Objekte über eine Pipeline an den Parameter senden können (true) oder nicht (false).</span><span class="sxs-lookup"><span data-stu-id="0dafc-322">Indicates whether you can (true) or can't (false) send objects to the parameter through a pipeline.</span></span> <span data-ttu-id="0dafc-323">**Nach Eigenschaftsname** bedeutet, dass das Pipeline Objekt über eine Eigenschaft verfügen muss, die den gleichen Namen wie der Parameter Name hat.</span><span class="sxs-lookup"><span data-stu-id="0dafc-323">**By Property Name** means that the pipelined object must have a property that has the same name as the parameter name.</span></span>

- <span data-ttu-id="0dafc-324">**Akzeptiert** Platzhalter Zeichen.</span><span class="sxs-lookup"><span data-stu-id="0dafc-324">**Accepts wildcard characters**.</span></span> <span data-ttu-id="0dafc-325">Gibt an, ob der Wert eines Parameters Platzhalter Zeichen enthalten kann, z. b. ein Sternchen ( `*` ) oder ein Fragezeichen ( `?` ).</span><span class="sxs-lookup"><span data-stu-id="0dafc-325">Indicates whether the value of a parameter can include wildcard characters, such as an asterisk (`*`) or question mark (`?`).</span></span>

## <span data-ttu-id="0dafc-326">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="0dafc-326">RELATED LINKS</span></span>

[<span data-ttu-id="0dafc-327">about_Command_Syntax</span><span class="sxs-lookup"><span data-stu-id="0dafc-327">about_Command_Syntax</span></span>](About/about_Command_Syntax.md)

[<span data-ttu-id="0dafc-328">about_Comment_Based_Help</span><span class="sxs-lookup"><span data-stu-id="0dafc-328">about_Comment_Based_Help</span></span>](./About/about_Comment_Based_Help.md)

[<span data-ttu-id="0dafc-329">Get-Command</span><span class="sxs-lookup"><span data-stu-id="0dafc-329">Get-Command</span></span>](Get-Command.md)

[<span data-ttu-id="0dafc-330">Unterstützung einer aktualisierbaren Hilfe</span><span class="sxs-lookup"><span data-stu-id="0dafc-330">Supporting Updatable Help</span></span>](/powershell/scripting/developer/module/supporting-updatable-help)

[<span data-ttu-id="0dafc-331">Update-Help</span><span class="sxs-lookup"><span data-stu-id="0dafc-331">Update-Help</span></span>](Update-Help.md)

[<span data-ttu-id="0dafc-332">Schreiben von kommentarbasierten Hilfethemen</span><span class="sxs-lookup"><span data-stu-id="0dafc-332">Writing Comment-Based Help Topics</span></span>](/powershell/scripting/developer/help/writing-comment-based-help-topics)

[<span data-ttu-id="0dafc-333">Schreiben einer Hilfe für PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="0dafc-333">Writing Help for PowerShell Cmdlets</span></span>](/powershell/scripting/developer/help/writing-help-for-windows-powershell-cmdlets)

