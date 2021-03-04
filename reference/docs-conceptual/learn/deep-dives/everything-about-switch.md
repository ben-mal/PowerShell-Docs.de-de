---
title: Alles, was Sie schon immer über die switch-Anweisung wissen wollten
description: Die switch-Anweisung in PowerShell bietet Features, die es in anderen Sprachen nicht gibt.
ms.date: 03/01/2021
ms.custom: contributor-KevinMarquette
ms.openlocfilehash: f6baa624285557452a2b95150b2c4de1ab274f27
ms.sourcegitcommit: 1dfd5554b70c7e8f4e3df19e29c384a9c0a4b227
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/03/2021
ms.locfileid: "101686010"
---
# <a name="everything-you-ever-wanted-to-know-about-the-switch-statement"></a><span data-ttu-id="9468e-103">Alles, was Sie schon immer über die switch-Anweisung wissen wollten</span><span class="sxs-lookup"><span data-stu-id="9468e-103">Everything you ever wanted to know about the switch statement</span></span>

<span data-ttu-id="9468e-104">Wie viele andere Sprachen bietet PowerShell Befehle zur Ablaufsteuerung der Ausführung innerhalb Ihrer Skripts.</span><span class="sxs-lookup"><span data-stu-id="9468e-104">Like many other languages, PowerShell has commands for controlling the flow of execution within your scripts.</span></span> <span data-ttu-id="9468e-105">Eine dieser Anweisungen ist die [switch][]-Anweisung in PowerShell mit Features, die es in anderen Sprachen nicht gibt.</span><span class="sxs-lookup"><span data-stu-id="9468e-105">One of those statements is the [switch][] statement and in PowerShell, it offers features that aren't found in other languages.</span></span> <span data-ttu-id="9468e-106">Heute beschäftigen wir uns eingehend mit dem Arbeiten mit der PowerShell-Anweisung `switch`.</span><span class="sxs-lookup"><span data-stu-id="9468e-106">Today, we take a deep dive into working with the PowerShell `switch`.</span></span>

> [!NOTE]
> <span data-ttu-id="9468e-107">Die [Originalversion][] dieses Artikels ist im Blog von [@KevinMarquette][] erschienen.</span><span class="sxs-lookup"><span data-stu-id="9468e-107">The [original version][] of this article appeared on the blog written by [@KevinMarquette][].</span></span> <span data-ttu-id="9468e-108">Das PowerShell-Team dankt Kevin Marquette, dass er diesen Inhalt mit uns teilt.</span><span class="sxs-lookup"><span data-stu-id="9468e-108">The PowerShell team thanks Kevin for sharing this content with us.</span></span> <span data-ttu-id="9468e-109">Weitere Informationen finden Sie in seinem Blog auf [PowerShellExplained.com][].</span><span class="sxs-lookup"><span data-stu-id="9468e-109">Please check out his blog at [PowerShellExplained.com][].</span></span>

## <a name="the-if-statement"></a><span data-ttu-id="9468e-110">Die Anweisung `if`</span><span class="sxs-lookup"><span data-stu-id="9468e-110">The `if` statement</span></span>

<span data-ttu-id="9468e-111">Eine der ersten Anweisungen, die Sie kennenlernen, ist die `if`-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="9468e-111">One of the first statements that you learn is the `if` statement.</span></span> <span data-ttu-id="9468e-112">Sie können einen Skriptblock ausführen, wenn eine Anweisung `$true` ist.</span><span class="sxs-lookup"><span data-stu-id="9468e-112">It lets you execute a script block if a statement is `$true`.</span></span>

``` powershell
if ( Test-Path $Path )
{
    Remove-Item $Path
}
```

<span data-ttu-id="9468e-113">Eine viel kompliziertere Logik ist möglich, wenn Sie die Anweisungen `elseif` und `else` nutzen.</span><span class="sxs-lookup"><span data-stu-id="9468e-113">You can have much more complicated logic by using `elseif` and `else` statements.</span></span> <span data-ttu-id="9468e-114">Hier ist ein Beispiel, bei dem ich einen numerischen Wert für einen Wochentag habe und ich den Namen als Zeichenfolge abrufen möchte.</span><span class="sxs-lookup"><span data-stu-id="9468e-114">Here is an example where I have a numeric value for day of the week and I want to get the name as a string.</span></span>

``` powershell
$day = 3

if ( $day -eq 0 ) { $result = 'Sunday'        }
elseif ( $day -eq 1 ) { $result = 'Monday'    }
elseif ( $day -eq 2 ) { $result = 'Tuesday'   }
elseif ( $day -eq 3 ) { $result = 'Wednesday' }
elseif ( $day -eq 4 ) { $result = 'Thursday'  }
elseif ( $day -eq 5 ) { $result = 'Friday'    }
elseif ( $day -eq 6 ) { $result = 'Saturday'  }

$result
```

```Output
Wednesday
```

<span data-ttu-id="9468e-115">Es stellt sich heraus, dass dies ein weit verbreitetes Muster ist und dass es viele Möglichkeiten gibt, damit umzugehen.</span><span class="sxs-lookup"><span data-stu-id="9468e-115">It turns out that this is a common pattern and there are many ways to deal with this.</span></span> <span data-ttu-id="9468e-116">Eine davon ist mit einer `switch`-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="9468e-116">One of them is with a `switch`.</span></span>

## <a name="switch-statement"></a><span data-ttu-id="9468e-117">switch-Anweisung</span><span class="sxs-lookup"><span data-stu-id="9468e-117">Switch statement</span></span>

<span data-ttu-id="9468e-118">Mit der `switch`-Anweisung können Sie eine Variable und eine Liste möglicher Werte angeben.</span><span class="sxs-lookup"><span data-stu-id="9468e-118">The `switch` statement allows you to provide a variable and a list of possible values.</span></span> <span data-ttu-id="9468e-119">Wenn der Wert mit der Variablen übereinstimmt, wird der zugehörige Skriptblock ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="9468e-119">If the value matches the variable, then its scriptblock is executed.</span></span>

