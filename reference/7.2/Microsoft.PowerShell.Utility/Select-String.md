---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/22/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/select-string?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Select-String
ms.openlocfilehash: 339afab9c817b54a79e2f1b33b7021ecb4fe6a6e
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601897"
---
# <span data-ttu-id="dd643-102">Select-String</span><span class="sxs-lookup"><span data-stu-id="dd643-102">Select-String</span></span>

## <span data-ttu-id="dd643-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="dd643-103">SYNOPSIS</span></span>
<span data-ttu-id="dd643-104">Sucht nach Text in Dateien und Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="dd643-104">Finds text in strings and files.</span></span>

## <span data-ttu-id="dd643-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="dd643-105">SYNTAX</span></span>

### <span data-ttu-id="dd643-106">File (Standard)</span><span class="sxs-lookup"><span data-stu-id="dd643-106">File (Default)</span></span>

```
Select-String [-Culture <String>] [-Pattern] <String[]> [-Path] <String[]> [-SimpleMatch]
 [-CaseSensitive] [-Quiet] [-List] [-NoEmphasis] [-Include <String[]>] [-Exclude <String[]>]
 [-NotMatch] [-AllMatches] [-Encoding <Encoding>] [-Context <Int32[]>] [<CommonParameters>]
```

### <span data-ttu-id="dd643-107">Objectraw</span><span class="sxs-lookup"><span data-stu-id="dd643-107">ObjectRaw</span></span>

```
Select-String [-Culture <String>] -InputObject <PSObject> [-Pattern] <String[]> -Raw [-SimpleMatch]
 [-CaseSensitive] [-List] [-NoEmphasis] [-Include <String[]>] [-Exclude <String[]>] [-NotMatch]
 [-AllMatches] [-Encoding <Encoding>] [-Context <Int32[]>] [<CommonParameters>]
```

### <span data-ttu-id="dd643-108">Object</span><span class="sxs-lookup"><span data-stu-id="dd643-108">Object</span></span>

```
Select-String [-Culture <String>] -InputObject <PSObject> [-Pattern] <String[]> [-SimpleMatch]
 [-CaseSensitive] [-Quiet] [-List] [-NoEmphasis] [-Include <String[]>] [-Exclude <String[]>]
 [-NotMatch] [-AllMatches] [-Encoding <Encoding>] [-Context <Int32[]>] [<CommonParameters>]
```

### <span data-ttu-id="dd643-109">Filteraw</span><span class="sxs-lookup"><span data-stu-id="dd643-109">FileRaw</span></span>

```
Select-String [-Culture <String>] [-Pattern] <String[]> [-Path] <String[]> -Raw [-SimpleMatch]
 [-CaseSensitive] [-List] [-NoEmphasis] [-Include <String[]>] [-Exclude <String[]>] [-NotMatch]
 [-AllMatches] [-Encoding <Encoding>] [-Context <Int32[]>] [<CommonParameters>]
```

### <span data-ttu-id="dd643-110">Literalfileraw</span><span class="sxs-lookup"><span data-stu-id="dd643-110">LiteralFileRaw</span></span>

```
Select-String [-Culture <String>] [-Pattern] <String[]> -LiteralPath <String[]> -Raw [-SimpleMatch]
 [-CaseSensitive] [-List] [-NoEmphasis] [-Include <String[]>] [-Exclude <String[]>] [-NotMatch]
 [-AllMatches] [-Encoding <Encoding>] [-Context <Int32[]>] [<CommonParameters>]
```

### <span data-ttu-id="dd643-111">Literalfile</span><span class="sxs-lookup"><span data-stu-id="dd643-111">LiteralFile</span></span>

```
Select-String [-Culture <String>] [-Pattern] <String[]> -LiteralPath <String[]> [-SimpleMatch]
 [-CaseSensitive] [-Quiet] [-List] [-NoEmphasis] [-Include <String[]>] [-Exclude <String[]>]
 [-NotMatch] [-AllMatches] [-Encoding <Encoding>] [-Context <Int32[]>] [<CommonParameters>]
```

## <span data-ttu-id="dd643-112">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="dd643-112">DESCRIPTION</span></span>

<span data-ttu-id="dd643-113">Das `Select-String` Cmdlet sucht Text-und Textmuster in Eingabe Zeichenfolgen und Dateien.</span><span class="sxs-lookup"><span data-stu-id="dd643-113">The `Select-String` cmdlet searches for text and text patterns in input strings and files.</span></span> <span data-ttu-id="dd643-114">Sie können `Select-String` ähnlich wie **grep** in UNIX oder **findstr.exe** in Windows verwenden.</span><span class="sxs-lookup"><span data-stu-id="dd643-114">You can use `Select-String` similar to **grep** in UNIX or **findstr.exe** in Windows.</span></span>

<span data-ttu-id="dd643-115">`Select-String` basiert auf Textzeilen.</span><span class="sxs-lookup"><span data-stu-id="dd643-115">`Select-String` is based on lines of text.</span></span> <span data-ttu-id="dd643-116">Standardmäßig `Select-String` sucht die erste Übereinstimmung in jeder Zeile und zeigt für jede Übereinstimmung den Dateinamen, die Zeilennummer und den gesamten Text in der Zeile an, die die Übereinstimmung enthält.</span><span class="sxs-lookup"><span data-stu-id="dd643-116">By default, `Select-String` finds the first match in each line and, for each match, it displays the file name, line number, and all text in the line containing the match.</span></span> <span data-ttu-id="dd643-117">Sie können angeben, `Select-String` ob mehrere Übereinstimmungen pro Zeile gefunden werden, wie Text vor und nach der Übereinstimmung angezeigt werden soll oder ob ein boolescher Wert (true oder false) angezeigt werden soll, der angibt, ob eine Übereinstimmung gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="dd643-117">You can direct `Select-String` to find multiple matches per line, display text before and after the match, or display a Boolean value (True or False) that indicates whether a match is found.</span></span>

<span data-ttu-id="dd643-118">`Select-String` verwendet reguläre Ausdrucks Vergleiche, aber es kann auch eine Übereinstimmung durchsucht werden, die die Eingabe nach dem angegebenen Text durchsucht.</span><span class="sxs-lookup"><span data-stu-id="dd643-118">`Select-String` uses regular expression matching, but it can also perform a match that searches the input for the text that you specify.</span></span>

<span data-ttu-id="dd643-119">`Select-String` kann alle Text Übereinstimmungen anzeigen oder nach der ersten Übereinstimmung in jeder Eingabedatei angehalten werden.</span><span class="sxs-lookup"><span data-stu-id="dd643-119">`Select-String` can display all the text matches or stop after the first match in each input file.</span></span>
<span data-ttu-id="dd643-120">`Select-String` kann verwendet werden, um den gesamten Text anzuzeigen, der nicht dem angegebenen Muster entspricht.</span><span class="sxs-lookup"><span data-stu-id="dd643-120">`Select-String` can be used to display all text that doesn't match the specified pattern.</span></span>

<span data-ttu-id="dd643-121">Sie können auch angeben, dass `Select-String` eine bestimmte Zeichencodierung erwarten soll, z. b. beim Durchsuchen von Dateien mit Unicode-Text.</span><span class="sxs-lookup"><span data-stu-id="dd643-121">You can also specify that `Select-String` should expect a particular character encoding, such as when you're searching files of Unicode text.</span></span> <span data-ttu-id="dd643-122">`Select-String` verwendet die Byte Reihenfolge-Markierung (BOM), um das Codierungsformat der Datei zu erkennen.</span><span class="sxs-lookup"><span data-stu-id="dd643-122">`Select-String` uses the byte-order-mark (BOM) to detect the encoding format of the file.</span></span> <span data-ttu-id="dd643-123">Wenn die Datei keine BOM enthält, wird davon ausgegangen, dass die Codierung UTF8 ist.</span><span class="sxs-lookup"><span data-stu-id="dd643-123">If the file has no BOM, it assumes the encoding is UTF8.</span></span>

## <span data-ttu-id="dd643-124">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="dd643-124">EXAMPLES</span></span>

### <span data-ttu-id="dd643-125">Beispiel 1: Suchen nach der Groß-/Kleinschreibung</span><span class="sxs-lookup"><span data-stu-id="dd643-125">Example 1: Find a case-sensitive match</span></span>

<span data-ttu-id="dd643-126">In diesem Beispiel wird die Groß-/Kleinschreibung beachtet, die in der Pipeline an das `Select-String` Cmdlet gesendet wurde.</span><span class="sxs-lookup"><span data-stu-id="dd643-126">This example does a case-sensitive match of the text that was sent down the pipeline to the `Select-String` cmdlet.</span></span>

```powershell
'Hello', 'HELLO' | Select-String -Pattern 'HELLO' -CaseSensitive -SimpleMatch
```

<span data-ttu-id="dd643-127">Die Text Zeichenfolgen **Hello** und **Hello** werden über die Pipeline an das `Select-String` Cmdlet gesendet.</span><span class="sxs-lookup"><span data-stu-id="dd643-127">The text strings **Hello** and **HELLO** are sent down the pipeline to the `Select-String` cmdlet.</span></span>
<span data-ttu-id="dd643-128">`Select-String` verwendet den **Pattern** -Parameter, um **Hello** anzugeben.</span><span class="sxs-lookup"><span data-stu-id="dd643-128">`Select-String` uses the **Pattern** parameter to specify **HELLO**.</span></span> <span data-ttu-id="dd643-129">Der **CaseSensitive** -Parameter gibt an, dass der Fall nur dem Großbuchstaben entsprechen muss.</span><span class="sxs-lookup"><span data-stu-id="dd643-129">The **CaseSensitive** parameter specifies that the case must match only the upper-case pattern.</span></span> <span data-ttu-id="dd643-130">**Simplematch** ist ein optionaler Parameter, der angibt, dass die Zeichenfolge im Muster nicht als regulärer Ausdruck interpretiert wird.</span><span class="sxs-lookup"><span data-stu-id="dd643-130">**SimpleMatch** is an optional parameter and specifies that the string in the pattern isn't interpreted as a regular expression.</span></span>
<span data-ttu-id="dd643-131">`Select-String` zeigt **Hello** in der PowerShell-Konsole an.</span><span class="sxs-lookup"><span data-stu-id="dd643-131">`Select-String` displays **HELLO** in the PowerShell console.</span></span>

