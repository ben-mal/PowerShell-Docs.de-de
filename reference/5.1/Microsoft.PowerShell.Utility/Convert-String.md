---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convert-string?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Convert-String
ms.openlocfilehash: 29ec9e21277bae02ab94ce5e862787c86a87b439
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214148"
---
# <span data-ttu-id="10dc1-103">Convert-String</span><span class="sxs-lookup"><span data-stu-id="10dc1-103">Convert-String</span></span>

## <span data-ttu-id="10dc1-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="10dc1-104">SYNOPSIS</span></span>
<span data-ttu-id="10dc1-105">Formatiert eine Zeichenfolge, um Beispiele zu vergleichen.</span><span class="sxs-lookup"><span data-stu-id="10dc1-105">Formats a string to match examples.</span></span>

## <span data-ttu-id="10dc1-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="10dc1-106">SYNTAX</span></span>

```
Convert-String [-Example <System.Collections.Generic.List`1[System.Management.Automation.PSObject]>]
 -InputObject <String> [<CommonParameters>]
```

## <span data-ttu-id="10dc1-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="10dc1-107">DESCRIPTION</span></span>

<span data-ttu-id="10dc1-108">Das **Convert-String-** Cmdlet formatiert eine Zeichenfolge so, dass Sie dem Format von Beispielen entspricht.</span><span class="sxs-lookup"><span data-stu-id="10dc1-108">The **Convert-String** cmdlet formats a string to match the format of examples.</span></span>

## <span data-ttu-id="10dc1-109">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="10dc1-109">EXAMPLES</span></span>

### <span data-ttu-id="10dc1-110">Beispiel 1: Konvertieren des Formats einer Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="10dc1-110">Example 1: Convert format of a string</span></span>

```powershell
"Mu Han", "Jim Hance", "David Ahs", "Kim Akers" | Convert-String -Example "Ed Wilson=Wilson, E."
```

```output
Han, M.
Hance, J.
Ahs, D.
Akers, K.
```

<span data-ttu-id="10dc1-111">Der erste Befehl erstellt ein Array, das vor-und Nachnamen enthält.</span><span class="sxs-lookup"><span data-stu-id="10dc1-111">The first command creates an array that contains first and last names.</span></span>

<span data-ttu-id="10dc1-112">Mit dem zweiten Befehl werden die Namen gemäß dem Beispiel formatiert.</span><span class="sxs-lookup"><span data-stu-id="10dc1-112">The second command formats the names according to the example.</span></span>
<span data-ttu-id="10dc1-113">Er fügt den Nachnamen zuerst in die Ausgabe ein, gefolgt von einem ursprünglichen.</span><span class="sxs-lookup"><span data-stu-id="10dc1-113">It puts the surname first in the output, followed by an initial.</span></span>

### <span data-ttu-id="10dc1-114">Beispiel 2: Vereinfachen der Format Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="10dc1-114">Example 2: Simplify format of a string</span></span>

```powershell
$composers = @("Johann Sebastian Bach", "Wolfgang Amadeus Mozart", "Frederic Francois Chopin", "Johannes Brahms")
$composers | Convert-String -Example "first middle last=last, first"
```

```output
Bach, Johann
Mozart, Wolfgang
Chopin, Frederic
Brahms, Johannes
```

<span data-ttu-id="10dc1-115">Der erste Befehl erstellt ein Array, das vor-, Mittel-und Nachnamen enthält.</span><span class="sxs-lookup"><span data-stu-id="10dc1-115">The first command creates an array that contains first, middle and last names.</span></span>
<span data-ttu-id="10dc1-116">Beachten Sie, dass der letzte Eintrag keinen mittleren Namen aufweist.</span><span class="sxs-lookup"><span data-stu-id="10dc1-116">Note that the last entry has no middle name.</span></span>

<span data-ttu-id="10dc1-117">Mit dem zweiten Befehl werden die Namen gemäß dem Beispiel formatiert.</span><span class="sxs-lookup"><span data-stu-id="10dc1-117">The second command formats the names according to the example.</span></span>
<span data-ttu-id="10dc1-118">Der Nachname wird zuerst in die Ausgabe eingefügt, gefolgt vom Vornamen.</span><span class="sxs-lookup"><span data-stu-id="10dc1-118">It puts the last name first in the output, followed by the first name.</span></span>
<span data-ttu-id="10dc1-119">Alle mittleren Namen wurden entfernt. der Eintrag ohne den mittleren Namen wird ordnungsgemäß behandelt.</span><span class="sxs-lookup"><span data-stu-id="10dc1-119">All middle names removed; entry without middle name is handled correctly.</span></span>

### <span data-ttu-id="10dc1-120">Beispiel 3: Ausgabe Verwaltung, wenn Zeichen folgen nicht mit Beispiel vergleichen</span><span class="sxs-lookup"><span data-stu-id="10dc1-120">Example 3: Output management when strings don't match example</span></span>

```powershell
$composers = @("Johann Sebastian Bach", "Wolfgang Amadeus Mozart", "Frederic Francois Chopin", "Johannes Brahms")
$composers | Convert-String -Example "first middle last=middle, first"
```

```output
Sebastian, Johann
Amadeus, Wolfgang
Francois, Frederic
```

<span data-ttu-id="10dc1-121">Der erste Befehl erstellt ein Array, das vor-, Mittel-und Nachnamen enthält.</span><span class="sxs-lookup"><span data-stu-id="10dc1-121">The first command creates an array that contains first, middle and last names.</span></span>
<span data-ttu-id="10dc1-122">Beachten Sie, dass der letzte Eintrag keinen mittleren Namen aufweist.</span><span class="sxs-lookup"><span data-stu-id="10dc1-122">Note that the last entry has no middle name.</span></span>

<span data-ttu-id="10dc1-123">Mit dem zweiten Befehl werden die Namen gemäß dem Beispiel formatiert.</span><span class="sxs-lookup"><span data-stu-id="10dc1-123">The second command formats the names according to the example.</span></span>
<span data-ttu-id="10dc1-124">**Der zweite Name wird** in die Ausgabe eingefügt, gefolgt vom Vornamen.</span><span class="sxs-lookup"><span data-stu-id="10dc1-124">It puts the **middle name** first in the output, followed by the first name.</span></span>
<span data-ttu-id="10dc1-125">Der letzte Eintrag in **$Composers** wird übersprungen, da er nicht mit dem Beispiel Muster identisch ist: er hat keinen mittleren Namen.</span><span class="sxs-lookup"><span data-stu-id="10dc1-125">The last entry in **$Composers** is skipped, because it doesn't match the sample pattern: it has no middle name.</span></span>

### <span data-ttu-id="10dc1-126">Beispiel 4: Vorsicht bei Beauty Spaces</span><span class="sxs-lookup"><span data-stu-id="10dc1-126">Example 4: Caution with beauty spaces</span></span>

```powershell
$composers = @("Antonio Vivaldi", "Richard Wagner ", "Franz Schubert", "Johannes Brahms ")
$composers | Convert-String -Example "Patti Fuller = Fuller, P."
```

```output
 Wagner, R.
 Brahms, J.