``` powershell
$day = 3

switch ( $day )
{
    0 { $result = 'Sunday'    }
    1 { $result = 'Monday'    }
    2 { $result = 'Tuesday'   }
    3 { $result = 'Wednesday' }
    4 { $result = 'Thursday'  }
    5 { $result = 'Friday'    }
    6 { $result = 'Saturday'  }
}

$result
```

```Output
'Wednesday'
```

<span data-ttu-id="9468e-120">In diesem Beispiel entspricht der Wert von `$day` einem der numerischen Werte. Dann wird `$result` der richtige Name zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="9468e-120">For this example, the value of `$day` matches one of the numeric values, then the correct name is assigned to `$result`.</span></span> <span data-ttu-id="9468e-121">Wir weisen in diesem Beispiel nur eine Variable zu, aber jeder beliebige PowerShell-Befehl kann in diesen Skriptblöcken ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="9468e-121">We are only doing a variable assignment in this example, but any PowerShell can be executed in those script blocks.</span></span>

### <a name="assign-to-a-variable"></a><span data-ttu-id="9468e-122">Zuweisen zu einer Variablen</span><span class="sxs-lookup"><span data-stu-id="9468e-122">Assign to a variable</span></span>

<span data-ttu-id="9468e-123">Dieses letzte Beispiel kann auf andere Weise geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="9468e-123">We can write that last example in another way.</span></span>

``` powershell
$result = switch ( $day )
{
    0 { 'Sunday'    }
    1 { 'Monday'    }
    2 { 'Tuesday'   }
    3 { 'Wednesday' }
    4 { 'Thursday'  }
    5 { 'Friday'    }
    6 { 'Saturday'  }
}
```

<span data-ttu-id="9468e-124">Wir legen den Wert in der PowerShell-Pipeline ab und weisen ihn `$result` zu.</span><span class="sxs-lookup"><span data-stu-id="9468e-124">We are placing the value on the PowerShell pipeline and assigning it to the `$result`.</span></span> <span data-ttu-id="9468e-125">Dasselbe lässt sich mit den Anweisungen `if` und `foreach` realisieren.</span><span class="sxs-lookup"><span data-stu-id="9468e-125">You can do this same thing with the `if` and `foreach` statements.</span></span>

### <a name="default"></a><span data-ttu-id="9468e-126">Standard</span><span class="sxs-lookup"><span data-stu-id="9468e-126">Default</span></span>

<span data-ttu-id="9468e-127">Wir können das Schlüsselwort `default` nutzen, um zu bestimmen, was geschehen soll, wenn es keine Übereinstimmung gibt.</span><span class="sxs-lookup"><span data-stu-id="9468e-127">We can use the `default` keyword to identify the what should happen if there is no match.</span></span>

``` powershell
$result = switch ( $day )
{
    0 { 'Sunday' }
    # ...
    6 { 'Saturday' }
    default { 'Unknown' }
}
```

<span data-ttu-id="9468e-128">Hier geben wir im Standardfall den Wert `Unknown` zurück.</span><span class="sxs-lookup"><span data-stu-id="9468e-128">Here we return the value `Unknown` in the default case.</span></span>

### <a name="strings"></a><span data-ttu-id="9468e-129">Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="9468e-129">Strings</span></span>

<span data-ttu-id="9468e-130">In den letzten Beispielen habe ich Zahlen auf Übereinstimmung abgeglichen, aber Sie können auch Zeichenfolgen abgleichen.</span><span class="sxs-lookup"><span data-stu-id="9468e-130">I was matching numbers in those last examples, but you can also match strings.</span></span>

``` powershell
$item = 'Role'

switch ( $item )
{
    Component
    {
        'is a component'
    }
    Role
    {
        'is a role'
    }
    Location
    {
        'is a location'
    }
}
```

```Output
is a role
```

<span data-ttu-id="9468e-131">Ich habe beschlossen, die Abgleiche auf `Component`, `Role` und `Location` hier nicht in Anführungszeichen zu setzen, um hervorzuheben, dass sie optional sind.</span><span class="sxs-lookup"><span data-stu-id="9468e-131">I decided not to wrap the `Component`,`Role` and `Location` matches in quotes here to highlight that they're optional.</span></span> <span data-ttu-id="9468e-132">`switch` behandelt diese in den meisten Fällen als Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="9468e-132">The `switch` treats those as a string in most cases.</span></span>

## <a name="arrays"></a><span data-ttu-id="9468e-133">Arrays</span><span class="sxs-lookup"><span data-stu-id="9468e-133">Arrays</span></span>

<span data-ttu-id="9468e-134">Eines der coolen Features der PowerShell-Anweisung `switch` ist die Handhabung von Arrays.</span><span class="sxs-lookup"><span data-stu-id="9468e-134">One of the cool features of the PowerShell `switch` is the way it handles arrays.</span></span> <span data-ttu-id="9468e-135">Wenn Sie an `switch` ein Array übergeben, wird jedes Element in dieser Sammlung verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="9468e-135">If you give a `switch` an array, it processes each element in that collection.</span></span>

``` powershell
$roles = @('WEB','Database')

switch ( $roles ) {
    'Database'   { 'Configure SQL' }
    'WEB'        { 'Configure IIS' }
    'FileServer' { 'Configure Share' }
}
```

```Output
Configure IIS
Configure SQL
```

<span data-ttu-id="9468e-136">Wenn Ihr Array sich wiederholende Elemente enthält, werden diese im entsprechenden Abschnitt mehrfach abgeglichen.</span><span class="sxs-lookup"><span data-stu-id="9468e-136">If you have repeated items in your array, then they're matched multiple times by the appropriate section.</span></span>

### <a name="psitem"></a><span data-ttu-id="9468e-137">PSItem</span><span class="sxs-lookup"><span data-stu-id="9468e-137">PSItem</span></span>