### <span data-ttu-id="dd643-132">Beispiel 2: Suchen von Übereinstimmungen in Textdateien</span><span class="sxs-lookup"><span data-stu-id="dd643-132">Example 2: Find matches in text files</span></span>

<span data-ttu-id="dd643-133">Mit diesem Befehl werden alle Dateien mit der `.txt` Dateinamenerweiterung im aktuellen Verzeichnis durchsucht.</span><span class="sxs-lookup"><span data-stu-id="dd643-133">This command searches all files with the `.txt` file name extension in the current directory.</span></span> <span data-ttu-id="dd643-134">Die Ausgabe zeigt die Zeilen in den Dateien an, die die angegebene Zeichenfolge enthalten.</span><span class="sxs-lookup"><span data-stu-id="dd643-134">The output displays the lines in those files that include the specified string.</span></span>

```powershell
Get-Alias | Out-File -FilePath .\Alias.txt
Get-Command | Out-File -FilePath .\Command.txt
Select-String -Path .\*.txt -Pattern 'Get-'
```

```Output
Alias.txt:8:Alias            cat -> Get-Content
Alias.txt:28:Alias           dir -> Get-ChildItem
Alias.txt:43:Alias           gal -> Get-Alias
Command.txt:966:Cmdlet       Get-Acl
Command.txt:967:Cmdlet       Get-Alias
```

<span data-ttu-id="dd643-135">In diesem Beispiel `Get-Alias` werden und `Get-Command` mit dem- `Out-File` Cmdlet zum Erstellen von zwei Textdateien im aktuellen Verzeichnis, **Alias.txt** und **Command.txt** verwendet.</span><span class="sxs-lookup"><span data-stu-id="dd643-135">In this example, `Get-Alias` and `Get-Command` are used with the `Out-File` cmdlet to create two text files in the current directory, **Alias.txt** and **Command.txt**.</span></span>

<span data-ttu-id="dd643-136">`Select-String` verwendet den **path** -Parameter mit dem Platzhalter Sternchen ( `*` ), um alle Dateien im aktuellen Verzeichnis mit der Dateinamenerweiterung zu durchsuchen `.txt` .</span><span class="sxs-lookup"><span data-stu-id="dd643-136">`Select-String` uses the **Path** parameter with the asterisk (`*`) wildcard to search all files in the current directory with the file name extension `.txt`.</span></span> <span data-ttu-id="dd643-137">Der **Pattern** -Parameter gibt den Text an, der mit **Get-** identisch ist.</span><span class="sxs-lookup"><span data-stu-id="dd643-137">The **Pattern** parameter specifies the text to match **Get-**.</span></span> <span data-ttu-id="dd643-138">`Select-String` zeigt die Ausgabe in der PowerShell-Konsole an.</span><span class="sxs-lookup"><span data-stu-id="dd643-138">`Select-String` displays the output in the PowerShell console.</span></span> <span data-ttu-id="dd643-139">Der Dateiname und die Zeilennummer stehen vor jeder Inhalts Zeile, die eine Übereinstimmung für den **Pattern** -Parameter enthält.</span><span class="sxs-lookup"><span data-stu-id="dd643-139">The file name and line number precede each line of content that contains a match for the **Pattern** parameter.</span></span>

### <span data-ttu-id="dd643-140">Beispiel 3: Suchen einer Muster Übereinstimmung</span><span class="sxs-lookup"><span data-stu-id="dd643-140">Example 3: Find a pattern match</span></span>

<span data-ttu-id="dd643-141">In diesem Beispiel werden mehrere Dateien durchsucht, um nach Übereinstimmungen für das angegebene Muster zu suchen.</span><span class="sxs-lookup"><span data-stu-id="dd643-141">In this example, multiple files are searched to find matches for the specified pattern.</span></span> <span data-ttu-id="dd643-142">Das-Muster verwendet einen regulären Ausdrucks Quantifizierer.</span><span class="sxs-lookup"><span data-stu-id="dd643-142">The pattern uses a regular expression quantifier.</span></span> <span data-ttu-id="dd643-143">Weitere Informationen finden Sie unter [about_Regular_Expressions](../Microsoft.PowerShell.Core/About/About_Regular_Expressions.md).</span><span class="sxs-lookup"><span data-stu-id="dd643-143">For more information, see [about_Regular_Expressions](../Microsoft.PowerShell.Core/About/About_Regular_Expressions.md).</span></span>

```powershell
Select-String -Path "$PSHOME\en-US\*.txt" -Pattern '\?'
```

```Output
C:\Program Files\PowerShell\6\en-US\default.help.txt:27:    beginning at https://go.microsoft.com/fwlink/?LinkID=108518.
C:\Program Files\PowerShell\6\en-US\default.help.txt:50:    or go to: https://go.microsoft.com/fwlink/?LinkID=210614
```