```

<span data-ttu-id="10dc1-127">Der erste Befehl erstellt ein Array von vor-und Nachnamen.</span><span class="sxs-lookup"><span data-stu-id="10dc1-127">The first command creates an array of first and last names.</span></span>
<span data-ttu-id="10dc1-128">Beachten Sie, dass das zweite und vierte Element nach dem Nachnamen über einen zusätzlichen nachfolgenden Bereich verfügen.</span><span class="sxs-lookup"><span data-stu-id="10dc1-128">Note that second and fourth items have an extra trailing space, after the last name.</span></span>

<span data-ttu-id="10dc1-129">Der zweite Befehl konvertiert alle Zeichen folgen, die mit dem Beispiel Muster übereinstimmen: _Word, Leerzeichen, Word und abschließende nachfolgende leer_ Zeichen, all dies vor dem Gleichheitszeichen.</span><span class="sxs-lookup"><span data-stu-id="10dc1-129">The second command converts all strings that match the sample pattern: _word, space, word, and final trailing space_ , all of this before the equal sign.</span></span>
<span data-ttu-id="10dc1-130">Beachten Sie auch den führenden Leerraum in der Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="10dc1-130">Also, note the leading space in the output.</span></span>

### <span data-ttu-id="10dc1-131">Beispiel 5: Formatieren von Prozessinformationen mit mehreren Mustern</span><span class="sxs-lookup"><span data-stu-id="10dc1-131">Example 5: Format process information with multiple patterns</span></span>

```powershell
$ExamplePatterns = @(
    @{before='"Hello","World"'; after='World: Hello'},
    @{before='"Hello","1"'; after='1: Hello'},
    @{before='"Hello-World","22"'; after='22: Hello-World'},
    @{before='"hello world","333"'; after='333: hello world'}
)
$Processes = Get-Process   | Select-Object -Property ProcessName, Id | ConvertTo-Csv -NoTypeInformation
$Processes | Convert-String -Example $ExamplePatterns
```

```output
Id: ProcessName
4368: AGSService
8896: Amazon Music Helper
4420: AppleMobileDeviceService
...
11140: git-bash
0: Idle
...
56: Secure System
...
13028: WmiPrvSE
2724: WUDFHost
2980: WUDFHost
3348: WUDFHost
```

<span data-ttu-id="10dc1-132">In **$ExamplePatterns** werden verschiedene erwartete Muster in den Daten anhand von Beispielen definiert.</span><span class="sxs-lookup"><span data-stu-id="10dc1-132">**$ExamplePatterns** defines different expected patterns in the data, through examples.</span></span>

<span data-ttu-id="10dc1-133">Das erste Muster, `@{before='"Hello","World"'; after='World: Hello'}` , liest wie folgt: erwartet werden Zeichen folgen, _bei denen ein Wort in doppelte Anführungszeichen eingeschlossen ist, dann ein Komma_ 
 _und dann das zweite und letzte Wort in Anführungszeichen eingeschlossen werden._ 
 _ohne Leerzeichen in der Zeichenfolge. In der Ausgabe: Platzieren Sie das zweite Wort zuerst_ 
 _ohne Anführungszeichen, dann ein einzelnes Leerzeichen und dann das erste Wort ohne Anführungszeichen._</span><span class="sxs-lookup"><span data-stu-id="10dc1-133">The first pattern, `@{before='"Hello","World"'; after='World: Hello'}`, reads as follows: _expect strings where a word comes enclosed in double quotes, then a comma,_
_and then the second, and last, word enclosed in quotes;_
_with no spaces in the string. On the output: place second word first,_
_without quotes, then a single space, and then the first word, without quotes._</span></span>

<span data-ttu-id="10dc1-134">Das zweite Muster, `@{before='"Hello","1"'; after='1: Hello'}` , liest wie folgt: _erwartet werden Zeichen folgen, bei denen ein Wort in doppelte Anführungszeichen eingeschlossen ist, dann ein Komma_ 
 _und eine Zahl in Anführungszeichen eingeschlossen wird._ 
 _ohne Leerzeichen in der Zeichenfolge. In der Ausgabe: Platzieren Sie die Zahl zuerst_ 
 _ohne Anführungszeichen, dann ein einzelnes Leerzeichen und dann das Wort ohne Anführungszeichen._</span><span class="sxs-lookup"><span data-stu-id="10dc1-134">The second pattern, `@{before='"Hello","1"'; after='1: Hello'}`, reads as follows: _expect strings where a word comes enclosed in double quotes, then a comma,_
_and then a number enclosed in quotes;_
_with no spaces in the string. On the output: place the number first,_
_without quotes, then a single space, and then the word, without quotes._</span></span>

<span data-ttu-id="10dc1-135">Das dritte Muster, `@{before='"Hello-World","22"'; after='22: Hello-World'}` , liest wie folgt: erwartet werden Zeichen folgen, _bei denen zwei Wörter mit einem Bindestrich dazwischen in_ 
 _doppelte Anführungszeichen eingeschlossen werden, dann ein Komma und eine Zahl in Anführungszeichen eingeschlossen sind._ 
 _ohne Leerzeichen zwischen dem Komma und dem dritten doppelten Anführungszeichen._ 
 _In der Ausgabe: Platzieren Sie die Zahl zuerst ohne Anführungszeichen und dann ein einzelnes Leerzeichen_ 
 . _und dann die Bindestriche ohne Anführungszeichen._</span><span class="sxs-lookup"><span data-stu-id="10dc1-135">The third pattern, `@{before='"Hello-World","22"'; after='22: Hello-World'}`, reads as follows: _expect strings where two words with a hyphen in between come enclosed in_
_double quotes, then a comma, and then a number enclosed in quotes;_
_with no spaces between the comma and the third double quote._
_On the output: place the number first, without quotes, then a single space,_
_and then the hyphenated words, without quotes._</span></span>

<span data-ttu-id="10dc1-136">Das vierte und abschließende Muster, `@{before='"hello world","333"'; after='333: hello world'}` ,, liest wie folgt: erwartet werden Zeichen folgen, _bei denen zwei Wörter mit einem Leerzeichen dazwischen in_ 
 _doppelte Anführungszeichen eingeschlossen werden, dann ein Komma und dann eine Zahl in Anführungszeichen_ eingeschlossen sind. 
 _ohne Leerzeichen zwischen dem Komma und dem dritten doppelten Anführungszeichen._ 
 _In der Ausgabe: Platzieren Sie die Zahl zuerst ohne Anführungszeichen und dann ein einzelnes Leerzeichen_ 
 . _und dann die Wörter mit dem Leerzeichen dazwischen, ohne Anführungszeichen._</span><span class="sxs-lookup"><span data-stu-id="10dc1-136">The fourth, and final, pattern, `@{before='"hello world","333"'; after='333: hello world'}`, reads as follows: _expect strings where two words with a space in between come enclosed in_
_double quotes, then a comma, and then a number enclosed in quotes;_
_with no spaces between the comma and the third double quote._
_On the output: place the number first, without quotes, then a single space,_
_and then the words with the space in between, without quotes._</span></span>

<span data-ttu-id="10dc1-137">Der erste Befehl ruft alle Prozesse mithilfe des Get-Process-Cmdlets ab.</span><span class="sxs-lookup"><span data-stu-id="10dc1-137">The first command gets all processes by using the Get-Process cmdlet.</span></span>
<span data-ttu-id="10dc1-138">Der Befehl übergibt sie an das Select-Object-Cmdlet, das den Prozessnamen und die Prozess-ID auswählt.</span><span class="sxs-lookup"><span data-stu-id="10dc1-138">The command passes them to the Select-Object cmdlet, which selects the process name and process ID.</span></span> <span data-ttu-id="10dc1-139">Am Ende der Pipeline konvertiert der Befehl die Ausgabe in durch Trennzeichen getrennte Werte ohne Typinformationen mithilfe des-Cmdlets ConvertTo-Csv.</span><span class="sxs-lookup"><span data-stu-id="10dc1-139">At the end of the pipeline, the command converts the output to comma separated values, without type information, by using the ConvertTo-Csv cmdlet.</span></span>
<span data-ttu-id="10dc1-140">Der Befehl speichert die Ergebnisse in der **$processes** Variable.</span><span class="sxs-lookup"><span data-stu-id="10dc1-140">The command stores the results in the **$Processes** variable.</span></span>
<span data-ttu-id="10dc1-141">**$Processes** jetzt die Prozessnamen und die PID enthält.</span><span class="sxs-lookup"><span data-stu-id="10dc1-141">**$Processes** now contains process names and PID.</span></span>

<span data-ttu-id="10dc1-142">Mit dem zweiten Befehl wird eine Beispiel Variable angegeben, die die Reihenfolge der Eingabeelemente ändert.</span><span class="sxs-lookup"><span data-stu-id="10dc1-142">The second command specifies an example variable that changes the order of the input items.</span></span>
<span data-ttu-id="10dc1-143">Der Befehl konvertiert jede Zeichenfolge in **$processes** .</span><span class="sxs-lookup"><span data-stu-id="10dc1-143">The command coverts each string in **$Processes** .</span></span>

><span data-ttu-id="10dc1-144">**Hinweis** Das vierte Muster besagt implizit, dass zwei oder mehr durch Leerzeichen getrennte Wörter übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="10dc1-144">**Note** The fourth pattern implicitly says that two or more words separated by spaces are matched.</span></span>
>
><span data-ttu-id="10dc1-145">Ohne das vierte Muster wird nur das erste Wort der Zeichenfolge abgeglichen, das in doppelte Anführungszeichen eingeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="10dc1-145">Without the fourth pattern, only the first word of the string enclosed in double quotes is matched.</span></span>

## <span data-ttu-id="10dc1-146">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="10dc1-146">PARAMETERS</span></span>

### <span data-ttu-id="10dc1-147">-Beispiel</span><span class="sxs-lookup"><span data-stu-id="10dc1-147">-Example</span></span>

<span data-ttu-id="10dc1-148">Gibt eine Liste von Beispielen für das Zielformat an.</span><span class="sxs-lookup"><span data-stu-id="10dc1-148">Specifies a list of examples of the target format.</span></span>
<span data-ttu-id="10dc1-149">Geben Sie Paare, die durch das Gleichheitszeichen (=) getrennt sind, mit dem Quell Muster auf der linken Seite und dem Ziel Muster auf der rechten Seite an, wie in den folgenden Beispielen gezeigt:</span><span class="sxs-lookup"><span data-stu-id="10dc1-149">Specify pairs separated by the equal (=) sign, with the source pattern on the left and the target pattern on the right, as in the following examples:</span></span>

* `-Example "Hello World=World, Hello"`
* `-Example "Hello World=World: Hello",'"Hello","1"=1: Hello'`

><span data-ttu-id="10dc1-150">**Hinweis** Im zweiten Beispiel wird eine Liste mit Mustern verwendet.</span><span class="sxs-lookup"><span data-stu-id="10dc1-150">**Note** The second example uses a list of patterns</span></span>

<span data-ttu-id="10dc1-151">Sie können auch eine Liste von Hash Tabellen angeben, die Eigenschaften von " **before** " und " **after** " enthalten.</span><span class="sxs-lookup"><span data-stu-id="10dc1-151">Alternatively, specify a list of hash tables that contain **Before** and **After** properties.</span></span>

* `-Example @{before='"Hello","World"'; after='World: Hello'}, @{before='"Hello","1"'; after='1: Hello'}`

><span data-ttu-id="10dc1-152">**Vorsicht** Vermeiden Sie die Verwendung von Leerzeichen um das Gleichheitszeichen, da diese als Teil des Musters behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="10dc1-152">**Caution** Avoid using spaces around the equal sign, as they are treated as part of the pattern.</span></span>

```yaml
Type: System.Collections.Generic.List`1[System.Management.Automation.PSObject]
Parameter Sets: (All)
Aliases: E

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="10dc1-153">-InputObject</span><span class="sxs-lookup"><span data-stu-id="10dc1-153">-InputObject</span></span>

<span data-ttu-id="10dc1-154">Gibt eine zu formatierende Zeichenfolge an.</span><span class="sxs-lookup"><span data-stu-id="10dc1-154">Specifies a string to format.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="10dc1-155">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="10dc1-155">CommonParameters</span></span>

<span data-ttu-id="10dc1-156">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="10dc1-156">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="10dc1-157">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="10dc1-157">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="10dc1-158">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="10dc1-158">INPUTS</span></span>

### <span data-ttu-id="10dc1-159">String</span><span class="sxs-lookup"><span data-stu-id="10dc1-159">String</span></span>

<span data-ttu-id="10dc1-160">Sie können Zeichen folgen an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="10dc1-160">You can pipe strings to this cmdlet.</span></span>

## <span data-ttu-id="10dc1-161">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="10dc1-161">OUTPUTS</span></span>

### <span data-ttu-id="10dc1-162">String</span><span class="sxs-lookup"><span data-stu-id="10dc1-162">String</span></span>

<span data-ttu-id="10dc1-163">Dieses Cmdlet gibt eine Zeichenfolge zurück.</span><span class="sxs-lookup"><span data-stu-id="10dc1-163">This cmdlet returns a string.</span></span>

## <span data-ttu-id="10dc1-164">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="10dc1-164">NOTES</span></span>

## <span data-ttu-id="10dc1-165">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="10dc1-165">RELATED LINKS</span></span>

[<span data-ttu-id="10dc1-166">ConvertFrom-String</span><span class="sxs-lookup"><span data-stu-id="10dc1-166">ConvertFrom-String</span></span>](ConvertFrom-String.md)

[<span data-ttu-id="10dc1-167">ConvertTo-Csv</span><span class="sxs-lookup"><span data-stu-id="10dc1-167">ConvertTo-Csv</span></span>](ConvertTo-Csv.md)

[<span data-ttu-id="10dc1-168">Get-Process</span><span class="sxs-lookup"><span data-stu-id="10dc1-168">Get-Process</span></span>](../Microsoft.PowerShell.Management/Get-Process.md)

[<span data-ttu-id="10dc1-169">Out-String</span><span class="sxs-lookup"><span data-stu-id="10dc1-169">Out-String</span></span>](Out-String.md)

[<span data-ttu-id="10dc1-170">Select-Object</span><span class="sxs-lookup"><span data-stu-id="10dc1-170">Select-Object</span></span>](Select-Object.md)