<span data-ttu-id="9468e-138">Sie können `$PSItem` oder `$_` nutzen, um auf das aktuelle Element zu verweisen, das verarbeitet wurde.</span><span class="sxs-lookup"><span data-stu-id="9468e-138">You can use the `$PSItem` or `$_` to reference the current item that was processed.</span></span> <span data-ttu-id="9468e-139">Wenn wir einen einfachen Abgleich vornehmen, ist `$PSItem` der Wert, den wir auf Übereinstimmung abgleichen.</span><span class="sxs-lookup"><span data-stu-id="9468e-139">When we do a simple match, `$PSItem` is the value that we are matching.</span></span> <span data-ttu-id="9468e-140">Im nächsten Abschnitt möchte ich einige komplexere Abgleiche durchführen, bei denen diese Variable zum Einsatz kommt.</span><span class="sxs-lookup"><span data-stu-id="9468e-140">I'll be performing some advanced matches in the next section where this variable is used.</span></span>

## <a name="parameters"></a><span data-ttu-id="9468e-141">Parameter</span><span class="sxs-lookup"><span data-stu-id="9468e-141">Parameters</span></span>

<span data-ttu-id="9468e-142">Ein besonderes Merkmal der PowerShell-Anweisung `switch` ist, dass sie über eine Reihe von switch-Parameter verfügt, die ihre Funktionsweise beeinflussen.</span><span class="sxs-lookup"><span data-stu-id="9468e-142">A unique feature of the PowerShell `switch` is that it has a number of switch parameters that change how it performs.</span></span>

### <a name="-casesensitive"></a><span data-ttu-id="9468e-143">-CaseSensitive</span><span class="sxs-lookup"><span data-stu-id="9468e-143">-CaseSensitive</span></span>

<span data-ttu-id="9468e-144">Standardmäßig wird beim Abgleich Groß-/Kleinschreibung nicht beachtet.</span><span class="sxs-lookup"><span data-stu-id="9468e-144">The matches aren't case-sensitive by default.</span></span> <span data-ttu-id="9468e-145">Wenn Sie Groß-/Kleinschreibung beachten müssen, können Sie `-CaseSensitive`verwenden.</span><span class="sxs-lookup"><span data-stu-id="9468e-145">If you need to be case-sensitive, you can use `-CaseSensitive`.</span></span> <span data-ttu-id="9468e-146">Dies kann in Kombination mit den anderen Schalterparametern genutzt werden.</span><span class="sxs-lookup"><span data-stu-id="9468e-146">This can be used in combination with the other switch parameters.</span></span>

### <a name="-wildcard"></a><span data-ttu-id="9468e-147">-Wildcard</span><span class="sxs-lookup"><span data-stu-id="9468e-147">-Wildcard</span></span>

<span data-ttu-id="9468e-148">Mit dem Schalter `-wildcard` können wir Platzhalterunterstützung aktivieren.</span><span class="sxs-lookup"><span data-stu-id="9468e-148">We can enable wildcard support with the `-wildcard` switch.</span></span> <span data-ttu-id="9468e-149">Dabei wird für jeden Abgleich auf Übereinstimmung die gleiche Platzhalterlogik wie beim Operator `-like` genutzt.</span><span class="sxs-lookup"><span data-stu-id="9468e-149">This uses the same wildcard logic as the `-like` operator to do each match.</span></span>

``` powershell
$Message = 'Warning, out of disk space'

switch -Wildcard ( $message )
{
    'Error*'
    {
        Write-Error -Message $Message
    }
    'Warning*'
    {
        Write-Warning -Message $Message
    }
    default
    {
        Write-Information $message
    }
}
```

```Output
WARNING: Warning, out of disk space
```

<span data-ttu-id="9468e-150">Hier verarbeiten wir eine Nachricht und geben sie dann je nach Inhalt in verschiedenen Datenströmen aus.</span><span class="sxs-lookup"><span data-stu-id="9468e-150">Here we are processing a message and then outputting it on different streams based on the contents.</span></span>

### <a name="-regex"></a><span data-ttu-id="9468e-151">-Regex</span><span class="sxs-lookup"><span data-stu-id="9468e-151">-Regex</span></span>

<span data-ttu-id="9468e-152">Die switch-Anweisung unterstützt Übereinstimmungen mit regulären Ausdrücken (RegEx) ebenso wie Platzhalter.</span><span class="sxs-lookup"><span data-stu-id="9468e-152">The switch statement supports regex matches just like it does wildcards.</span></span>

``` powershell
switch -Regex ( $message )
{
    '^Error'
    {
        Write-Error -Message $Message
    }
    '^Warning'
    {
        Write-Warning -Message $Message
    }
    default
    {
        Write-Information $message
    }
}
```

<span data-ttu-id="9468e-153">Weitere Beispiele für die Nutzung regulärer Ausdrücke finden Sie in einem anderen Artikel von mir: [The many ways to use regex][] (Die vielfältigen Verwendungsmöglichkeiten von regulären Ausdrücken)</span><span class="sxs-lookup"><span data-stu-id="9468e-153">I have more examples of using regex in another article I wrote: [The many ways to use regex][].</span></span>

### <a name="-file"></a><span data-ttu-id="9468e-154">-File</span><span class="sxs-lookup"><span data-stu-id="9468e-154">-File</span></span>

<span data-ttu-id="9468e-155">Ein wenig bekanntes Merkmal der switch-Anweisung ist, dass sie eine Datei mit dem Parameter `-File` verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="9468e-155">A little known feature of the switch statement is that it can process a file with the `-File` parameter.</span></span> <span data-ttu-id="9468e-156">Sie verwenden `-file` mit einem Pfad zu einer Datei, anstatt dafür einen variablen Ausdruck anzugeben.</span><span class="sxs-lookup"><span data-stu-id="9468e-156">You use `-file` with a path to a file instead of giving it a variable expression.</span></span>