<span data-ttu-id="dd643-144">Das `Select-String` Cmdlet verwendet zwei Parameter: **path** und **Pattern**.</span><span class="sxs-lookup"><span data-stu-id="dd643-144">The `Select-String` cmdlet uses two parameters, **Path** and **Pattern**.</span></span> <span data-ttu-id="dd643-145">Der **path** -Parameter verwendet die-Variable `$PSHOME` , die das PowerShell-Verzeichnis angibt.</span><span class="sxs-lookup"><span data-stu-id="dd643-145">The **Path** parameter uses the variable `$PSHOME` that specifies the PowerShell directory.</span></span> <span data-ttu-id="dd643-146">Der Rest des Pfads enthält das Unterverzeichnis **en-US** und gibt jede `*.txt` Datei im Verzeichnis an.</span><span class="sxs-lookup"><span data-stu-id="dd643-146">The remainder of the path includes the subdirectory **en-US** and specifies each `*.txt` file in the directory.</span></span> <span data-ttu-id="dd643-147">Der **Pattern** -Parameter gibt an, dass in jeder Datei ein Fragezeichen () gefunden werden soll `?` .</span><span class="sxs-lookup"><span data-stu-id="dd643-147">The **Pattern** parameter specifies to match a question mark (`?`) in each file.</span></span> <span data-ttu-id="dd643-148">Ein umgekehrter Schrägstrich ( `\` ) wird als Escapezeichen verwendet und ist erforderlich, da das Fragezeichen ( `?` ) ein Quantifizierer für reguläre Ausdrücke ist.</span><span class="sxs-lookup"><span data-stu-id="dd643-148">A backslash (`\`) is used as an escape character and is necessary because the question mark (`?`) is a regular expression quantifier.</span></span> <span data-ttu-id="dd643-149">`Select-String` zeigt die Ausgabe in der PowerShell-Konsole an.</span><span class="sxs-lookup"><span data-stu-id="dd643-149">`Select-String` displays the output in the PowerShell console.</span></span> <span data-ttu-id="dd643-150">Der Dateiname und die Zeilennummer stehen vor jeder Inhalts Zeile, die eine Übereinstimmung für den **Pattern** -Parameter enthält.</span><span class="sxs-lookup"><span data-stu-id="dd643-150">The file name and line number precede each line of content that contains a match for the **Pattern** parameter.</span></span>

### <span data-ttu-id="dd643-151">Beispiel 4: Verwenden von Select-String in einer Funktion</span><span class="sxs-lookup"><span data-stu-id="dd643-151">Example 4: Use Select-String in a function</span></span>

<span data-ttu-id="dd643-152">In diesem Beispiel wird eine Funktion erstellt, um in den PowerShell-Hilfedateien nach einem Muster zu suchen.</span><span class="sxs-lookup"><span data-stu-id="dd643-152">This example creates a function to search for a pattern in the PowerShell help files.</span></span> <span data-ttu-id="dd643-153">In diesem Beispiel ist die Funktion nur in der PowerShell-Sitzung vorhanden.</span><span class="sxs-lookup"><span data-stu-id="dd643-153">For this example, the function only exists in the PowerShell session.</span></span> <span data-ttu-id="dd643-154">Wenn die PowerShell-Sitzung geschlossen ist, wird die Funktion gelöscht.</span><span class="sxs-lookup"><span data-stu-id="dd643-154">When the PowerShell session is closed, the function is deleted.</span></span> <span data-ttu-id="dd643-155">Weitere Informationen finden Sie unter [about_Functions](../Microsoft.PowerShell.Core/About/about_Functions.md).</span><span class="sxs-lookup"><span data-stu-id="dd643-155">For more information, see [about_Functions](../Microsoft.PowerShell.Core/About/about_Functions.md).</span></span>

```
PS> Function Search-Help
>> {
>> $PSHelp = "$PSHOME\en-US\*.txt"
>> Select-String -Path $PSHelp -Pattern 'About_'
>> }
PS>

PS> Search-Help

C:\Program Files\PowerShell\6\en-US\default.help.txt:67:    The titles of conceptual topics begin with "About_".
C:\Program Files\PowerShell\6\en-US\default.help.txt:70:    Get-Help About_<topic-name>
C:\Program Files\PowerShell\6\en-US\default.help.txt:93:    Get-Help About_Modules : Displays help about PowerShell modules.
C:\Program Files\PowerShell\6\en-US\default.help.txt:97:    about_Updatable_Help
```

<span data-ttu-id="dd643-156">Die-Funktion wird in der PowerShell-Befehlszeile erstellt.</span><span class="sxs-lookup"><span data-stu-id="dd643-156">The function is created on the PowerShell command line.</span></span> <span data-ttu-id="dd643-157">Der `Function` Befehl verwendet den Namen **Search-Help**.</span><span class="sxs-lookup"><span data-stu-id="dd643-157">The `Function` command uses the name **Search-Help**.</span></span> <span data-ttu-id="dd643-158">Drücken **Sie die Eingabe** Taste, um der Funktion Anweisungen hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="dd643-158">Press **Enter** to begin adding statements to the function.</span></span> <span data-ttu-id="dd643-159">`>>`Fügen Sie in der Eingabeaufforderung jede-Anweisung hinzu, und drücken **Sie die Eingabe** Taste, wie im Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="dd643-159">From the `>>` prompt, add each statement and press **Enter** as shown in the example.</span></span> <span data-ttu-id="dd643-160">Nachdem die schließende Klammer hinzugefügt wurde, werden Sie an eine PowerShell-Eingabeaufforderung zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="dd643-160">After the closing bracket is added, you're returned to a PowerShell prompt.</span></span>

<span data-ttu-id="dd643-161">Die Funktion enthält zwei Befehle.</span><span class="sxs-lookup"><span data-stu-id="dd643-161">The function contains two commands.</span></span> <span data-ttu-id="dd643-162">Die `$PSHelp` Variable speichert den Pfad zu den PowerShell-Hilfedateien.</span><span class="sxs-lookup"><span data-stu-id="dd643-162">The `$PSHelp` variable stores the path to the PowerShell help files.</span></span> <span data-ttu-id="dd643-163">`$PSHOME` ist das PowerShell-Installationsverzeichnis mit dem Unterverzeichnis " **en-US** ", das jede `*.txt` Datei im Verzeichnis angibt.</span><span class="sxs-lookup"><span data-stu-id="dd643-163">`$PSHOME` is the PowerShell installation directory with the subdirectory **en-US** that specifies each `*.txt` file in the directory.</span></span>

<span data-ttu-id="dd643-164">Der `Select-String` -Befehl in der-Funktion verwendet die **path** -und **Pattern** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="dd643-164">The `Select-String` command in the function uses the **Path** and **Pattern** parameters.</span></span> <span data-ttu-id="dd643-165">Der **path** -Parameter verwendet die- `$PSHelp` Variable, um den Pfad zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="dd643-165">The **Path** parameter uses the `$PSHelp` variable to get the path.</span></span> <span data-ttu-id="dd643-166">Der **Pattern** -Parameter verwendet die Zeichenfolge **About_** als Suchkriterium.</span><span class="sxs-lookup"><span data-stu-id="dd643-166">The **Pattern** parameter uses the string **About_** as the search criteria.</span></span>

<span data-ttu-id="dd643-167">Geben Sie ein, um die Funktion auszuführen `Search-Help` .</span><span class="sxs-lookup"><span data-stu-id="dd643-167">To run the function, type `Search-Help`.</span></span> <span data-ttu-id="dd643-168">Der Befehl der Funktion `Select-String` zeigt die Ausgabe in der PowerShell-Konsole an.</span><span class="sxs-lookup"><span data-stu-id="dd643-168">The function's `Select-String` command displays the output in the PowerShell console.</span></span>

### <span data-ttu-id="dd643-169">Beispiel 5: Suchen nach einer Zeichenfolge in einem Windows-Ereignisprotokoll</span><span class="sxs-lookup"><span data-stu-id="dd643-169">Example 5: Search for a string in a Windows event log</span></span>

<span data-ttu-id="dd643-170">Dieses Beispiel sucht nach einer Zeichenfolge in einem Windows-Ereignisprotokoll.</span><span class="sxs-lookup"><span data-stu-id="dd643-170">This example searches for a string in a Windows event log.</span></span> <span data-ttu-id="dd643-171">Die-Variable `$_` stellt das aktuelle Objekt in der Pipeline dar.</span><span class="sxs-lookup"><span data-stu-id="dd643-171">The variable `$_` represents the current object in the pipeline.</span></span> <span data-ttu-id="dd643-172">Weitere Informationen finden Sie unter [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="dd643-172">For more information, see [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md).</span></span>

```powershell
$Events = Get-WinEvent -LogName Application -MaxEvents 50
$Events | Select-String -InputObject {$_.message} -Pattern 'Failed'
```

<span data-ttu-id="dd643-173">Das- `Get-WinEvent` Cmdlet verwendet den **logName** -Parameter, um das Anwendungsprotokoll anzugeben.</span><span class="sxs-lookup"><span data-stu-id="dd643-173">The `Get-WinEvent` cmdlet uses the **LogName** parameter to specify the Application log.</span></span> <span data-ttu-id="dd643-174">Der **maxevents** -Parameter ruft die letzten 50-Ereignisse aus dem Protokoll ab.</span><span class="sxs-lookup"><span data-stu-id="dd643-174">The **MaxEvents** parameter gets the 50 most recent events from the log.</span></span> <span data-ttu-id="dd643-175">Der Protokoll Inhalt wird in der Variablen mit dem Namen gespeichert `$Events` .</span><span class="sxs-lookup"><span data-stu-id="dd643-175">The log content is stored in the variable named `$Events`.</span></span>

<span data-ttu-id="dd643-176">Die `$Events` Variable wird an das Cmdlet über die Pipeline gesendet `Select-String` .</span><span class="sxs-lookup"><span data-stu-id="dd643-176">The `$Events` variable is sent down the pipeline to the `Select-String` cmdlet.</span></span> <span data-ttu-id="dd643-177">`Select-String` verwendet den **Inputobject** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="dd643-177">`Select-String` uses the **InputObject** parameter.</span></span> <span data-ttu-id="dd643-178">Die `$_` -Variable stellt das aktuelle-Objekt dar und `message` ist eine Eigenschaft des-Ereignisses.</span><span class="sxs-lookup"><span data-stu-id="dd643-178">The `$_` variable represents the current object and `message` is a property of the event.</span></span> <span data-ttu-id="dd643-179">Die **Muster** Parameter Arten der Zeichenfolge ist **fehlgeschlagen** , und in wird nach Übereinstimmungen gesucht `$_.message` .</span><span class="sxs-lookup"><span data-stu-id="dd643-179">The **Pattern** parameter species the string **Failed** and searches for matches in `$_.message`.</span></span> <span data-ttu-id="dd643-180">`Select-String` zeigt die Ausgabe in der PowerShell-Konsole an.</span><span class="sxs-lookup"><span data-stu-id="dd643-180">`Select-String` displays the output in the PowerShell console.</span></span>

### <span data-ttu-id="dd643-181">Beispiel 6: Suchen nach einer Zeichenfolge in Unterverzeichnissen</span><span class="sxs-lookup"><span data-stu-id="dd643-181">Example 6: Find a string in subdirectories</span></span>

<span data-ttu-id="dd643-182">In diesem Beispiel werden ein Verzeichnis und alle Unterverzeichnisse für eine bestimmte Text Zeichenfolge durchsucht.</span><span class="sxs-lookup"><span data-stu-id="dd643-182">This example searches a directory and all of its subdirectories for a specific text string.</span></span>

```powershell
Get-ChildItem -Path C:\Windows\System32\*.txt -Recurse | Select-String -Pattern 'Microsoft' -CaseSensitive
```

<span data-ttu-id="dd643-183">`Get-ChildItem` verwendet den **path** -Parameter, um **c:\Windows\System32 \* . txt** anzugeben.</span><span class="sxs-lookup"><span data-stu-id="dd643-183">`Get-ChildItem` uses the **Path** parameter to specify **C:\Windows\System32\*.txt**.</span></span> <span data-ttu-id="dd643-184">Der **recurse** -Parameter enthält die Unterverzeichnisse.</span><span class="sxs-lookup"><span data-stu-id="dd643-184">The **Recurse** parameter includes the subdirectories.</span></span> <span data-ttu-id="dd643-185">Die Objekte werden über die Pipeline an gesendet `Select-String` .</span><span class="sxs-lookup"><span data-stu-id="dd643-185">The objects are sent down the pipeline to `Select-String`.</span></span>

<span data-ttu-id="dd643-186">`Select-String` verwendet den **Pattern** -Parameter und gibt die Zeichenfolge **Microsoft** an.</span><span class="sxs-lookup"><span data-stu-id="dd643-186">`Select-String` uses the **Pattern** parameter and specifies the string **Microsoft**.</span></span> <span data-ttu-id="dd643-187">Der **CaseSensitive** -Parameter wird verwendet, um die exakte Groß-/Kleinschreibung der Zeichenfolge abzugleichen.</span><span class="sxs-lookup"><span data-stu-id="dd643-187">The **CaseSensitive** parameter is used to match the exact case of the string.</span></span> <span data-ttu-id="dd643-188">`Select-String` zeigt die Ausgabe in der PowerShell-Konsole an.</span><span class="sxs-lookup"><span data-stu-id="dd643-188">`Select-String` displays the output in the PowerShell console.</span></span>

> [!NOTE]
> <span data-ttu-id="dd643-189">Abhängig von ihren Berechtigungen werden in der Ausgabe möglicherweise die Meldung " **Zugriff verweigert** " angezeigt.</span><span class="sxs-lookup"><span data-stu-id="dd643-189">Dependent upon your permissions, you might see **Access denied** messages in the output.</span></span>

### <span data-ttu-id="dd643-190">Beispiel 7: Suchen nach Zeichen folgen, die nicht mit einem Muster in Einklang stehen</span><span class="sxs-lookup"><span data-stu-id="dd643-190">Example 7: Find strings that do not match a pattern</span></span>

<span data-ttu-id="dd643-191">In diesem Beispiel wird gezeigt, wie Daten Zeilen ausgeschlossen werden, die nicht mit einem Muster zu vergleichen sind.</span><span class="sxs-lookup"><span data-stu-id="dd643-191">This example shows how to exclude lines of data that don't match a pattern.</span></span>

```powershell
Get-Command | Out-File -FilePath .\Command.txt
Select-String -Path .\Command.txt -Pattern 'Get', 'Set'  -NotMatch
```

<span data-ttu-id="dd643-192">Das- `Get-Command` Cmdlet sendet Objekte über die Pipeline an den `Out-File` , um die **Command.txt** Datei im aktuellen Verzeichnis zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="dd643-192">The `Get-Command` cmdlet sends objects down the pipeline to the `Out-File` to create the **Command.txt** file in the current directory.</span></span> <span data-ttu-id="dd643-193">`Select-String` verwendet den **path** -Parameter, um die **Command.txt** Datei anzugeben.</span><span class="sxs-lookup"><span data-stu-id="dd643-193">`Select-String` uses the **Path** parameter to specify the **Command.txt** file.</span></span> <span data-ttu-id="dd643-194">Der **Pattern** -Parameter gibt **Get** und **set** als Suchmuster an.</span><span class="sxs-lookup"><span data-stu-id="dd643-194">The **Pattern** parameter specifies **Get** and **Set** as the search pattern.</span></span> <span data-ttu-id="dd643-195">Der **notmatch** -Parameter schließt **Get** und **set** aus den Ergebnissen aus.</span><span class="sxs-lookup"><span data-stu-id="dd643-195">The **NotMatch** parameter excludes **Get** and **Set** from the results.</span></span>
<span data-ttu-id="dd643-196">`Select-String` zeigt die Ausgabe in der PowerShell-Konsole an, die " **Get** " oder " **set**" nicht enthält.</span><span class="sxs-lookup"><span data-stu-id="dd643-196">`Select-String` displays the output in the PowerShell console that doesn't include **Get** or **Set**.</span></span>

### <span data-ttu-id="dd643-197">Beispiel 8: Suchen nach Zeilen vor und nach einer Entsprechung</span><span class="sxs-lookup"><span data-stu-id="dd643-197">Example 8: Find lines before and after a match</span></span>

<span data-ttu-id="dd643-198">Dieses Beispiel zeigt, wie Sie die Zeilen vor und nach dem übereinstimmenden Muster erhalten.</span><span class="sxs-lookup"><span data-stu-id="dd643-198">This example shows how to get the lines before and after the matched pattern.</span></span>

```powershell
Get-Command | Out-File -FilePath .\Command.txt
Select-String -Path .\Command.txt -Pattern 'Get-Computer' -Context 2, 3
```

```Output
  Command.txt:986:Cmdlet          Get-CmsMessage           6.1.0.0    Microsoft.PowerShell.Security
  Command.txt:987:Cmdlet          Get-Command              6.1.2.0    Microsoft.PowerShell.Core
> Command.txt:988:Cmdlet          Get-ComputerInfo         6.1.0.0    Microsoft.PowerShell.Management
  Command.txt:990:Cmdlet          Get-Content              6.1.0.0    Microsoft.PowerShell.Management
  Command.txt:991:Cmdlet          Get-ControlPanelItem     3.1.0.0    Microsoft.PowerShell.Management
  Command.txt:992:Cmdlet          Get-Credential           6.1.0.0    Microsoft.PowerShell.Security
```

<span data-ttu-id="dd643-199">Das- `Get-Command` Cmdlet sendet Objekte über die Pipeline an den `Out-File` , um die **Command.txt** Datei im aktuellen Verzeichnis zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="dd643-199">The `Get-Command` cmdlet sends objects down the pipeline to the `Out-File` to create the **Command.txt** file in the current directory.</span></span> <span data-ttu-id="dd643-200">`Select-String` verwendet den **path** -Parameter, um die **Command.txt** Datei anzugeben.</span><span class="sxs-lookup"><span data-stu-id="dd643-200">`Select-String` uses the **Path** parameter to specify the **Command.txt** file.</span></span> <span data-ttu-id="dd643-201">Der **Pattern** -Parameter gibt **Get-Computer** als Suchmuster an.</span><span class="sxs-lookup"><span data-stu-id="dd643-201">The **Pattern** parameter specifies **Get-Computer** as the search pattern.</span></span> <span data-ttu-id="dd643-202">Der **Kontext** Parameter verwendet zwei Werte, vor und nach, und markiert Muster Übereinstimmungen in der Ausgabe mit einer Spitze Klammer ( `>` ).</span><span class="sxs-lookup"><span data-stu-id="dd643-202">The **Context** parameter uses two values, before and after, and marks pattern matches in the output with an angle bracket (`>`).</span></span> <span data-ttu-id="dd643-203">Der **Kontext** Parameter gibt die zwei Zeilen vor der ersten Muster Übereinstimmung und drei Zeilen nach der letzten Muster Übereinstimmung aus.</span><span class="sxs-lookup"><span data-stu-id="dd643-203">The **Context** parameter outputs the two lines before the first pattern match and three lines after the last pattern match.</span></span>

### <span data-ttu-id="dd643-204">Beispiel 9: Suchen aller Muster Übereinstimmungen</span><span class="sxs-lookup"><span data-stu-id="dd643-204">Example 9: Find all pattern matches</span></span>

<span data-ttu-id="dd643-205">Dieses Beispiel zeigt, wie der **allmatches** -Parameter jede Muster Übereinstimmung in einer Textzeile findet.</span><span class="sxs-lookup"><span data-stu-id="dd643-205">This example shows how the **AllMatches** parameter finds each pattern match in a line of text.</span></span> <span data-ttu-id="dd643-206">Standardmäßig `Select-String` findet nur das erste Vorkommen eines Musters in einer Textzeile.</span><span class="sxs-lookup"><span data-stu-id="dd643-206">By default, `Select-String` only finds the first occurrence of a pattern in a line of text.</span></span> <span data-ttu-id="dd643-207">In diesem Beispiel werden Objekteigenschaften verwendet, die mit dem- `Get-Member` Cmdlet gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="dd643-207">This example uses object properties that are found with the `Get-Member` cmdlet.</span></span>

```
PS> $A = Get-ChildItem -Path "$PSHOME\en-US\*.txt" | Select-String -Pattern 'PowerShell'

PS> $A

C:\Program Files\PowerShell\6\en-US\default.help.txt:3:    PowerShell Help System
C:\Program Files\PowerShell\6\en-US\default.help.txt:6:    Displays help about PowerShell cmdlets and concepts.
C:\Program Files\PowerShell\6\en-US\default.help.txt:9:    PowerShell Help describes PowerShell cmdlets

PS> $A.Matches

Groups   : {0}
Success  : True
Name     : 0
Captures : {0}
Index    : 4
Length   : 10
Value    : PowerShell

PS> $A.Matches.Length

8

PS> $B = Get-ChildItem -Path "$PSHOME\en-US\*.txt" | Select-String -Pattern 'PowerShell' -AllMatches

PS> $B.Matches.Length

9
```

<span data-ttu-id="dd643-208">Das `Get-ChildItem` Cmdlet verwendet den **path** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="dd643-208">The `Get-ChildItem` cmdlet uses the **Path** parameter.</span></span> <span data-ttu-id="dd643-209">Der **path** -Parameter verwendet die-Variable `$PSHOME` , die das PowerShell-Verzeichnis angibt.</span><span class="sxs-lookup"><span data-stu-id="dd643-209">The **Path** parameter uses the variable `$PSHOME` that specifies the PowerShell directory.</span></span> <span data-ttu-id="dd643-210">Der Rest des Pfads enthält das Unterverzeichnis **en-US** und gibt jede `*.txt` Datei im Verzeichnis an.</span><span class="sxs-lookup"><span data-stu-id="dd643-210">The remainder of the path includes the subdirectory **en-US** and specifies each `*.txt` file in the directory.</span></span> <span data-ttu-id="dd643-211">Die- `Get-ChildItem` Objekte werden in der- `$A` Variable gespeichert.</span><span class="sxs-lookup"><span data-stu-id="dd643-211">The `Get-ChildItem` objects are stored in the `$A` variable.</span></span> <span data-ttu-id="dd643-212">Die `$A` Variable wird an das Cmdlet über die Pipeline gesendet `Select-String` .</span><span class="sxs-lookup"><span data-stu-id="dd643-212">The `$A` variable is sent down the pipeline to the `Select-String` cmdlet.</span></span> <span data-ttu-id="dd643-213">`Select-String` verwendet den **Pattern** -Parameter, um jede Datei nach der **PowerShell**-Zeichenfolge zu durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="dd643-213">`Select-String` uses the **Pattern** parameter to search each file for the string **PowerShell**.</span></span>

<span data-ttu-id="dd643-214">In der PowerShell-Befehlszeile `$A` werden der Inhalt der Variablen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="dd643-214">From the PowerShell command line, the `$A` variable contents are displayed.</span></span> <span data-ttu-id="dd643-215">Es gibt eine Zeile, die zwei Vorkommen der Zeichenfolge **PowerShell** enthält.</span><span class="sxs-lookup"><span data-stu-id="dd643-215">There's a line that contains two occurrences of the string **PowerShell**.</span></span>

<span data-ttu-id="dd643-216">Die- `$A.Matches` Eigenschaft listet das erste Vorkommen des Musters von **PowerShell** in jeder Zeile auf.</span><span class="sxs-lookup"><span data-stu-id="dd643-216">The `$A.Matches` property lists the first occurrence of the pattern **PowerShell** on each line.</span></span>

<span data-ttu-id="dd643-217">Die- `$A.Matches.Length` Eigenschaft zählt das erste Vorkommen des Musters von **PowerShell** in jeder Zeile.</span><span class="sxs-lookup"><span data-stu-id="dd643-217">The `$A.Matches.Length` property counts the first occurrence of the pattern **PowerShell** on each line.</span></span>

<span data-ttu-id="dd643-218">Die `$B` -Variable verwendet die gleichen `Get-ChildItem` -und- `Select-String` Cmdlets, fügt jedoch den **allmatches** -Parameter hinzu.</span><span class="sxs-lookup"><span data-stu-id="dd643-218">The `$B` variable uses the same `Get-ChildItem` and `Select-String` cmdlets, but adds the **AllMatches** parameter.</span></span> <span data-ttu-id="dd643-219">**Allmatches** findet jedes Vorkommen des Musters von **PowerShell** in jeder Zeile.</span><span class="sxs-lookup"><span data-stu-id="dd643-219">**AllMatches** finds each occurrence of the pattern **PowerShell** on each line.</span></span> <span data-ttu-id="dd643-220">Die in den `$A` Variablen und gespeicherten Objekte `$B` sind identisch.</span><span class="sxs-lookup"><span data-stu-id="dd643-220">The objects stored in the `$A` and `$B` variables are identical.</span></span>

<span data-ttu-id="dd643-221">Die- `$B.Matches.Length` Eigenschaft erhöht sich, weil für jede Zeile jedes Vorkommen des Musters **PowerShell** gezählt wird.</span><span class="sxs-lookup"><span data-stu-id="dd643-221">The `$B.Matches.Length` property increases because for each line, every occurrence of the pattern **PowerShell** is counted.</span></span>

## <span data-ttu-id="dd643-222">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="dd643-222">PARAMETERS</span></span>

### <span data-ttu-id="dd643-223">-Allmatches</span><span class="sxs-lookup"><span data-stu-id="dd643-223">-AllMatches</span></span>

<span data-ttu-id="dd643-224">Gibt an, dass das Cmdlet in jeder Textzeile mehr als eine Übereinstimmung sucht.</span><span class="sxs-lookup"><span data-stu-id="dd643-224">Indicates that the cmdlet searches for more than one match in each line of text.</span></span> <span data-ttu-id="dd643-225">Ohne diesen Parameter `Select-String` findet nur die erste Übereinstimmung in jeder Textzeile.</span><span class="sxs-lookup"><span data-stu-id="dd643-225">Without this parameter, `Select-String` finds only the first match in each line of text.</span></span>

<span data-ttu-id="dd643-226">Wenn `Select-String` in einer Textzeile mehr als eine Übereinstimmung findet, gibt Sie immer noch nur ein **matchinfo** -Objekt für die Zeile aus, aber die **Matches** -Eigenschaft des-Objekts enthält alle Übereinstimmungen.</span><span class="sxs-lookup"><span data-stu-id="dd643-226">When `Select-String` finds more than one match in a line of text, it still emits only one **MatchInfo** object for the line, but the **Matches** property of the object contains all the matches.</span></span>

> [!NOTE]
> <span data-ttu-id="dd643-227">Dieser Parameter wird ignoriert, wenn er in Kombination mit dem **simplematch** -Parameter verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="dd643-227">This parameter is ignored when used in combination with the **SimpleMatch** parameter.</span></span> <span data-ttu-id="dd643-228">Wenn Sie alle Übereinstimmungen zurückgeben möchten und das gesuchte Muster reguläre Ausdruckszeichen enthält, müssen Sie diese Zeichen mit Escapezeichen versehen, anstatt **simplematch** zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="dd643-228">If you wish to return all matches and the pattern that you are searching for contains regular expression characters, you must escape those characters rather than using **SimpleMatch**.</span></span> <span data-ttu-id="dd643-229">Weitere Informationen zum Escapezeichen für reguläre Ausdrücke finden Sie unter [about_Regular_Expressions](../Microsoft.PowerShell.Core/About/about_Regular_Expressions.md) .</span><span class="sxs-lookup"><span data-stu-id="dd643-229">See [about_Regular_Expressions](../Microsoft.PowerShell.Core/About/about_Regular_Expressions.md) for more information about escaping regular expressions.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="dd643-230">-CaseSensitive</span><span class="sxs-lookup"><span data-stu-id="dd643-230">-CaseSensitive</span></span>

<span data-ttu-id="dd643-231">Gibt an, dass die Groß-/Kleinschreibung der Cmdlet-Übereinstimmungen beachtet</span><span class="sxs-lookup"><span data-stu-id="dd643-231">Indicates that the cmdlet matches are case-sensitive.</span></span> <span data-ttu-id="dd643-232">Standardmäßig wird die Groß-/Kleinschreibung nicht beachtet.</span><span class="sxs-lookup"><span data-stu-id="dd643-232">By default, matches aren't case-sensitive.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="dd643-233">-Context</span><span class="sxs-lookup"><span data-stu-id="dd643-233">-Context</span></span>

<span data-ttu-id="dd643-234">Erfasst die angegebene Anzahl von Zeilen vor und nach der Zeile, die mit dem Muster übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="dd643-234">Captures the specified number of lines before and after the line that matches the pattern.</span></span>

<span data-ttu-id="dd643-235">Wenn Sie eine Zahl als Wert dieses Parameters eingeben, bestimmt diese Zahl die Anzahl der vor und nach der Übereinstimmung erfassten Zeilen.</span><span class="sxs-lookup"><span data-stu-id="dd643-235">If you enter one number as the value of this parameter, that number determines the number of lines captured before and after the match.</span></span> <span data-ttu-id="dd643-236">Wenn Sie zwei Zahlen als Wert eingeben, bestimmt die erste Zahl die Anzahl der Zeilen vor der Übereinstimmung und die zweite Zahl die Anzahl der Zeilen nach der Übereinstimmung.</span><span class="sxs-lookup"><span data-stu-id="dd643-236">If you enter two numbers as the value, the first number determines the number of lines before the match and the second number determines the number of lines after the match.</span></span> <span data-ttu-id="dd643-237">Beispiel: `-Context 2,3`.</span><span class="sxs-lookup"><span data-stu-id="dd643-237">For example, `-Context 2,3`.</span></span>

<span data-ttu-id="dd643-238">In der Standard Anzeige werden Zeilen mit einer Entsprechung durch eine schließende spitze Klammer ( `>` ) (ASCII 62) in der ersten Spalte der Anzeige angegeben.</span><span class="sxs-lookup"><span data-stu-id="dd643-238">In the default display, lines with a match are indicated by a right angle bracket (`>`) (ASCII 62) in the first column of the display.</span></span> <span data-ttu-id="dd643-239">Nicht gekennzeichnete Zeilen stehen für Kontext.</span><span class="sxs-lookup"><span data-stu-id="dd643-239">Unmarked lines are the context.</span></span>

<span data-ttu-id="dd643-240">Der **Kontext** Parameter ändert nicht die Anzahl der Objekte, die von generiert werden `Select-String` .</span><span class="sxs-lookup"><span data-stu-id="dd643-240">The **Context** parameter doesn't change the number of objects generated by `Select-String`.</span></span>
<span data-ttu-id="dd643-241">`Select-String` generiert ein [matchinfo](/dotnet/api/microsoft.powershell.commands.matchinfo) -Objekt für jede Entsprechung.</span><span class="sxs-lookup"><span data-stu-id="dd643-241">`Select-String` generates one [MatchInfo](/dotnet/api/microsoft.powershell.commands.matchinfo) object for each match.</span></span> <span data-ttu-id="dd643-242">Der Kontext wird als Zeichen folgen Array in der **context** -Eigenschaft des Objekts gespeichert.</span><span class="sxs-lookup"><span data-stu-id="dd643-242">The context is stored as an array of strings in the **Context** property of the object.</span></span>

<span data-ttu-id="dd643-243">Wenn die Ausgabe eines `Select-String` Befehls in der Pipeline an einen anderen Befehl gesendet wird `Select-String` , durchsucht der empfangende Befehl nur den Text in der übereinstimmenden Zeile.</span><span class="sxs-lookup"><span data-stu-id="dd643-243">When the output of a `Select-String` command is sent down the pipeline to another `Select-String` command, the receiving command searches only the text in the matched line.</span></span> <span data-ttu-id="dd643-244">Die übereinstimmende Zeile ist der Wert der **Line** -Eigenschaft des **matchinfo** -Objekts und nicht der Text in den Kontext Zeilen.</span><span class="sxs-lookup"><span data-stu-id="dd643-244">The matched line is the value of the **Line** property of the **MatchInfo** object, not the text in the context lines.</span></span> <span data-ttu-id="dd643-245">Folglich ist der **Kontext** Parameter im empfangenden Befehl nicht gültig `Select-String` .</span><span class="sxs-lookup"><span data-stu-id="dd643-245">As a result, the **Context** parameter isn't valid on the receiving `Select-String` command.</span></span>

<span data-ttu-id="dd643-246">Wenn der Kontext eine Entsprechung enthält, enthält das **matchinfo** -Objekt für jede Übereinstimmung alle Kontext Zeilen, aber die überlappenden Zeilen werden nur einmal in der Anzeige angezeigt.</span><span class="sxs-lookup"><span data-stu-id="dd643-246">When the context includes a match, the **MatchInfo** object for each match includes all the context lines, but the overlapping lines appear only once in the display.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="dd643-247">-Kultur</span><span class="sxs-lookup"><span data-stu-id="dd643-247">-Culture</span></span>

<span data-ttu-id="dd643-248">Gibt einen Kultur Namen an, der dem angegebenen Muster entspricht.</span><span class="sxs-lookup"><span data-stu-id="dd643-248">Specifies a culture name to match the specified pattern.</span></span> <span data-ttu-id="dd643-249">Der **Culture** -Parameter muss mit dem **simplematch** -Parameter verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="dd643-249">The **Culture** parameter must be used with the **SimpleMatch** parameter.</span></span> <span data-ttu-id="dd643-250">Das Standardverhalten verwendet die Kultur des aktuellen PowerShell-Runspace (Session).</span><span class="sxs-lookup"><span data-stu-id="dd643-250">The default behavior uses the culture of the current PowerShell runspace (session).</span></span>

<span data-ttu-id="dd643-251">Um eine Liste aller unterstützten Kulturen zu erhalten, verwenden Sie den `Get-Culture -ListAvailable` Befehl.</span><span class="sxs-lookup"><span data-stu-id="dd643-251">To get a list of all supported cultures, use `Get-Culture -ListAvailable` command.</span></span>

<span data-ttu-id="dd643-252">Außerdem akzeptiert dieser Parameter die folgenden Argumente:</span><span class="sxs-lookup"><span data-stu-id="dd643-252">In addition, this parameter accepts the following arguments:</span></span>

- <span data-ttu-id="dd643-253">CurrentCulture, das ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="dd643-253">CurrentCulture, that is default;</span></span>
- <span data-ttu-id="dd643-254">Ordinal, bei dem es sich um einen nicht linguistischen binären Vergleich handelt.</span><span class="sxs-lookup"><span data-stu-id="dd643-254">Ordinal, that is non-linguistic binary comparison;</span></span>
- <span data-ttu-id="dd643-255">Invariant, das ist ein Kultur unabhängiger Vergleich.</span><span class="sxs-lookup"><span data-stu-id="dd643-255">Invariant, that is culture independent comparison.</span></span>

<span data-ttu-id="dd643-256">Mit dem `Select-String -Culture Ordinal -CaseSensitive -SimpleMatch` Befehl erhalten Sie den schnellsten binären Vergleich.</span><span class="sxs-lookup"><span data-stu-id="dd643-256">With `Select-String -Culture Ordinal -CaseSensitive -SimpleMatch` command you gets fastest binary comparison.</span></span>

<span data-ttu-id="dd643-257">Der **Culture** -Parameter verwendet die Vervollständigung mit der Tab-Taste, um durch die Liste der Argumente, die die verfügbaren Kulturen angeben</span><span class="sxs-lookup"><span data-stu-id="dd643-257">The **Culture** parameter uses tab completion to scroll through the list of arguments that specify the available cultures.</span></span> <span data-ttu-id="dd643-258">Um alle verfügbaren Argumente aufzulisten, verwenden Sie den folgenden Befehl:</span><span class="sxs-lookup"><span data-stu-id="dd643-258">To list all available arguments, use the following command:</span></span>

`(Get-Command Select-String).Parameters.Culture.Attributes.ValidValues`

<span data-ttu-id="dd643-259">Weitere Informationen zur .net CultureInfo.Name-Eigenschaft finden Sie unter [CultureInfo.Name](/dotnet/api//system.globalization.cultureinfo.name).</span><span class="sxs-lookup"><span data-stu-id="dd643-259">For more information about .NET CultureInfo.Name property, see [CultureInfo.Name](/dotnet/api//system.globalization.cultureinfo.name).</span></span>

<span data-ttu-id="dd643-260">Der **Culture** -Parameter wurde in PowerShell 7 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="dd643-260">The **Culture** parameter was introduced in PowerShell 7.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Culture of the current PowerShell session
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="dd643-261">-Codierung</span><span class="sxs-lookup"><span data-stu-id="dd643-261">-Encoding</span></span>

<span data-ttu-id="dd643-262">Gibt den Typ der Codierung für die Zieldatei an.</span><span class="sxs-lookup"><span data-stu-id="dd643-262">Specifies the type of encoding for the target file.</span></span> <span data-ttu-id="dd643-263">Der Standardwert ist `utf8NoBOM`.</span><span class="sxs-lookup"><span data-stu-id="dd643-263">The default value is `utf8NoBOM`.</span></span>

<span data-ttu-id="dd643-264">Die zulässigen Werte für diesen Parameter lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="dd643-264">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="dd643-265">`ascii`: Verwendet die Codierung für den ASCII-Zeichensatz (7-Bit).</span><span class="sxs-lookup"><span data-stu-id="dd643-265">`ascii`: Uses the encoding for the ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="dd643-266">`bigendianunicode`: Codiert im UTF-16-Format unter Verwendung der Big-Endian-Byte Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="dd643-266">`bigendianunicode`: Encodes in UTF-16 format using the big-endian byte order.</span></span>
- <span data-ttu-id="dd643-267">`bigendianutf32`: Codiert im UTF-32-Format unter Verwendung der Big-Endian-Byte Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="dd643-267">`bigendianutf32`: Encodes in UTF-32 format using the big-endian byte order.</span></span>
- <span data-ttu-id="dd643-268">`oem`: Verwendet die Standard Codierung für MS-DOS-und-Konsolen Programme.</span><span class="sxs-lookup"><span data-stu-id="dd643-268">`oem`: Uses the default encoding for MS-DOS and console programs.</span></span>
- <span data-ttu-id="dd643-269">`unicode`: Codiert im UTF-16-Format unter Verwendung der Little-Endian-Byte Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="dd643-269">`unicode`: Encodes in UTF-16 format using the little-endian byte order.</span></span>
- <span data-ttu-id="dd643-270">`utf7`: Codiert im UTF-7-Format.</span><span class="sxs-lookup"><span data-stu-id="dd643-270">`utf7`: Encodes in UTF-7 format.</span></span>
- <span data-ttu-id="dd643-271">`utf8`: Codiert im UTF-8-Format.</span><span class="sxs-lookup"><span data-stu-id="dd643-271">`utf8`: Encodes in UTF-8 format.</span></span>
- <span data-ttu-id="dd643-272">`utf8BOM`: Codiert im UTF-8-Format mit Byte Reihenfolge Markierung (BOM).</span><span class="sxs-lookup"><span data-stu-id="dd643-272">`utf8BOM`: Encodes in UTF-8 format with Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="dd643-273">`utf8NoBOM`: Codiert im UTF-8-Format ohne Byte Reihenfolge-Markierung (BOM).</span><span class="sxs-lookup"><span data-stu-id="dd643-273">`utf8NoBOM`: Encodes in UTF-8 format without Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="dd643-274">`utf32`: Codiert im UTF-32-Format.</span><span class="sxs-lookup"><span data-stu-id="dd643-274">`utf32`: Encodes in UTF-32 format.</span></span>

<span data-ttu-id="dd643-275">Ab PowerShell 6,2 ermöglicht der **Encoding** -Parameter auch numerische IDs registrierter Codepages (z `-Encoding 1251` . b.) oder Zeichen folgen Namen registrierter Codepages (z `-Encoding "windows-1251"` . b.).</span><span class="sxs-lookup"><span data-stu-id="dd643-275">Beginning with PowerShell 6.2, the **Encoding** parameter also allows numeric IDs of registered code pages (like `-Encoding 1251`) or string names of registered code pages (like `-Encoding "windows-1251"`).</span></span> <span data-ttu-id="dd643-276">Weitere Informationen finden Sie in der .NET-Dokumentation für [Encoding. Codepage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).</span><span class="sxs-lookup"><span data-stu-id="dd643-276">For more information, see the .NET documentation for [Encoding.CodePage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).</span></span>

> [!NOTE]
> <span data-ttu-id="dd643-277">**UTF-7** _ wird nicht mehr für die Verwendung von empfohlen.</span><span class="sxs-lookup"><span data-stu-id="dd643-277">**UTF-7** _ is no longer recommended to use.</span></span> <span data-ttu-id="dd643-278">In PowerShell 7,1 wird eine Warnung geschrieben, wenn Sie `utf7` für den Parameter "_ \*Encoding\*\*" angeben.</span><span class="sxs-lookup"><span data-stu-id="dd643-278">In PowerShell 7.1, a warning is written if you specify `utf7` for the _ *Encoding*\* parameter.</span></span>

```yaml
Type: System.Text.Encoding
Parameter Sets: (All)
Aliases:
Accepted values: ASCII, BigEndianUnicode, BigEndianUTF32, OEM, Unicode, UTF7, UTF8, UTF8BOM, UTF8NoBOM, UTF32

Required: False
Position: Named
Default value: UTF8NoBOM
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="dd643-279">-Ausschließen</span><span class="sxs-lookup"><span data-stu-id="dd643-279">-Exclude</span></span>

<span data-ttu-id="dd643-280">Schließen Sie die angegebenen Elemente aus.</span><span class="sxs-lookup"><span data-stu-id="dd643-280">Exclude the specified items.</span></span> <span data-ttu-id="dd643-281">Der Wert dieses Parameters qualifiziert den **Path**-Parameter.</span><span class="sxs-lookup"><span data-stu-id="dd643-281">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="dd643-282">Geben Sie ein Pfad Element oder-Muster ein, z `*.txt` . b..</span><span class="sxs-lookup"><span data-stu-id="dd643-282">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="dd643-283">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="dd643-283">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="dd643-284">-Include</span><span class="sxs-lookup"><span data-stu-id="dd643-284">-Include</span></span>

<span data-ttu-id="dd643-285">Schließt die angegebenen Elemente ein.</span><span class="sxs-lookup"><span data-stu-id="dd643-285">Includes the specified items.</span></span> <span data-ttu-id="dd643-286">Der Wert dieses Parameters qualifiziert den **Path**-Parameter.</span><span class="sxs-lookup"><span data-stu-id="dd643-286">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="dd643-287">Geben Sie ein Pfad Element oder-Muster ein, z `*.txt` . b..</span><span class="sxs-lookup"><span data-stu-id="dd643-287">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="dd643-288">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="dd643-288">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="dd643-289">-InputObject</span><span class="sxs-lookup"><span data-stu-id="dd643-289">-InputObject</span></span>

<span data-ttu-id="dd643-290">Gibt den zu durchsuchenden Text an.</span><span class="sxs-lookup"><span data-stu-id="dd643-290">Specifies the text to be searched.</span></span> <span data-ttu-id="dd643-291">Geben Sie eine Variable ein, die den Text enthält, oder geben Sie einen Befehl oder Ausdruck ein, der den Text abruft.</span><span class="sxs-lookup"><span data-stu-id="dd643-291">Enter a variable that contains the text, or type a command or expression that gets the text.</span></span>

<span data-ttu-id="dd643-292">Die Verwendung des **Inputobject** -Parameters entspricht nicht dem Senden von Zeichen folgen in der Pipeline an `Select-String` .</span><span class="sxs-lookup"><span data-stu-id="dd643-292">Using the **InputObject** parameter isn't the same as sending strings down the pipeline to `Select-String`.</span></span>

<span data-ttu-id="dd643-293">Wenn Sie mehr als eine Zeichenfolge an das `Select-String` Cmdlet übergeben, sucht Sie in jeder Zeichenfolge nach dem angegebenen Text und gibt jede Zeichenfolge zurück, die den Suchtext enthält.</span><span class="sxs-lookup"><span data-stu-id="dd643-293">When you pipe more than one string to the `Select-String` cmdlet, it searches for the specified text in each string and returns each string that contains the search text.</span></span>

<span data-ttu-id="dd643-294">Wenn Sie den **Inputobject** -Parameter verwenden, um eine Auflistung von Zeichen folgen zu senden, `Select-String` behandelt die Auflistung als einzelne kombinierte Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="dd643-294">When you use the **InputObject** parameter to submit a collection of strings, `Select-String` treats the collection as a single combined string.</span></span> <span data-ttu-id="dd643-295">`Select-String` Gibt die Zeichen folgen als Einheit zurück, wenn der Suchtext in einer beliebigen Zeichenfolge gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="dd643-295">`Select-String` returns the strings as a unit if it finds the search text in any string.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: Object, ObjectRaw
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="dd643-296">-List</span><span class="sxs-lookup"><span data-stu-id="dd643-296">-List</span></span>

<span data-ttu-id="dd643-297">Nur die erste Instanz von übereinstimmenden Text wird von jeder Eingabedatei zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="dd643-297">Only the first instance of matching text is returned from each input file.</span></span> <span data-ttu-id="dd643-298">Dies ist die effizienteste Methode zum Abrufen einer Liste von Dateien, die Inhalte enthalten, die mit dem regulären Ausdruck übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="dd643-298">This is the most efficient way to retrieve a list of files that have contents matching the regular expression.</span></span>

<span data-ttu-id="dd643-299">Standardmäßig `Select-String` gibt ein **matchinfo** -Objekt für jede gefundene Entsprechung zurück.</span><span class="sxs-lookup"><span data-stu-id="dd643-299">By default, `Select-String` returns a **MatchInfo** object for each match it finds.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="dd643-300">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="dd643-300">-LiteralPath</span></span>

<span data-ttu-id="dd643-301">Gibt den Pfad zu den Dateien an, die durchsucht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="dd643-301">Specifies the path to the files to be searched.</span></span> <span data-ttu-id="dd643-302">Der Wert des **literalpath** -Parameters wird genau so verwendet, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="dd643-302">The value of the **LiteralPath** parameter is used exactly as it's typed.</span></span> <span data-ttu-id="dd643-303">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="dd643-303">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="dd643-304">Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="dd643-304">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="dd643-305">Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="dd643-305">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span> <span data-ttu-id="dd643-306">Weitere Informationen finden Sie unter [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="dd643-306">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralFileRaw, LiteralFile
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="dd643-307">-Nohervorzuheben</span><span class="sxs-lookup"><span data-stu-id="dd643-307">-NoEmphasis</span></span>

<span data-ttu-id="dd643-308">Standardmäßig wird `Select-String` die Zeichenfolge, die mit dem Muster übereinstimmt, das  Sie nach dem Muster Parameter gesucht haben, hervorgehoben</span><span class="sxs-lookup"><span data-stu-id="dd643-308">By default, `Select-String` highlights the string that matches the pattern you searched for with the **Pattern** parameter.</span></span> <span data-ttu-id="dd643-309">Der **noakzente** -Parameter deaktiviert die Hervorhebung.</span><span class="sxs-lookup"><span data-stu-id="dd643-309">The **NoEmphasis** parameter disables the highlighting.</span></span>

<span data-ttu-id="dd643-310">Der Schwerpunkt verwendet negative Farben basierend auf Ihren PowerShell-Hintergrund-und Textfarben.</span><span class="sxs-lookup"><span data-stu-id="dd643-310">The emphasis uses negative colors based on your PowerShell background and text colors.</span></span> <span data-ttu-id="dd643-311">Wenn Ihre PowerShell-Farben beispielsweise ein schwarzer Hintergrund mit weißem Text sind.</span><span class="sxs-lookup"><span data-stu-id="dd643-311">For example, if your PowerShell colors are a black background with white text.</span></span> <span data-ttu-id="dd643-312">Der Schwerpunkt liegt auf einem weißen Hintergrund mit schwarzem Text.</span><span class="sxs-lookup"><span data-stu-id="dd643-312">The emphasis is a white background with black text.</span></span>

<span data-ttu-id="dd643-313">Dieser Parameter wurde in PowerShell 7 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="dd643-313">This parameter was introduced in PowerShell 7.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="dd643-314">-Notmatch</span><span class="sxs-lookup"><span data-stu-id="dd643-314">-NotMatch</span></span>

<span data-ttu-id="dd643-315">Der **notmatch** -Parameter sucht nach Text, der nicht dem angegebenen Muster entspricht.</span><span class="sxs-lookup"><span data-stu-id="dd643-315">The **NotMatch** parameter finds text that doesn't match the specified pattern.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="dd643-316">-Path</span><span class="sxs-lookup"><span data-stu-id="dd643-316">-Path</span></span>

<span data-ttu-id="dd643-317">Gibt den Pfad zu den Dateien an, die durchsucht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="dd643-317">Specifies the path to the files to search.</span></span> <span data-ttu-id="dd643-318">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="dd643-318">Wildcards are permitted.</span></span> <span data-ttu-id="dd643-319">Der Standardspeicherort ist das lokale Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="dd643-319">The default location is the local directory.</span></span>

<span data-ttu-id="dd643-320">Geben Sie Dateien im Verzeichnis an, z `log1.txt` `*.doc` . b., oder `*.*` .</span><span class="sxs-lookup"><span data-stu-id="dd643-320">Specify files in the directory, such as `log1.txt`, `*.doc`, or `*.*`.</span></span> <span data-ttu-id="dd643-321">Wenn Sie nur das Verzeichnis angeben, führt der Befehl zu einem Fehler.</span><span class="sxs-lookup"><span data-stu-id="dd643-321">If you specify only a directory, the command fails.</span></span>

```yaml
Type: System.String[]
Parameter Sets: File, FileRaw
Aliases:

Required: True
Position: 1
Default value: Local directory
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="dd643-322">-Muster</span><span class="sxs-lookup"><span data-stu-id="dd643-322">-Pattern</span></span>

<span data-ttu-id="dd643-323">Gibt den Text an, der in jeder Zeile gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="dd643-323">Specifies the text to find on each line.</span></span> <span data-ttu-id="dd643-324">Der Pattern-Wert wird als regulärer Ausdruck behandelt.</span><span class="sxs-lookup"><span data-stu-id="dd643-324">The pattern value is treated as a regular expression.</span></span>

<span data-ttu-id="dd643-325">Informationen zu regulären Ausdrücken finden Sie unter [about_Regular_Expressions](../Microsoft.PowerShell.Core/About/about_Regular_Expressions.md).</span><span class="sxs-lookup"><span data-stu-id="dd643-325">To learn about regular expressions, see [about_Regular_Expressions](../Microsoft.PowerShell.Core/About/about_Regular_Expressions.md).</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="dd643-326">-Quiet</span><span class="sxs-lookup"><span data-stu-id="dd643-326">-Quiet</span></span>

<span data-ttu-id="dd643-327">Gibt an, dass das Cmdlet einen booleschen Wert (true oder false) anstelle eines **matchinfo** -Objekts zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="dd643-327">Indicates that the cmdlet returns a Boolean value (True or False), instead of a **MatchInfo** object.</span></span> <span data-ttu-id="dd643-328">Der Wert ist "true", wenn das Muster gefunden wurde. Andernfalls ist der Wert false.</span><span class="sxs-lookup"><span data-stu-id="dd643-328">The value is True if the pattern is found; otherwise the value is False.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: File, Object, LiteralFile
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="dd643-329">-RAW</span><span class="sxs-lookup"><span data-stu-id="dd643-329">-Raw</span></span>

<span data-ttu-id="dd643-330">Bewirkt, dass das Cmdlet nur die übereinstimmenden Zeichen folgen anstelle von **matchinfo** -Objekten ausgibt.</span><span class="sxs-lookup"><span data-stu-id="dd643-330">Causes the cmdlet to output only the matching strings, rather than **MatchInfo** objects.</span></span> <span data-ttu-id="dd643-331">Dies ist das Verhalten, das den Befehlen von UNIX **grep** oder Windows **findstr.exe** am ähnlichsten ist.</span><span class="sxs-lookup"><span data-stu-id="dd643-331">This is the results in behavior that's the most similar to the Unix **grep** or Windows **findstr.exe** commands.</span></span>

<span data-ttu-id="dd643-332">Dieser Parameter wurde in PowerShell 7 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="dd643-332">This parameter was introduced in PowerShell 7.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ObjectRaw, FileRaw, LiteralFileRaw
Aliases:

Required: True
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="dd643-333">-Simplematch</span><span class="sxs-lookup"><span data-stu-id="dd643-333">-SimpleMatch</span></span>

<span data-ttu-id="dd643-334">Gibt an, dass das Cmdlet anstelle einer regulären Ausdrucks Übereinstimmung eine einfache Entsprechung verwendet.</span><span class="sxs-lookup"><span data-stu-id="dd643-334">Indicates that the cmdlet uses a simple match rather than a regular expression match.</span></span> <span data-ttu-id="dd643-335">In einer einfachen `Select-String` Suche durchsucht die Eingabe nach dem Text im **Pattern** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="dd643-335">In a simple match, `Select-String` searches the input for the text in the **Pattern** parameter.</span></span> <span data-ttu-id="dd643-336">Er interpretiert den Wert des **Pattern** -Parameters nicht als Anweisung für reguläre Ausdrücke.</span><span class="sxs-lookup"><span data-stu-id="dd643-336">It doesn't interpret the value of the **Pattern** parameter as a regular expression statement.</span></span>

<span data-ttu-id="dd643-337">Wenn **simplematch** verwendet wird, ist auch die **Matches** -Eigenschaft des zurückgegebenen **matchinfo** -Objekts leer.</span><span class="sxs-lookup"><span data-stu-id="dd643-337">Also, when **SimpleMatch** is used, the **Matches** property of the **MatchInfo** object returned is empty.</span></span>

> [!NOTE]
> <span data-ttu-id="dd643-338">Wenn dieser Parameter mit dem **allmatches** -Parameter verwendet wird, wird **allmatches** ignoriert.</span><span class="sxs-lookup"><span data-stu-id="dd643-338">When this parameter is used with the **AllMatches** parameter, the **AllMatches** is ignored.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="dd643-339">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="dd643-339">CommonParameters</span></span>

<span data-ttu-id="dd643-340">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="dd643-340">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="dd643-341">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="dd643-341">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="dd643-342">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="dd643-342">INPUTS</span></span>

### <span data-ttu-id="dd643-343">System. Management. Automation. psobject</span><span class="sxs-lookup"><span data-stu-id="dd643-343">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="dd643-344">Sie können jedes beliebige Objekt über die Pipeline  an übergeben `Select-String` .</span><span class="sxs-lookup"><span data-stu-id="dd643-344">You can pipe any object that has a **ToString** method to `Select-String`.</span></span>

## <span data-ttu-id="dd643-345">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="dd643-345">OUTPUTS</span></span>

### <span data-ttu-id="dd643-346">Microsoft. PowerShell. Commands. matchinfo, System. Boolean, System. String</span><span class="sxs-lookup"><span data-stu-id="dd643-346">Microsoft.PowerShell.Commands.MatchInfo, System.Boolean, System.String</span></span>

<span data-ttu-id="dd643-347">Standardmäßig handelt es sich bei der Ausgabe um einen Satz von **matchinfo** -Objekten mit einer für jede gefundene Entsprechung.</span><span class="sxs-lookup"><span data-stu-id="dd643-347">By default, the output is a set of **MatchInfo** objects with one for each match found.</span></span> <span data-ttu-id="dd643-348">Wenn Sie den **quiet** -Parameter verwenden, ist die Ausgabe ein **boolescher** Wert, der angibt, ob das Muster gefunden wurde.</span><span class="sxs-lookup"><span data-stu-id="dd643-348">If you use the **Quiet** parameter, the output is a **Boolean** value indicating whether the pattern was found.</span></span>
<span data-ttu-id="dd643-349">Wenn Sie den **RAW** -Parameter verwenden, handelt es sich bei der Ausgabe um einen Satz von **Zeichen** folgen Objekten, die dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="dd643-349">If you use the **Raw** parameter, the output is a set of **String** objects that match the pattern.</span></span>

## <span data-ttu-id="dd643-350">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="dd643-350">NOTES</span></span>

<span data-ttu-id="dd643-351">`Select-String` ähnelt **grep** in UNIX oder **findstr.exe** in Windows.</span><span class="sxs-lookup"><span data-stu-id="dd643-351">`Select-String` is similar to **grep** in UNIX or **findstr.exe** in Windows.</span></span>

<span data-ttu-id="dd643-352">Der **SLS** -Alias für das `Select-String` Cmdlet wurde in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="dd643-352">The **sls** alias for the `Select-String` cmdlet was introduced in PowerShell 3.0.</span></span>

> [!NOTE]
> <span data-ttu-id="dd643-353">Gemäß [genehmigten Verben für PowerShell-Befehle](/powershell/scripting/developer/cmdlet/approved-verbs-for-windows-powershell-commands)ist das offizielle Alias Präfix für `Select-*` Cmdlets `sc` , nicht `sl` .</span><span class="sxs-lookup"><span data-stu-id="dd643-353">According to [Approved Verbs for PowerShell Commands](/powershell/scripting/developer/cmdlet/approved-verbs-for-windows-powershell-commands), the official alias prefix for `Select-*` cmdlets is `sc`, not `sl`.</span></span> <span data-ttu-id="dd643-354">Daher sollte der richtige Alias für `Select-String` lauten `scs` , nicht `sls` .</span><span class="sxs-lookup"><span data-stu-id="dd643-354">Therefore, the proper alias for `Select-String` should be `scs`, not `sls`.</span></span> <span data-ttu-id="dd643-355">Dies ist eine Ausnahme von dieser Regel.</span><span class="sxs-lookup"><span data-stu-id="dd643-355">This is an exception to this rule.</span></span>

<span data-ttu-id="dd643-356">`Select-String`Wenn Sie verwenden möchten, geben Sie den Text ein, der als Wert des **Pattern** -Parameters gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="dd643-356">To use `Select-String`, type the text that you want to find as the value of the **Pattern** parameter.</span></span> <span data-ttu-id="dd643-357">Um den zu durchsuchenden Text anzugeben, verwenden Sie die folgenden Kriterien:</span><span class="sxs-lookup"><span data-stu-id="dd643-357">To specify the text to be searched, use the following criteria:</span></span>

- <span data-ttu-id="dd643-358">Geben Sie den Text in eine Zeichenfolge in Anführungszeichen ein, und übergeben Sie ihn dann an `Select-String` .</span><span class="sxs-lookup"><span data-stu-id="dd643-358">Type the text in a quoted string, and then pipe it to `Select-String`.</span></span>
- <span data-ttu-id="dd643-359">Speichern Sie eine Text Zeichenfolge in einer Variablen, und geben Sie dann die Variable als Wert des **Inputobject** -Parameters an.</span><span class="sxs-lookup"><span data-stu-id="dd643-359">Store a text string in a variable, and then specify the variable as the value of the **InputObject** parameter.</span></span>
- <span data-ttu-id="dd643-360">Wenn der Text in Dateien gespeichert wird, verwenden Sie den **path** -Parameter, um den Pfad zu den Dateien anzugeben.</span><span class="sxs-lookup"><span data-stu-id="dd643-360">If the text is stored in files, use the **Path** parameter to specify the path to the files.</span></span>

<span data-ttu-id="dd643-361">Standardmäßig `Select-String` interpretiert den Wert des **Pattern** -Parameters als regulären Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="dd643-361">By default, `Select-String` interprets the value of the **Pattern** parameter as a regular expression.</span></span> <span data-ttu-id="dd643-362">Weitere Informationen finden Sie unter [about_Regular_Expressions](../Microsoft.PowerShell.Core/About/about_Regular_Expressions.md).</span><span class="sxs-lookup"><span data-stu-id="dd643-362">For more information, see [about_Regular_Expressions](../Microsoft.PowerShell.Core/About/about_Regular_Expressions.md).</span></span> <span data-ttu-id="dd643-363">Sie können den **simplematch** -Parameter verwenden, um den übereinstimmenden regulären Ausdruck zu überschreiben.</span><span class="sxs-lookup"><span data-stu-id="dd643-363">You can use the **SimpleMatch** parameter to override the regular expression matching.</span></span> <span data-ttu-id="dd643-364">Der **simplematch** -Parameter sucht in der Eingabe nach Instanzen des Werts des **Pattern** -Parameters.</span><span class="sxs-lookup"><span data-stu-id="dd643-364">The **SimpleMatch** parameter finds instances of the value of the **Pattern** parameter in the input.</span></span>

<span data-ttu-id="dd643-365">Die Standardausgabe von `Select-String` ist ein **matchinfo** -Objekt, das ausführliche Informationen zu den Übereinstimmungen enthält.</span><span class="sxs-lookup"><span data-stu-id="dd643-365">The default output of `Select-String` is a **MatchInfo** object, which includes detailed information about the matches.</span></span> <span data-ttu-id="dd643-366">Die Informationen im-Objekt sind nützlich, wenn Sie in Dateien nach Text suchen, da **matchinfo** -Objekte über Eigenschaften wie **Dateiname** und **Zeile** verfügen.</span><span class="sxs-lookup"><span data-stu-id="dd643-366">The information in the object is useful when you're searching for text in files, because **MatchInfo** objects have properties such as **Filename** and **Line**.</span></span> <span data-ttu-id="dd643-367">Wenn die Eingabe nicht aus der Datei besteht, ist der Wert dieser Parameter **InputStream**.</span><span class="sxs-lookup"><span data-stu-id="dd643-367">When the input isn't from the file, the value of these parameters is **InputStream**.</span></span>

<span data-ttu-id="dd643-368">Wenn Sie die Informationen im **matchinfo** -Objekt nicht benötigen, verwenden Sie den **quiet** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="dd643-368">If you don't need the information in the **MatchInfo** object, use the **Quiet** parameter.</span></span> <span data-ttu-id="dd643-369">Der **quiet** -Parameter gibt einen booleschen Wert (true oder false) zurück, um anzugeben, ob eine Entsprechung gefunden wurde, anstelle eines **matchinfo** -Objekts.</span><span class="sxs-lookup"><span data-stu-id="dd643-369">The **Quiet** parameter returns a Boolean value (True or False) to indicate whether it found a match, instead of a **MatchInfo** object.</span></span>

<span data-ttu-id="dd643-370">Beim Abgleichen `Select-String` von Ausdrücken verwendet die aktuelle Kultur, die für das System festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="dd643-370">When matching phrases, `Select-String` uses the current culture that is set for the system.</span></span> <span data-ttu-id="dd643-371">Verwenden Sie das-Cmdlet, um die aktuelle Kultur zu ermitteln `Get-Culture` .</span><span class="sxs-lookup"><span data-stu-id="dd643-371">To find the current culture, use the `Get-Culture` cmdlet.</span></span>

<span data-ttu-id="dd643-372">Um die Eigenschaften eines **matchinfo** -Objekts zu ermitteln, geben Sie den folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="dd643-372">To find the properties of a **MatchInfo** object, type the following command:</span></span>

`Select-String -Path test.txt -Pattern 'test' | Get-Member | Format-List -Property *`

## <span data-ttu-id="dd643-373">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="dd643-373">RELATED LINKS</span></span>

[<span data-ttu-id="dd643-374">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="dd643-374">about_Automatic_Variables</span></span>](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md)

[<span data-ttu-id="dd643-375">about_Comparison_Operators</span><span class="sxs-lookup"><span data-stu-id="dd643-375">about_Comparison_Operators</span></span>](../Microsoft.PowerShell.Core/About/about_Comparison_Operators.md)

[<span data-ttu-id="dd643-376">about_Functions</span><span class="sxs-lookup"><span data-stu-id="dd643-376">about_Functions</span></span>](../Microsoft.PowerShell.Core/About/about_Functions.md)

[<span data-ttu-id="dd643-377">about_Quoting_Rules</span><span class="sxs-lookup"><span data-stu-id="dd643-377">about_Quoting_Rules</span></span>](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)

[<span data-ttu-id="dd643-378">about_Regular_Expressions</span><span class="sxs-lookup"><span data-stu-id="dd643-378">about_Regular_Expressions</span></span>](../Microsoft.PowerShell.Core/About/about_Regular_Expressions.md)

[<span data-ttu-id="dd643-379">Get-Alias</span><span class="sxs-lookup"><span data-stu-id="dd643-379">Get-Alias</span></span>](Get-Alias.md)

[<span data-ttu-id="dd643-380">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="dd643-380">Get-ChildItem</span></span>](../Microsoft.PowerShell.Management/Get-ChildItem.md)

[<span data-ttu-id="dd643-381">Get-Command</span><span class="sxs-lookup"><span data-stu-id="dd643-381">Get-Command</span></span>](../Microsoft.PowerShell.Core/Get-Command.md)

[<span data-ttu-id="dd643-382">Get-Member</span><span class="sxs-lookup"><span data-stu-id="dd643-382">Get-Member</span></span>](Get-Member.md)

[<span data-ttu-id="dd643-383">Get-WinEvent</span><span class="sxs-lookup"><span data-stu-id="dd643-383">Get-WinEvent</span></span>](../Microsoft.PowerShell.Diagnostics/Get-WinEvent.md)

[<span data-ttu-id="dd643-384">Out-File</span><span class="sxs-lookup"><span data-stu-id="dd643-384">Out-File</span></span>](Out-File.md)