``` powershell
switch -Wildcard -File $path
{
    'Error*'
    {
        Write-Error -Message $PSItem
    }
    'Warning*'
    {
        Write-Warning -Message $PSItem
    }
    default
    {
        Write-Output $PSItem
    }
}
```

<span data-ttu-id="9468e-157">Dies funktioniert wie die Verarbeitung eines Arrays.</span><span class="sxs-lookup"><span data-stu-id="9468e-157">It works just like processing an array.</span></span> <span data-ttu-id="9468e-158">In diesem Beispiel kombiniere ich dies mit dem Platzhalterabgleich und nutze `$PSItem`.</span><span class="sxs-lookup"><span data-stu-id="9468e-158">In this example, I combine it with wildcard matching and make use of the `$PSItem`.</span></span> <span data-ttu-id="9468e-159">Damit ließe sich eine Protokolldatei verarbeiten und in Abhängigkeit von Übereinstimmungen mit regulären Ausdrücken in Warn- und Fehlermeldungen umwandeln.</span><span class="sxs-lookup"><span data-stu-id="9468e-159">This would process a log file and convert it to warning and error messages depending on the regex matches.</span></span>

## <a name="advanced-details"></a><span data-ttu-id="9468e-160">Details zur erweiterten Verarbeitung</span><span class="sxs-lookup"><span data-stu-id="9468e-160">Advanced details</span></span>

<span data-ttu-id="9468e-161">Jetzt, da Ihnen all diese dokumentierten Merkmale bekannt sind, können wir sie im Rahmen einer komplexeren Verarbeitung nutzen.</span><span class="sxs-lookup"><span data-stu-id="9468e-161">Now that you're aware of all these documented features, we can use them in the context of more advanced processing.</span></span>

### <a name="expressions"></a><span data-ttu-id="9468e-162">Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="9468e-162">Expressions</span></span>

<span data-ttu-id="9468e-163">`switch` kann für einen Ausdruck statt für eine Variable gelten.</span><span class="sxs-lookup"><span data-stu-id="9468e-163">The `switch` can be on an expression instead of a variable.</span></span>

``` powershell
switch ( ( Get-Service | Where status -eq 'running' ).name ) {...}
```

<span data-ttu-id="9468e-164">Das Ergebnis des Ausdrucks ist der für den Abgleich auf Übereinstimmung genutzte Wert.</span><span class="sxs-lookup"><span data-stu-id="9468e-164">Whatever the expression evaluates to is the value used for the match.</span></span>

### <a name="multiple-matches"></a><span data-ttu-id="9468e-165">Mehrere Übereinstimmungen</span><span class="sxs-lookup"><span data-stu-id="9468e-165">Multiple matches</span></span>

<span data-ttu-id="9468e-166">Möglicherweise haben Sie dies bereits bemerkt, aber eine `switch`-Anweisung kann mit mehreren Bedingungen übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="9468e-166">You may have already picked up on this, but a `switch` can match to multiple conditions.</span></span> <span data-ttu-id="9468e-167">Dies gilt insbesondere, wenn der Abgleich mit `-wildcard` oder `-regex` erfolgt.</span><span class="sxs-lookup"><span data-stu-id="9468e-167">This is especially true when using `-wildcard` or `-regex` matches.</span></span> <span data-ttu-id="9468e-168">Sie können dieselbe Bedingung mehrmals hinzufügen, die alle ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="9468e-168">You can add the same condition multiple times and all of them are triggered.</span></span>

``` powershell
switch ( 'Word' )
{
    'word' { 'lower case word match' }
    'Word' { 'mixed case word match' }
    'WORD' { 'upper case word match' }
}
```

```Output
lower case word match
mixed case word match
upper case word match
```

<span data-ttu-id="9468e-169">Alle drei dieser Anweisungen werden ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="9468e-169">All three of these statements are fired.</span></span> <span data-ttu-id="9468e-170">Dies zeigt, dass jede Bedingung (der Reihe nach) geprüft wird.</span><span class="sxs-lookup"><span data-stu-id="9468e-170">This shows that every condition is checked (in order).</span></span> <span data-ttu-id="9468e-171">Dies gilt für die Verarbeitung von Arrays, bei der jedes Element jede Bedingung prüft.</span><span class="sxs-lookup"><span data-stu-id="9468e-171">This holds true for processing arrays where each item checks each condition.</span></span>

### <a name="continue"></a><span data-ttu-id="9468e-172">Continue</span><span class="sxs-lookup"><span data-stu-id="9468e-172">Continue</span></span>

<span data-ttu-id="9468e-173">Normalerweise würde ich an dieser Stelle die Anweisung `break` einführen, aber es ist besser, wenn wir zunächst erfahren, wie `continue` verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="9468e-173">Normally, this is where I would introduce the `break` statement, but it's better that we learn how to use `continue` first.</span></span> <span data-ttu-id="9468e-174">Ebenso wie bei einer `foreach`-Schleife fährt `continue` mit dem nächsten Element in der Sammlung fort oder verlässt die `switch`-Anweisung, wenn es keine weiteren Elemente mehr gibt.</span><span class="sxs-lookup"><span data-stu-id="9468e-174">Just like with a `foreach` loop, `continue` continues onto the next item in the collection or exits the `switch` if there are no more items.</span></span> <span data-ttu-id="9468e-175">Wir können das letzte Beispiel mit continue-Anweisungen so umschreiben, dass nur eine Anweisung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="9468e-175">We can rewrite that last example with continue statements so that only one statement executes.</span></span>

``` powershell
switch ( 'Word' )
{
    'word'
    {
        'lower case word match'
        continue
    }
    'Word'
    {
        'mixed case word match'
        continue
    }
    'WORD'
    {
        'upper case word match'
        continue
    }
}
```

```Output
lower case word match
```

<span data-ttu-id="9468e-176">Anstatt alle drei Elemente abzugleichen, wird das erste abgeglichen, und die switch-Anweisung fährt mit dem nächsten Wert fort.</span><span class="sxs-lookup"><span data-stu-id="9468e-176">Instead of matching all three items, the first one is matched and the switch continues to the next value.</span></span> <span data-ttu-id="9468e-177">Da es keine weiteren Werte zu verarbeiten gibt, endet die switch-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="9468e-177">Because there are no values left to process, the switch exits.</span></span> <span data-ttu-id="9468e-178">Dieses nächste Beispiel zeigt, wie ein Platzhalter mit mehreren Elementen übereinstimmen kann.</span><span class="sxs-lookup"><span data-stu-id="9468e-178">This next example is showing how a wildcard could match multiple items.</span></span>

``` powershell
switch -Wildcard -File $path
{
    '*Error*'
    {
        Write-Error -Message $PSItem
        continue
    }
    '*Warning*'
    {
        Write-Warning -Message $PSItem
        continue
    }
    default
    {
        Write-Output $PSItem
    }
}
```

<span data-ttu-id="9468e-179">Da eine Zeile in der Eingabedatei sowohl das Wort `Error` als auch das Wort `Warning` enthalten könnte, möchten wir nur, dass das erste ausgeführt wird, und dann mit der Verarbeitung der Datei fortfahren.</span><span class="sxs-lookup"><span data-stu-id="9468e-179">Because a line in the input file could contain both the word `Error` and `Warning`, we only want the first one to execute and then continue processing the file.</span></span>

### <a name="break"></a><span data-ttu-id="9468e-180">Break</span><span class="sxs-lookup"><span data-stu-id="9468e-180">Break</span></span>

<span data-ttu-id="9468e-181">Eine `break`-Anweisung beendet die switch-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="9468e-181">A `break` statement exits the switch.</span></span> <span data-ttu-id="9468e-182">Dies ist das gleiche Verhalten wie bei `continue` für einzelne Werte.</span><span class="sxs-lookup"><span data-stu-id="9468e-182">This is the same behavior that `continue` presents for single values.</span></span> <span data-ttu-id="9468e-183">Der Unterschied zeigt sich bei der Verarbeitung eines Arrays.</span><span class="sxs-lookup"><span data-stu-id="9468e-183">The difference is shown when processing an array.</span></span> <span data-ttu-id="9468e-184">`break` beendet die gesamte Verarbeitung in der switch-Anweisung, während `continue` zum nächsten Element übergeht.</span><span class="sxs-lookup"><span data-stu-id="9468e-184">`break` stops all processing in the switch and `continue` moves onto the next item.</span></span>

``` powershell
$Messages = @(
    'Downloading update'
    'Ran into errors downloading file'
    'Error: out of disk space'
    'Sending email'
    '...'
)

switch -Wildcard ($Messages)
{
    'Error*'
    {
        Write-Error -Message $PSItem
        break
    }
    '*Error*'
    {
        Write-Warning -Message $PSItem
        continue
    }
    '*Warning*'
    {
        Write-Warning -Message $PSItem
        continue
    }
    default
    {
        Write-Output $PSItem
    }
}
```

```Output
Downloading update
WARNING: Ran into errors downloading file
write-error -message $PSItem : Error: out of disk space
+ CategoryInfo          : NotSpecified: (:) [Write-Error], WriteErrorException
+ FullyQualifiedErrorId : Microsoft.PowerShell.Commands.WriteErrorException
```

<span data-ttu-id="9468e-185">Wenn wir in diesem Fall auf Zeilen stoßen, die mit `Error` beginnen, erhalten wir einen Fehler, woraufhin die switch-Anweisung endet.</span><span class="sxs-lookup"><span data-stu-id="9468e-185">In this case, if we hit any lines that start with `Error` then we get an error and the switch stops.</span></span>
<span data-ttu-id="9468e-186">Diese Aufgabe erledigt diese `break`-Anweisung für uns.</span><span class="sxs-lookup"><span data-stu-id="9468e-186">This is what that `break` statement is doing for us.</span></span> <span data-ttu-id="9468e-187">Wenn wir `Error` innerhalb der Zeichenfolge und nicht nur am Anfang finden, schreiben wir dies als Warnung.</span><span class="sxs-lookup"><span data-stu-id="9468e-187">If we find `Error` inside the string and not just at the beginning, we write it as a warning.</span></span> <span data-ttu-id="9468e-188">Das Gleiche machen wir für `Warning`.</span><span class="sxs-lookup"><span data-stu-id="9468e-188">We do the same thing for `Warning`.</span></span> <span data-ttu-id="9468e-189">Es ist möglich, dass eine Zeile die Wörter `Error` und `Warning` enthalten kann, aber wir müssen nur eines davon verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="9468e-189">It's possible that a line could have both the word `Error` and `Warning`, but we only need one to process.</span></span> <span data-ttu-id="9468e-190">Diese Aufgabe erledigt die `continue`-Anweisung für uns.</span><span class="sxs-lookup"><span data-stu-id="9468e-190">This is what the `continue` statement is doing for us.</span></span>

### <a name="break-labels"></a><span data-ttu-id="9468e-191">break-Bezeichnungen</span><span class="sxs-lookup"><span data-stu-id="9468e-191">Break labels</span></span>

<span data-ttu-id="9468e-192">Die `switch`-Anweisung unterstützt `break/continue`-Bezeichnungen wie `foreach`.</span><span class="sxs-lookup"><span data-stu-id="9468e-192">The `switch` statement supports `break/continue` labels just like `foreach`.</span></span>

``` powershell
:filelist foreach($path in $logs)
{
    :logFile switch -Wildcard -File $path
    {
        'Error*'
        {
            Write-Error -Message $PSItem
            break filelist
        }
        'Warning*'
        {
            Write-Error -Message $PSItem
            break logFile
        }
        default
        {
            Write-Output $PSItem
        }
    }
}
```

<span data-ttu-id="9468e-193">Mir persönlich gefallen break-Bezeichnungen nicht, aber ich möchte auf sie hinweisen, weil sie verwirrend sind, wenn Sie sie noch nie zuvor gesehen haben.</span><span class="sxs-lookup"><span data-stu-id="9468e-193">I personally don't like the use of break labels but I wanted to point them out because they're confusing if you've never seen them before.</span></span> <span data-ttu-id="9468e-194">Wenn Sie mehrere geschachtelte `switch`- oder `foreach`-Anweisungen haben, möchten Sie möglicherweise bei mehr als nur dem innersten Element unterbrechen.</span><span class="sxs-lookup"><span data-stu-id="9468e-194">When you have multiple `switch` or `foreach` statements that are nested, you may want to break out of more than the inner most item.</span></span> <span data-ttu-id="9468e-195">Sie können einer `switch`-Anweisung eine Bezeichnung zuweisen, die das Ziel Ihrer `break`-Anweisung sein kann.</span><span class="sxs-lookup"><span data-stu-id="9468e-195">You can place a label on a `switch` that can be the target of your `break`.</span></span>

### <a name="enum"></a><span data-ttu-id="9468e-196">Enum</span><span class="sxs-lookup"><span data-stu-id="9468e-196">Enum</span></span>

<span data-ttu-id="9468e-197">Seit PowerShell 5.0 stehen uns Enumerationen zur Verfügung, die wir in einer switch-Anweisung nutzen können.</span><span class="sxs-lookup"><span data-stu-id="9468e-197">PowerShell 5.0 gave us enums and we can use them in a switch.</span></span>

``` powershell
enum Context {
    Component
    Role
    Location
}

$item = [Context]::Role

switch ( $item )
{
    Component
    {
        'is a component'
    }
    Role
    {
        'is a role'
    }
    Location
    {
        'is a location'
    }
}
```

```Output
is a role
```

<span data-ttu-id="9468e-198">Wenn Sie alles als stark typisierte Enumerationen beibehalten möchten, können Sie sie in Klammern setzen.</span><span class="sxs-lookup"><span data-stu-id="9468e-198">If you want to keep everything as strongly typed enums, then you can place them in parentheses.</span></span>

``` powershell
switch ($item )
{
    ([Context]::Component)
    {
        'is a component'
    }
    ([Context]::Role)
    {
        'is a role'
    }
    ([Context]::Location)
    {
        'is a location'
    }
}
```

<span data-ttu-id="9468e-199">Die Klammern werden hier benötigt, damit die switch-Anweisung den Wert `[Context]::Location` nicht als Literalzeichenfolge behandelt.</span><span class="sxs-lookup"><span data-stu-id="9468e-199">The parentheses are needed here so that the switch doesn't treat the value `[Context]::Location` as a literal string.</span></span>

### <a name="scriptblock"></a><span data-ttu-id="9468e-200">ScriptBlock</span><span class="sxs-lookup"><span data-stu-id="9468e-200">ScriptBlock</span></span>

<span data-ttu-id="9468e-201">Bei Bedarf können wir einen Skriptblock verwenden, um die Auswertung für eine Übereinstimmung vorzunehmen.</span><span class="sxs-lookup"><span data-stu-id="9468e-201">We can use a scriptblock to perform the evaluation for a match if needed.</span></span>

``` powershell
$age = 37

switch ( $age )
{
    {$PSItem -le 18}
    {
        'child'
    }
    {$PSItem -gt 18}
    {
        'adult'
    }
}
```

```Output
'adult'
```

<span data-ttu-id="9468e-202">Dies erhöht die Komplexität und kann Ihre `switch`-Anweisung schwer lesbar machen.</span><span class="sxs-lookup"><span data-stu-id="9468e-202">This adds complexity and can make your `switch` hard to read.</span></span> <span data-ttu-id="9468e-203">In den meisten Fällen, in denen Sie so etwas verwenden würden, wäre es besser, mit den Anweisungen `if` und `elseif` zu arbeiten.</span><span class="sxs-lookup"><span data-stu-id="9468e-203">In most cases where you would use something like this it would be better to use `if` and `elseif` statements.</span></span> <span data-ttu-id="9468e-204">Ich würde dies erwägen, wenn ich bereits eine große switch-Anweisung hätte und ich zwei Elemente bräuchte, um auf denselben Auswertungsblock zu treffen.</span><span class="sxs-lookup"><span data-stu-id="9468e-204">I would consider using this if I already had a large switch in place and I needed two items to hit the same evaluation block.</span></span>

<span data-ttu-id="9468e-205">Ein Punkt, der meiner Meinung nach zur Lesbarkeit beiträgt, ist das Setzen des Skriptblocks in Klammern.</span><span class="sxs-lookup"><span data-stu-id="9468e-205">One thing that I think helps with legibility is to place the scriptblock in parentheses.</span></span>

``` powershell
switch ( $age )
{
    ({$PSItem -le 18})
    {
        'child'
    }
    ({$PSItem -gt 18})
    {
        'adult'
    }
}
```

<span data-ttu-id="9468e-206">Er wird weiterhin auf die gleiche Weise ausgeführt und bietet beim schnellen Betrachten eine bessere visuelle Abgrenzung.</span><span class="sxs-lookup"><span data-stu-id="9468e-206">It still executes the same way and gives a better visual break when quickly looking at it.</span></span>

### <a name="regex-matches"></a><span data-ttu-id="9468e-207">$matches für reguläre Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="9468e-207">Regex $matches</span></span>

<span data-ttu-id="9468e-208">Wir müssen reguläre Ausdrücke wieder aufgreifen, um etwas anzusprechen, das nicht sofort offensichtlich ist.</span><span class="sxs-lookup"><span data-stu-id="9468e-208">We need to revisit regex to touch on something that isn't immediately obvious.</span></span> <span data-ttu-id="9468e-209">Bei Verwendung regulärer Ausdrücke wird die Variable `$matches` aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="9468e-209">The use of regex populates the `$matches` variable.</span></span> <span data-ttu-id="9468e-210">Ich gehe mehr auf die Verwendung von `$matches` ein, wenn ich auf [The many ways to use regex][] eingehe.</span><span class="sxs-lookup"><span data-stu-id="9468e-210">I do go into the use of `$matches` more when I talk about [The many ways to use regex][].</span></span> <span data-ttu-id="9468e-211">Hier ist ein kurzes Beispiel, um das Ganze mit benannten Übereinstimmungen in Aktion zu zeigen.</span><span class="sxs-lookup"><span data-stu-id="9468e-211">Here is a quick sample to show it in action with named matches.</span></span>

``` powershell
$message = 'my ssn is 123-23-3456 and credit card: 1234-5678-1234-5678'

switch -regex ($message)
{
    '(?<SSN>\d\d\d-\d\d-\d\d\d\d)'
    {
        Write-Warning "message contains a SSN: $($matches.SSN)"
    }
    '(?<CC>\d\d\d\d-\d\d\d\d-\d\d\d\d-\d\d\d\d)'
    {
        Write-Warning "message contains a credit card number: $($matches.CC)"
    }
    '(?<Phone>\d\d\d-\d\d\d-\d\d\d\d)'
    {
        Write-Warning "message contains a phone number: $($matches.Phone)"
    }
}
```

```Output
WARNING: message may contain a SSN: 123-23-3456
WARNING: message may contain a credit card number: 1234-5678-1234-5678
```

### <a name="null"></a><span data-ttu-id="9468e-212">$null</span><span class="sxs-lookup"><span data-stu-id="9468e-212">$null</span></span>

<span data-ttu-id="9468e-213">Sie können einen `$null`-Wert abgleichen, der nicht der Standardwert sein muss.</span><span class="sxs-lookup"><span data-stu-id="9468e-213">You can match a `$null` value that doesn't have to be the default.</span></span>

``` powershell
$value = $null

switch ( $value )
{
    $null
    {
        'Value is null'
    }
    default
    {
        'value is not null'
    }
}

```Output
Value is null
```

<span data-ttu-id="9468e-214">Gleiches gilt für eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="9468e-214">Same goes for an empty string.</span></span>

``` powershell
switch ( '' )
{
    ''
    {
        'Value is empty'
    }
    default
    {
        'value is a empty string'
    }
}

```Output
Value is empty
```

### <a name="constant-expression"></a><span data-ttu-id="9468e-215">Konstanter Ausdruck</span><span class="sxs-lookup"><span data-stu-id="9468e-215">Constant expression</span></span>

<span data-ttu-id="9468e-216">Lee Dailey hat darauf hingewiesen, dass wir einen Ausdruck, der konstant `$true` ist, nutzen können, um `[bool]`-Elemente auszuwerten.</span><span class="sxs-lookup"><span data-stu-id="9468e-216">Lee Dailey pointed out that we can use a constant `$true` expression to evaluate `[bool]` items.</span></span>
<span data-ttu-id="9468e-217">Stellen Sie sich vor, wir müssen mehrere Prüfungen boolescher Werte durchführen.</span><span class="sxs-lookup"><span data-stu-id="9468e-217">Imagine if we have several boolean checks that need to happen.</span></span>

``` powershell
$isVisible = $false
$isEnabled = $true
$isSecure = $true

switch ( $true )
{
    $isEnabled
    {
        'Do-Action'
    }
    $isVisible
    {
        'Show-Animation'
    }
    $isSecure
    {
        'Enable-AdminMenu'
    }
}
```

```Output
Do-Action
Enabled-AdminMenu
```

<span data-ttu-id="9468e-218">Dies ist eine einfache Möglichkeit, den Status mehrerer boolescher Felder auszuwerten und entsprechende Maßnahmen zu ergreifen.</span><span class="sxs-lookup"><span data-stu-id="9468e-218">This is a clean way to evaluate and take action on the status of several boolean fields.</span></span> <span data-ttu-id="9468e-219">Das Besondere daran ist, dass Sie mit einer Übereinstimmung den Status eines noch nicht ausgewerteten Werts umdrehen können.</span><span class="sxs-lookup"><span data-stu-id="9468e-219">The cool thing about this is that you can have one match flip the status of a value that hasn't been evaluated yet.</span></span>

``` powershell
$isVisible = $false
$isEnabled = $true
$isAdmin = $false

switch ( $true )
{
    $isEnabled
    {
        'Do-Action'
        $isVisible = $true
    }
    $isVisible
    {
        'Show-Animation'
    }
    $isAdmin
    {
        'Enable-AdminMenu'
    }
}
```

```Output
Do-Action
Show-Animation
```

<span data-ttu-id="9468e-220">Das Festlegen von `$isEnabled` auf `$true` in diesem Beispiel stellt sicher, dass `$isVisible` auch auf `$true` festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="9468e-220">Setting `$isEnabled` to `$true` in this example makes sure that `$isVisible` is also set to `$true`.</span></span> <span data-ttu-id="9468e-221">Wenn `$isVisible` dann ausgewertet wird, wird sein Skriptblock aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="9468e-221">Then when `$isVisible` gets evaluated, its scriptblock is invoked.</span></span> <span data-ttu-id="9468e-222">Das ist ein wenig widersinnig, aber eine geschickte Nutzung vorhandener Mechanismen.</span><span class="sxs-lookup"><span data-stu-id="9468e-222">This is a bit counter-intuitive but is a clever use of the mechanics.</span></span>

### <a name="switch-automatic-variable"></a><span data-ttu-id="9468e-223">$switch (automatische Variable)</span><span class="sxs-lookup"><span data-stu-id="9468e-223">$switch automatic variable</span></span>

<span data-ttu-id="9468e-224">Wenn `switch` seine Werte verarbeitet, wird ein Enumerator erstellt, der `$switch` genannt wird.</span><span class="sxs-lookup"><span data-stu-id="9468e-224">When the `switch` is processing its values, it creates an enumerator and calls it `$switch`.</span></span> <span data-ttu-id="9468e-225">Dies ist eine von PowerShell automatisch erstellte Variable, die Sie direkt verändern können.</span><span class="sxs-lookup"><span data-stu-id="9468e-225">This is an automatic variable created by PowerShell and you can manipulate it directly.</span></span>

```powershell
$a = 1, 2, 3, 4

switch($a) {
    1 { [void]$switch.MoveNext(); $switch.Current }
    3 { [void]$switch.MoveNext(); $switch.Current }
}
```

<span data-ttu-id="9468e-226">Dadurch erhalten Sie die folgenden Ergebnisse:</span><span class="sxs-lookup"><span data-stu-id="9468e-226">This gives you the results of:</span></span>

```Output
2
4
```

<span data-ttu-id="9468e-227">Indem Sie den Enumerator vorwärts bewegen, wird das nächste Element nicht durch `switch` verarbeitet, aber Sie können direkt auf diesen Wert zugreifen.</span><span class="sxs-lookup"><span data-stu-id="9468e-227">By moving the enumerator forward, the next item doesn't get processed by the `switch` but you can access that value directly.</span></span> <span data-ttu-id="9468e-228">Das würde ich Aberwitz nennen.</span><span class="sxs-lookup"><span data-stu-id="9468e-228">I would call it madness.</span></span>

## <a name="other-patterns"></a><span data-ttu-id="9468e-229">Andere Muster</span><span class="sxs-lookup"><span data-stu-id="9468e-229">Other patterns</span></span>

### <a name="hashtables"></a><span data-ttu-id="9468e-230">Hashtabellen</span><span class="sxs-lookup"><span data-stu-id="9468e-230">Hashtables</span></span>

<span data-ttu-id="9468e-231">Einer meiner beliebtesten Beiträge ist der zu [Hashtabellen][].</span><span class="sxs-lookup"><span data-stu-id="9468e-231">One of my most popular posts is the one I did on [hashtables][].</span></span> <span data-ttu-id="9468e-232">Einer der Anwendungsfälle für eine `hashtable` soll eine Nachschlagetabelle sein.</span><span class="sxs-lookup"><span data-stu-id="9468e-232">One of the use cases for a `hashtable` is to be a lookup table.</span></span> <span data-ttu-id="9468e-233">Das ist eine alternative Annäherung an ein gängiges Muster, mit dem sich eine `switch`-Anweisung oft befasst.</span><span class="sxs-lookup"><span data-stu-id="9468e-233">That is an alternate approach to a common pattern that a `switch` statement is often addressing.</span></span>

``` powershell
$day = 3

$lookup = @{
    0 = 'Sunday'
    1 = 'Monday'
    2 = 'Tuesday'
    3 = 'Wednesday'
    4 = 'Thursday'
    5 = 'Friday'
    6 = 'Saturday'
}

$lookup[$day]
```

```Output
Wednesday
```

<span data-ttu-id="9468e-234">Wenn ich eine `switch`-Anweisung nur zum Nachschlagen verwende, nutze ich stattdessen oft eine `hashtable`.</span><span class="sxs-lookup"><span data-stu-id="9468e-234">If I'm only using a `switch` as a lookup, I often use a `hashtable` instead.</span></span>

### <a name="enum"></a><span data-ttu-id="9468e-235">Enum</span><span class="sxs-lookup"><span data-stu-id="9468e-235">Enum</span></span>

<span data-ttu-id="9468e-236">Seit PowerShell 5.0 gibt es `Enum`, was in diesem Fall auch eine Option ist.</span><span class="sxs-lookup"><span data-stu-id="9468e-236">PowerShell 5.0 introduced the `Enum` and it's also an option in this case.</span></span>

``` powershell
$day = 3

enum DayOfTheWeek {
    Sunday
    Monday
    Tuesday
    Wednesday
    Thursday
    Friday
    Saturday
}

[DayOfTheWeek]$day
```

```Output
Wednesday
```

<span data-ttu-id="9468e-237">Wir könnten den ganzen Tag damit verbringen, verschiedene Wege zur Lösung dieses Problems zu finden.</span><span class="sxs-lookup"><span data-stu-id="9468e-237">We could go all day looking at different ways to solve this problem.</span></span> <span data-ttu-id="9468e-238">Ich wollte nur sichergehen, dass Sie wissen, welche Möglichkeiten Sie haben.</span><span class="sxs-lookup"><span data-stu-id="9468e-238">I just wanted to make sure you knew you had options.</span></span>

## <a name="final-words"></a><span data-ttu-id="9468e-239">Schlusswort</span><span class="sxs-lookup"><span data-stu-id="9468e-239">Final words</span></span>

<span data-ttu-id="9468e-240">Die switch-Anweisung ist oberflächlich betrachtet einfach, aber sie bietet einige erweiterte Merkmale, von denen die meisten nicht wissen, dass sie zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="9468e-240">The switch statement is simple on the surface but it offers some advanced features that most people don't realize are available.</span></span> <span data-ttu-id="9468e-241">Durch die Kombination dieser Merkmale steht Ihnen ein leistungsstarkes Instrument zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="9468e-241">Stringing those features together makes this a powerful feature.</span></span> <span data-ttu-id="9468e-242">Ich hoffe, Sie haben etwas gelernt, was Sie vorher noch nicht wussten.</span><span class="sxs-lookup"><span data-stu-id="9468e-242">I hope you learned something that you had not realized before.</span></span>

<!-- link references -->
[Originalversion]: https://powershellexplained.com/2018-01-12-Powershell-switch-statement/
[original version]: https://powershellexplained.com/2018-01-12-Powershell-switch-statement/
[powershellexplained.com]: https://powershellexplained.com/
[@KevinMarquette]: https://twitter.com/KevinMarquette
[switch]: /powershell/module/microsoft.powershell.core/about/about_switch
[The many ways to use regex]: https://powershellexplained.com/2017-07-31-Powershell-regex-regular-expression (Die vielfältigen Verwendungsmöglichkeiten von regulären Ausdrücken)
[Hashtabellen]: everything-about-hashtable.md
[hashtables]: everything-about-hashtable.md
