---
description: Beschreibt reguläre Ausdrücke in PowerShell.
Locale: en-US
ms.date: 03/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_regular_expressions?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Regular_Expressions
ms.openlocfilehash: 4dc6ac670a31cbea4c35ee6540ce3368ad9b02ca
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99595525"
---
# <a name="about-regular-expressions"></a><span data-ttu-id="a7704-103">Informationen zu regulären Ausdrücken</span><span class="sxs-lookup"><span data-stu-id="a7704-103">About Regular Expressions</span></span>

## <a name="short-description"></a><span data-ttu-id="a7704-104">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a7704-104">Short description</span></span>
<span data-ttu-id="a7704-105">Beschreibt reguläre Ausdrücke in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a7704-105">Describes regular expressions in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="a7704-106">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a7704-106">Long description</span></span>

> [!NOTE]
> <span data-ttu-id="a7704-107">In diesem Artikel werden die Syntax und Methoden für die Verwendung regulärer Ausdrücke in PowerShell erläutert, nicht alle Syntax Themen.</span><span class="sxs-lookup"><span data-stu-id="a7704-107">This article will show you the syntax and methods for using regular expressions in PowerShell, not all syntax is discussed.</span></span> <span data-ttu-id="a7704-108">Einen ausführlicheren Verweis finden Sie unter [Sprache für reguläre Ausdrücke-kurz](/dotnet/standard/base-types/regular-expression-language-quick-reference)Übersicht.</span><span class="sxs-lookup"><span data-stu-id="a7704-108">For a more complete reference, see the [Regular Expression Language - Quick Reference](/dotnet/standard/base-types/regular-expression-language-quick-reference).</span></span>

<span data-ttu-id="a7704-109">Ein regulärer Ausdruck ist ein Muster, das verwendet wird, um Text zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="a7704-109">A regular expression is a pattern used to match text.</span></span> <span data-ttu-id="a7704-110">Sie kann aus Literalzeichen, Operatoren und anderen Konstrukten bestehen.</span><span class="sxs-lookup"><span data-stu-id="a7704-110">It can be made up of literal characters, operators, and other constructs.</span></span>

<span data-ttu-id="a7704-111">Dieser Artikel veranschaulicht die Syntax regulärer Ausdrücke in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a7704-111">This article demonstrates regular expression syntax in PowerShell.</span></span> <span data-ttu-id="a7704-112">PowerShell verfügt über mehrere Operatoren und Cmdlets, die reguläre Ausdrücke verwenden.</span><span class="sxs-lookup"><span data-stu-id="a7704-112">PowerShell has several operators and cmdlets that use regular expressions.</span></span> <span data-ttu-id="a7704-113">Weitere Informationen zur Syntax und Verwendung finden Sie unter den folgenden Links.</span><span class="sxs-lookup"><span data-stu-id="a7704-113">You can read more about their syntax and usage at the links below.</span></span>

- [<span data-ttu-id="a7704-114">Select-String</span><span class="sxs-lookup"><span data-stu-id="a7704-114">Select-String</span></span>](xref:Microsoft.PowerShell.Utility.Select-String)
- [<span data-ttu-id="a7704-115">-Match-und-replace-Operatoren</span><span class="sxs-lookup"><span data-stu-id="a7704-115">-match and -replace operators</span></span>](about_Comparison_Operators.md)
- [<span data-ttu-id="a7704-116">-Teilen</span><span class="sxs-lookup"><span data-stu-id="a7704-116">-split</span></span>](about_Split.md)
- [<span data-ttu-id="a7704-117">Switch-Anweisung mit der Option "-regex"</span><span class="sxs-lookup"><span data-stu-id="a7704-117">switch statement with -regex option</span></span>](about_Switch.md)

<span data-ttu-id="a7704-118">Bei regulären Ausdrücken von PowerShell wird die Groß-/Kleinschreibung nicht beachtet.</span><span class="sxs-lookup"><span data-stu-id="a7704-118">PowerShell regular expressions are case-insensitive by default.</span></span> <span data-ttu-id="a7704-119">Jede oben gezeigte Methode bietet eine andere Möglichkeit, die Groß-/Kleinschreibung zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="a7704-119">Each method shown above has a different way to force case sensitivity.</span></span>

|       <span data-ttu-id="a7704-120">Methode</span><span class="sxs-lookup"><span data-stu-id="a7704-120">Method</span></span>       |                      <span data-ttu-id="a7704-121">Groß- und Kleinschreibung</span><span class="sxs-lookup"><span data-stu-id="a7704-121">Case Sensitivity</span></span>                      |
| ------------------ | ---------------------------------------------------------- |
| `Select-String`    | <span data-ttu-id="a7704-122">Verwenden des `-CaseSensitive` Schalters</span><span class="sxs-lookup"><span data-stu-id="a7704-122">use `-CaseSensitive` switch</span></span>                                |
| <span data-ttu-id="a7704-123">`switch`-Anweisung</span><span class="sxs-lookup"><span data-stu-id="a7704-123">`switch` statement</span></span> | <span data-ttu-id="a7704-124">Verwenden Sie die `-casesensitive` Option</span><span class="sxs-lookup"><span data-stu-id="a7704-124">use the `-casesensitive` option</span></span>                            |
| <span data-ttu-id="a7704-125">Operatoren</span><span class="sxs-lookup"><span data-stu-id="a7704-125">operators</span></span>          | <span data-ttu-id="a7704-126">Präfix mit **"c"** ( `-cmatch` , `-csplit` oder `-creplace` )</span><span class="sxs-lookup"><span data-stu-id="a7704-126">prefix with **'c'** (`-cmatch`, `-csplit`, or `-creplace`)</span></span> |

### <a name="character-literals"></a><span data-ttu-id="a7704-127">Zeichenliterale</span><span class="sxs-lookup"><span data-stu-id="a7704-127">Character literals</span></span>

<span data-ttu-id="a7704-128">Ein regulärer Ausdruck kann ein Literalzeichen oder eine Zeichenfolge sein.</span><span class="sxs-lookup"><span data-stu-id="a7704-128">A regular expression can be a literal character or a string.</span></span> <span data-ttu-id="a7704-129">Der Ausdruck bewirkt, dass die Engine mit dem exakt angegebenen Text übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="a7704-129">The expression causes the engine to match the text specified exactly.</span></span>

```powershell
# This statement returns true because book contains the string "oo"
'book' -match 'oo'
```

### <a name="character-classes"></a><span data-ttu-id="a7704-130">Zeichenklassen</span><span class="sxs-lookup"><span data-stu-id="a7704-130">Character classes</span></span>

<span data-ttu-id="a7704-131">Wenn Zeichen Literale funktionieren, wenn Sie das genaue Muster kennen, können Sie mit Zeichenklassen weniger spezifisch sein.</span><span class="sxs-lookup"><span data-stu-id="a7704-131">While character literals work if you know the exact pattern, character classes allow you to be less specific.</span></span>

#### <a name="character-groups"></a><span data-ttu-id="a7704-132">Zeichen Gruppen</span><span class="sxs-lookup"><span data-stu-id="a7704-132">Character groups</span></span>

<span data-ttu-id="a7704-133">`[character group]` ermöglicht es Ihnen, eine beliebige Anzahl von Zeichen einmal abzugleichen, während `[^character group]` nur Zeichen, die nicht in der Gruppe enthalten sind, übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="a7704-133">`[character group]` allows you to match any number of characters one time, while `[^character group]` only matches characters NOT in the group.</span></span>

```powershell
# This expression returns true if the pattern matches big, bog, or bug.
'big' -match 'b[iou]g'
```

<span data-ttu-id="a7704-134">Wenn die Liste der zu Übereinstimmungs enden Zeichen den Bindestrich ( `-` ) enthält, muss Sie sich am Anfang oder Ende der Liste befinden, damit Sie von einem Zeichen Bereichs Ausdruck unterschieden werden kann.</span><span class="sxs-lookup"><span data-stu-id="a7704-134">If your list of characters to match includes the hyphen character (`-`), it must be at the beginning or end of the list to distinguish it from a character range expression.</span></span>

#### <a name="character-ranges"></a><span data-ttu-id="a7704-135">Zeichen Bereiche</span><span class="sxs-lookup"><span data-stu-id="a7704-135">Character ranges</span></span>

<span data-ttu-id="a7704-136">Ein Muster kann auch ein Bereich von Zeichen sein.</span><span class="sxs-lookup"><span data-stu-id="a7704-136">A pattern can also be a range of characters.</span></span> <span data-ttu-id="a7704-137">Die Zeichen können alphabetisch `[A-Z]` , numerisch `[0-9]` oder sogar ASCII-basiert `[ -~]` (alle druckbaren Zeichen) sein.</span><span class="sxs-lookup"><span data-stu-id="a7704-137">The characters can be alphabetic `[A-Z]`, numeric `[0-9]`, or even ASCII-based `[ -~]` (all printable characters).</span></span>

```powershell
# This expression returns true if the pattern matches any 2 digit number.
42 -match '[0-9][0-9]'
```

#### <a name="numbers"></a><span data-ttu-id="a7704-138">Zahlen</span><span class="sxs-lookup"><span data-stu-id="a7704-138">Numbers</span></span>

<span data-ttu-id="a7704-139">Die `\d` Zeichenklasse entspricht einer beliebigen Dezimal Ziffer.</span><span class="sxs-lookup"><span data-stu-id="a7704-139">The `\d` character class will match any decimal digit.</span></span> <span data-ttu-id="a7704-140">Umgekehrt findet eine Entsprechung für `\D` jede nicht-dezimal Ziffer.</span><span class="sxs-lookup"><span data-stu-id="a7704-140">Conversely, `\D` will match any non-decimal digit.</span></span>

```powershell
# This expression returns true if it matches a server name.
# (Server-01 - Server-99).
'Server-01' -match 'Server-\d\d'
```

#### <a name="word-characters"></a><span data-ttu-id="a7704-141">Wort Zeichen</span><span class="sxs-lookup"><span data-stu-id="a7704-141">Word characters</span></span>

<span data-ttu-id="a7704-142">Die `\w` Zeichenklasse entspricht einem beliebigen Wort Zeichen `[a-zA-Z_0-9]` .</span><span class="sxs-lookup"><span data-stu-id="a7704-142">The `\w` character class will match any word character `[a-zA-Z_0-9]`.</span></span> <span data-ttu-id="a7704-143">Verwenden Sie, um einem beliebigen nicht-Wort Zeichen zu entsprechen `\W` .</span><span class="sxs-lookup"><span data-stu-id="a7704-143">To match any non-word character, use `\W`.</span></span>

```powershell
# This expression returns true.
# The pattern matches the first word character 'B'.
'Book' -match '\w'
```

#### <a name="wildcards"></a><span data-ttu-id="a7704-144">Platzhalter</span><span class="sxs-lookup"><span data-stu-id="a7704-144">Wildcards</span></span>

<span data-ttu-id="a7704-145">Der Zeitraum ( `.` ) ist ein Platzhalter Zeichen in regulären Ausdrücken.</span><span class="sxs-lookup"><span data-stu-id="a7704-145">The period (`.`) is a wildcard character in regular expressions.</span></span> <span data-ttu-id="a7704-146">Es findet eine Entsprechung für jedes Zeichen außer einem Zeilen Umleitungs Zeichen ( `\n` ).</span><span class="sxs-lookup"><span data-stu-id="a7704-146">It will match any character except a newline (`\n`).</span></span>

```powershell
# This expression returns true.
# The pattern matches any 4 characters except the newline.
'a1\ ' -match '....'
```

#### <a name="whitespace"></a><span data-ttu-id="a7704-147">Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="a7704-147">Whitespace</span></span>

<span data-ttu-id="a7704-148">Leerraum wird mithilfe der- `\s` Zeichenklasse abgeglichen.</span><span class="sxs-lookup"><span data-stu-id="a7704-148">Whitespace is matched using the `\s` character class.</span></span> <span data-ttu-id="a7704-149">Ein Zeichen, das kein Leerzeichen ist, wird mithilfe von abgeglichen `\S` .</span><span class="sxs-lookup"><span data-stu-id="a7704-149">Any non-whitespace character is matched using `\S`.</span></span> <span data-ttu-id="a7704-150">Literalleerzeichen `' '` können ebenfalls verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a7704-150">Literal space characters `' '` can also be used.</span></span>

```powershell
# This expression returns true.
# The pattern uses both methods to match the space.
' - ' -match '\s- '
```

### <a name="quantifiers"></a><span data-ttu-id="a7704-151">Quantifizierer</span><span class="sxs-lookup"><span data-stu-id="a7704-151">Quantifiers</span></span>

<span data-ttu-id="a7704-152">Quantifiziererer steuern, wie viele Instanzen jedes Elements in der Eingabe Zeichenfolge vorhanden sein sollten.</span><span class="sxs-lookup"><span data-stu-id="a7704-152">Quantifiers control how many instances of each element should be present in the input string.</span></span>

<span data-ttu-id="a7704-153">Im folgenden sind einige der in PowerShell verfügbaren quantifiziererer aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="a7704-153">The following are a few of the quantifiers available in PowerShell:</span></span>

| <span data-ttu-id="a7704-154">Quantifizierer</span><span class="sxs-lookup"><span data-stu-id="a7704-154">Quantifier</span></span> |                <span data-ttu-id="a7704-155">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a7704-155">Description</span></span>                |
| ---------- | ----------------------------------------- |
| `*`        | <span data-ttu-id="a7704-156">NULL oder mehrmals.</span><span class="sxs-lookup"><span data-stu-id="a7704-156">Zero or more times.</span></span>                       |
| `+`        | <span data-ttu-id="a7704-157">Einmal oder mehrmals.</span><span class="sxs-lookup"><span data-stu-id="a7704-157">One or more times.</span></span>                        |
| `?`        | <span data-ttu-id="a7704-158">Kein oder einmal.</span><span class="sxs-lookup"><span data-stu-id="a7704-158">Zero or one time.</span></span>                         |
| `{n,m}`    | <span data-ttu-id="a7704-159">Mindestens `n` , aber nicht mehr als `m` Uhrzeiten.</span><span class="sxs-lookup"><span data-stu-id="a7704-159">At least `n`, but no more than `m` times.</span></span> |

<span data-ttu-id="a7704-160">Das Sternchen ( `*` ) entspricht dem vorangehenden Element nicht oder mehrmals.</span><span class="sxs-lookup"><span data-stu-id="a7704-160">The asterisk (`*`) matches the previous element zero or more times.</span></span> <span data-ttu-id="a7704-161">Das Ergebnis ist, dass auch eine Eingabe Zeichenfolge ohne das-Element eine Entsprechung wäre.</span><span class="sxs-lookup"><span data-stu-id="a7704-161">The result is that even an input string without the element would be a match.</span></span>

```powershell
# This returns true for all account name strings even if the name is absent.
'ACCOUNT NAME:    Administrator' -match 'ACCOUNT NAME:\s*\w*'
```

<span data-ttu-id="a7704-162">Das Pluszeichen ( `+` ) entspricht dem vorangehenden Element einmal oder mehrmals.</span><span class="sxs-lookup"><span data-stu-id="a7704-162">The plus sign (`+`) matches the previous element one or more times.</span></span>

```powershell
# This returns true if it matches any server name.
'DC-01' -match '[A-Z]+-\d\d'
```

<span data-ttu-id="a7704-163">Das Fragezeichen `?` entspricht dem vorangehenden Element nicht oder einmal.</span><span class="sxs-lookup"><span data-stu-id="a7704-163">The question mark `?` matches the previous element zero or one time.</span></span> <span data-ttu-id="a7704-164">Ebenso wie Sternchen werden Zeichen folgen `*` , in denen das-Element nicht vorhanden ist, sogar abgeglichen.</span><span class="sxs-lookup"><span data-stu-id="a7704-164">Like asterisk `*`, it will even match strings where the element is absent.</span></span>

```powershell
# This returns true for any server name, even server names without dashes.
'SERVER01' -match '[A-Z]+-?\d\d'
```

<span data-ttu-id="a7704-165">Der `{n, m}` Quantifizierer kann auf verschiedene Arten verwendet werden, um eine differenzierte Steuerung des Quantifizierers zuzulassen.</span><span class="sxs-lookup"><span data-stu-id="a7704-165">The `{n, m}` quantifier can be used several different ways to allow granular control over the quantifier.</span></span> <span data-ttu-id="a7704-166">Das zweite Element `m` und das Komma `,` sind optional.</span><span class="sxs-lookup"><span data-stu-id="a7704-166">The second element `m` and the comma `,` are optional.</span></span>

| <span data-ttu-id="a7704-167">Quantifizierer</span><span class="sxs-lookup"><span data-stu-id="a7704-167">Quantifier</span></span> |                <span data-ttu-id="a7704-168">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a7704-168">Description</span></span>                 |
| ---------- | ------------------------------------------ |
| `{n}`      | <span data-ttu-id="a7704-169">Übereinstimmung `n` mit genau der Anzahl von vorkommen.</span><span class="sxs-lookup"><span data-stu-id="a7704-169">Match EXACTLY `n` number of times.</span></span>         |
| `{n,}`     | <span data-ttu-id="a7704-170">Entspricht mindestens `n` der Anzahl von vorkommen.</span><span class="sxs-lookup"><span data-stu-id="a7704-170">Match at LEAST `n` number of times.</span></span>        |
| `{n,m}`    | <span data-ttu-id="a7704-171">Vergleichen zwischen `n` und `m` der Anzahl von vorkommen.</span><span class="sxs-lookup"><span data-stu-id="a7704-171">Match between `n` and `m` number of times.</span></span> |

```powershell
# This returns true if it matches any phone number.
'111-222-3333' -match '\d{3}-\d{3}-\d{4}'
```

### <a name="anchors"></a><span data-ttu-id="a7704-172">Anchors</span><span class="sxs-lookup"><span data-stu-id="a7704-172">Anchors</span></span>

<span data-ttu-id="a7704-173">Anker ermöglichen es Ihnen, eine Übereinstimmung basierend auf der übereinstimmenden Position in der Eingabe Zeichenfolge erfolgreich oder fehlerhaft zu erzeugen.</span><span class="sxs-lookup"><span data-stu-id="a7704-173">Anchors allow you to cause a match to succeed or fail based on the matches position within the input string.</span></span>

<span data-ttu-id="a7704-174">Die beiden häufig verwendeten Anker sind `^` und `$` .</span><span class="sxs-lookup"><span data-stu-id="a7704-174">The two commonly used anchors are `^` and `$`.</span></span> <span data-ttu-id="a7704-175">Die Einfügemarke `^` entspricht dem Anfang einer Zeichenfolge und `$` , die mit dem Ende einer Zeichenfolge übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="a7704-175">The caret `^` matches the start of a string, and `$`, which matches the end of a string.</span></span> <span data-ttu-id="a7704-176">Die Anker ermöglichen es Ihnen, Ihren Text an einer bestimmten Position abzugleichen, während unerwünschte Zeichen verworfen werden.</span><span class="sxs-lookup"><span data-stu-id="a7704-176">The anchors allow you to match your text at a specific position while also discarding unwanted characters.</span></span>

```powershell
# The pattern expects the string 'fish' to be the only thing on the line.
# This returns FALSE.
'fishing' -match '^fish$'
```

> [!NOTE]
> <span data-ttu-id="a7704-177">Wenn Sie einen regulären Ausdruck definieren, der einen `$` Anker enthält, achten Sie darauf, dass Sie den Regex-Ausdruck in einfache Anführungszeichen ( `'` ) statt in doppelte Anführungszeichen () einschließen, `"` oder der Ausdruck wird von PowerShell als Variable erweitert.</span><span class="sxs-lookup"><span data-stu-id="a7704-177">When defining a regex containing an `$` anchor, be sure to enclose the regex using single quotes (`'`) instead of double quotes (`"`) or PowerShell will expand the expression as a variable.</span></span>

<span data-ttu-id="a7704-178">Wenn Sie Anker in PowerShell verwenden, sollten Sie den Unterschied zwischen den Optionen für " **SingleLine** " und " **mehrzeilige** reguläre Ausdrücke" verstehen.</span><span class="sxs-lookup"><span data-stu-id="a7704-178">When using anchors in PowerShell, you should understand the difference between **Singleline** and **Multiline** regular expression options.</span></span>

- <span data-ttu-id="a7704-179">**MultiLine**: der mehrzeilige Modus erzwingt `^` und `$` , um das Anfangs Ende jeder Zeile anstelle von Anfang und Ende der Eingabe Zeichenfolge abzugleichen.</span><span class="sxs-lookup"><span data-stu-id="a7704-179">**Multiline**: Multiline mode forces `^` and `$` to match the beginning end of every LINE instead of the beginning and end of the input string.</span></span>
- <span data-ttu-id="a7704-180">**SingleLine**: der SingleLine-Modus behandelt die Eingabe Zeichenfolge als **SingleLine**.</span><span class="sxs-lookup"><span data-stu-id="a7704-180">**Singleline**: Singleline mode treats the input string as a **SingleLine**.</span></span>
  <span data-ttu-id="a7704-181">Es erzwingt `.` , dass das Zeichen jedem Zeichen (einschließlich der Zeilenumbrüche) entspricht, anstatt jedes Zeichen mit Ausnahme von Zeilenumbrüche abzugleichen `\n` .</span><span class="sxs-lookup"><span data-stu-id="a7704-181">It forces the `.` character to match every character (including newlines), instead of matching every character EXCEPT the newline `\n`.</span></span>

<span data-ttu-id="a7704-182">Weitere Informationen zu diesen Optionen und deren Verwendung finden Sie in der Sprache für [reguläre Ausdrücke (kurz](/dotnet/standard/base-types/regular-expression-language-quick-reference)Übersicht).</span><span class="sxs-lookup"><span data-stu-id="a7704-182">To read more about these options and how to use them, visit the [Regular Expression Language - Quick Reference](/dotnet/standard/base-types/regular-expression-language-quick-reference).</span></span>

### <a name="escaping-characters"></a><span data-ttu-id="a7704-183">Zeichen mit Escapezeichen</span><span class="sxs-lookup"><span data-stu-id="a7704-183">Escaping characters</span></span>

<span data-ttu-id="a7704-184">Der umgekehrte Schrägstrich ( `\` ) wird verwendet, um Zeichen zu Escapezeichen, sodass Sie nicht von der Engine für reguläre Ausdrücke analysiert werden.</span><span class="sxs-lookup"><span data-stu-id="a7704-184">The backslash (`\`) is used to escape characters so they aren't parsed by the regular expression engine.</span></span>

<span data-ttu-id="a7704-185">Die folgenden Zeichen sind reserviert: `[]().\^$|?*+{}` .</span><span class="sxs-lookup"><span data-stu-id="a7704-185">The following characters are reserved: `[]().\^$|?*+{}`.</span></span>

<span data-ttu-id="a7704-186">Sie müssen diese Zeichen in ihren Mustern mit Escapezeichen versehen, um Sie in ihren Eingabe Zeichenfolgen abzugleichen.</span><span class="sxs-lookup"><span data-stu-id="a7704-186">You'll need to escape these characters in your patterns to match them in your input strings.</span></span>

```powershell
# This returns true and matches numbers with at least 2 digits of precision.
# The decimal point is escaped using the backslash.
'3.141' -match '3\.\d{2,}'
```

<span data-ttu-id="a7704-187">Es gibt eine statische Methode der Regex-Klasse, die Text mit Escapezeichen versehen kann.</span><span class="sxs-lookup"><span data-stu-id="a7704-187">There\`s a static method of the regex class that can escape text for you.</span></span>

```powershell
[regex]::escape('3.\d{2,}')
```

```Output
3\.\\d\{2,}
```

> [!NOTE]
> <span data-ttu-id="a7704-188">Dadurch werden alle reservierten Zeichen für reguläre Ausdrücke, einschließlich vorhandener umgekehrter Schrägstriche, in Zeichenklassen verwendet.</span><span class="sxs-lookup"><span data-stu-id="a7704-188">This escapes all reserved regular expression characters, including existing backslashes used in character classes.</span></span> <span data-ttu-id="a7704-189">Achten Sie darauf, dass Sie Sie nur für den Teil des Musters verwenden, den Sie mit Escapezeichen versehen müssen.</span><span class="sxs-lookup"><span data-stu-id="a7704-189">Be sure to only use it on the portion of your pattern that you need to escape.</span></span>

#### <a name="other-character-escapes"></a><span data-ttu-id="a7704-190">Andere Escapezeichen</span><span class="sxs-lookup"><span data-stu-id="a7704-190">Other character escapes</span></span>

<span data-ttu-id="a7704-191">Es gibt auch reservierte Escapezeichen, die Sie verwenden können, um besondere Zeichen Typen abzugleichen.</span><span class="sxs-lookup"><span data-stu-id="a7704-191">There are also reserved character escapes that you can use to match special character types.</span></span>

<span data-ttu-id="a7704-192">Im folgenden finden Sie einige häufig verwendete Escapezeichen:</span><span class="sxs-lookup"><span data-stu-id="a7704-192">The following are a few commonly used character escapes:</span></span>

|<span data-ttu-id="a7704-193">Escapezeichen</span><span class="sxs-lookup"><span data-stu-id="a7704-193">Character Escape</span></span>  |<span data-ttu-id="a7704-194">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="a7704-194">Description</span></span>  |
|---------|---------|
|`\t`|<span data-ttu-id="a7704-195">Entspricht einer Registerkarte</span><span class="sxs-lookup"><span data-stu-id="a7704-195">Matches a tab</span></span>|
|`\n`|<span data-ttu-id="a7704-196">Entspricht einem Zeilen Einschluss</span><span class="sxs-lookup"><span data-stu-id="a7704-196">Matches a newline</span></span>|
|`\r`|<span data-ttu-id="a7704-197">Entspricht einem Wagen Rücklauf Zeichen</span><span class="sxs-lookup"><span data-stu-id="a7704-197">Matches a carriage return</span></span>|

### <a name="groups-captures-and-substitutions"></a><span data-ttu-id="a7704-198">Gruppen, Erfassungen und Ersetzungen</span><span class="sxs-lookup"><span data-stu-id="a7704-198">Groups, Captures, and Substitutions</span></span>

<span data-ttu-id="a7704-199">Gruppierungskonstrukte trennen eine Eingabe Zeichenfolge in Teil Zeichenfolgen, die aufgezeichnet oder ignoriert werden können.</span><span class="sxs-lookup"><span data-stu-id="a7704-199">Grouping constructs separate an input string into substrings that can be captured or ignored.</span></span> <span data-ttu-id="a7704-200">Gruppierte Teil Zeichenfolgen werden als Teil Ausdrücke bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="a7704-200">Grouped substrings are called subexpressions.</span></span> <span data-ttu-id="a7704-201">Standard Ausdrücke werden standardmäßig in nummerierten Gruppen aufgezeichnet, aber Sie können Ihnen auch Namen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="a7704-201">By default subexpressions are captured in numbered groups, though you can assign names to them as well.</span></span>

<span data-ttu-id="a7704-202">Ein Gruppierungs Konstrukt ist ein regulärer Ausdruck, der von Klammern umgeben ist.</span><span class="sxs-lookup"><span data-stu-id="a7704-202">A grouping construct is a regular expression surrounded by parentheses.</span></span> <span data-ttu-id="a7704-203">Jeder Text, der mit dem eingeschlossenen regulären Ausdruck übereinstimmt, wird aufgezeichnet.</span><span class="sxs-lookup"><span data-stu-id="a7704-203">Any text matched by the enclosed regular expression is captured.</span></span> <span data-ttu-id="a7704-204">Im folgenden Beispiel wird der Eingabetext in zwei Erfassungs Gruppen aufgeteilt.</span><span class="sxs-lookup"><span data-stu-id="a7704-204">The following example will break the input text into two capturing groups.</span></span>

```powershell
'The last logged on user was CONTOSO\jsmith' -match '(.+was )(.+)'
```

```Output
True
```

<span data-ttu-id="a7704-205">Verwenden `$Matches` Sie die automatische **Hash Tabelle** -Variable, um erfassten Text abzurufen.</span><span class="sxs-lookup"><span data-stu-id="a7704-205">Use the `$Matches` **Hashtable** automatic variable to retrieve captured text.</span></span>
<span data-ttu-id="a7704-206">Der Text, der die gesamte Übereinstimmung darstellt, wird im Schlüssel gespeichert `0` .</span><span class="sxs-lookup"><span data-stu-id="a7704-206">The text representing the entire match is stored at key `0`.</span></span>

```powershell
$Matches.0
```

```Output
The last logged on user was CONTOSO\jsmith
```

<span data-ttu-id="a7704-207">Erfassungen werden in numerischen **ganzzahligen** Schlüsseln gespeichert, die sich von links nach rechts erhöhen.</span><span class="sxs-lookup"><span data-stu-id="a7704-207">Captures are stored in numeric **Integer** keys that increase from left to right.</span></span> <span data-ttu-id="a7704-208">Capture `1` enthält den gesamten Text bis zum Benutzernamen, die Erfassung `2` enthält lediglich den Benutzernamen.</span><span class="sxs-lookup"><span data-stu-id="a7704-208">Capture `1` contains all the text until the username, capture `2` contains just the username.</span></span>

```powershell
$Matches
```

```Output
Name                           Value
----                           -----
2                              CONTOSO\jsmith
1                              The last logged on user was
0                              The last logged on user was CONTOSO\jsmith
```

> [!IMPORTANT]
> <span data-ttu-id="a7704-209">Der `0` Schlüssel ist eine **ganze** Zahl.</span><span class="sxs-lookup"><span data-stu-id="a7704-209">The `0` key is an **Integer**.</span></span> <span data-ttu-id="a7704-210">Sie können eine beliebige **Hash Tabellen** Methode verwenden, um auf den gespeicherten Wert zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="a7704-210">You can use any **Hashtable** method to access the value stored.</span></span>
>
> ```
> PS> 'Good Dog' -match 'Dog'
> True
>
> PS> $Matches[0]
> Dog
>
> PS> $Matches.Item(0)
> Dog
>
> PS> $Matches.0
> Dog
> ```

#### <a name="named-captures"></a><span data-ttu-id="a7704-211">Benannte Erfassungen</span><span class="sxs-lookup"><span data-stu-id="a7704-211">Named Captures</span></span>

<span data-ttu-id="a7704-212">Standardmäßig werden Erfassungen von links nach rechts in aufsteigender numerischer Reihenfolge gespeichert.</span><span class="sxs-lookup"><span data-stu-id="a7704-212">By default, captures are stored in ascending numeric order, from left to right.</span></span>
<span data-ttu-id="a7704-213">Sie können einer Erfassungs Gruppe auch einen **Namen** zuweisen.</span><span class="sxs-lookup"><span data-stu-id="a7704-213">You can also assign a **name** to a capturing group.</span></span> <span data-ttu-id="a7704-214">Dieser **Name** wird ein Schlüssel für die `$Matches` automatische **Hash Tabellen** Variable.</span><span class="sxs-lookup"><span data-stu-id="a7704-214">This **name** becomes a key on the `$Matches` **Hashtable** automatic variable.</span></span>

<span data-ttu-id="a7704-215">Verwenden Sie in einer `?<keyname>` Erfassungs Gruppe, um erfasste Daten unter einem benannten Schlüssel zu speichern.</span><span class="sxs-lookup"><span data-stu-id="a7704-215">Inside a capturing group, use `?<keyname>` to store captured data under a named key.</span></span>

```
PS> $string = 'The last logged on user was CONTOSO\jsmith'
PS> $string -match 'was (?<domain>.+)\\(?<user>.+)'
True

PS> $Matches

Name                           Value
----                           -----
domain                         CONTOSO
user                           jsmith
0                              was CONTOSO\jsmith

PS> $Matches.domain
CONTOSO

PS> $Matches.user
jsmith
```

<span data-ttu-id="a7704-216">Im folgenden Beispiel wird der neueste Protokolleintrag im Windows-Sicherheitsprotokoll gespeichert.</span><span class="sxs-lookup"><span data-stu-id="a7704-216">The following example stores the newest log entry in the Windows Security Log.</span></span>
<span data-ttu-id="a7704-217">Der angegebene reguläre Ausdruck extrahiert den Benutzernamen und die Domäne aus der Nachricht und speichert Sie unter den Schlüsseln:**N** für Name und **D** für die Domäne.</span><span class="sxs-lookup"><span data-stu-id="a7704-217">The provided regular expression extracts the username and domain from the message and stores them under the keys:**N** for name and **D** for domain.</span></span>

```powershell
$log = (Get-WinEvent -LogName Security -MaxEvents 1).message
$r = '(?s).*Account Name:\s*(?<N>.*).*Account Domain:\s*(?<D>[A-Z,0-9]*)'
$log -match $r
```

```Output
True
```

```powershell
$Matches
```

```Output
Name                           Value
----                           -----
D                              CONTOSO
N                              jsmith
0                              A process has exited....
```

<span data-ttu-id="a7704-218">Weitere Informationen finden Sie unter [Gruppierungskonstrukte in regulären Ausdrücken](/dotnet/standard/base-types/grouping-constructs-in-regular-expressions).</span><span class="sxs-lookup"><span data-stu-id="a7704-218">For more information, see [Grouping Constructs in Regular Expressions](/dotnet/standard/base-types/grouping-constructs-in-regular-expressions).</span></span>

#### <a name="substitutions-in-regular-expressions"></a><span data-ttu-id="a7704-219">Ersetzungen in regulären Ausdrücken</span><span class="sxs-lookup"><span data-stu-id="a7704-219">Substitutions in Regular Expressions</span></span>

<span data-ttu-id="a7704-220">Die Verwendung der regulären Ausdrücke mit dem- `-replace` Operator ermöglicht das dynamische Ersetzen von Text mithilfe von Erfassungs Text.</span><span class="sxs-lookup"><span data-stu-id="a7704-220">Using the regular expressions with the `-replace` operator allows you to dynamically replace text using captured text.</span></span>

`<input> -replace <original>, <substitute>`

- <span data-ttu-id="a7704-221">`<input>`: Die zu durchsuchende Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="a7704-221">`<input>`: The string to be searched</span></span>
- <span data-ttu-id="a7704-222">`<original>`: Ein regulärer Ausdruck zum Durchsuchen der Eingabe Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="a7704-222">`<original>`: A regular expression used to search the input string</span></span>
- <span data-ttu-id="a7704-223">`<substitute>`: Ein Ersetzungs Ausdruck für reguläre Ausdrücke zum Ersetzen der in der Eingabe Zeichenfolge gefundenen Übereinstimmungen.</span><span class="sxs-lookup"><span data-stu-id="a7704-223">`<substitute>`: A regular expression substitution expression to replace matches found in the input string.</span></span>

> [!NOTE]
> <span data-ttu-id="a7704-224">Der `<original>` -und der- `<substitute>` Operanden unterliegen den Regeln der Engine für reguläre Ausdrücke, z. b. Escapezeichen.</span><span class="sxs-lookup"><span data-stu-id="a7704-224">The `<original>` and `<substitute>` operands are subject to rules of the regular expression engine such as character escaping.</span></span>

<span data-ttu-id="a7704-225">In der Zeichenfolge kann auf Erfassungs Gruppen verwiesen werden `<substitute>` .</span><span class="sxs-lookup"><span data-stu-id="a7704-225">Capturing groups can be referenced in the `<substitute>` string.</span></span> <span data-ttu-id="a7704-226">Die Ersetzung erfolgt mithilfe des `$` Zeichens vor dem Gruppen Bezeichner.</span><span class="sxs-lookup"><span data-stu-id="a7704-226">The substitution is done by using the `$` character before the group identifier.</span></span>

<span data-ttu-id="a7704-227">Zwei Möglichkeiten, auf Erfassungs Gruppen zu verweisen, sind nach **Nummer** und **Name**.</span><span class="sxs-lookup"><span data-stu-id="a7704-227">Two ways to reference capturing groups are by **Number** and by **Name**.</span></span>

- <span data-ttu-id="a7704-228">Nach **Zahlen** Erfassungs Gruppen werden von links nach rechts nummeriert.</span><span class="sxs-lookup"><span data-stu-id="a7704-228">By **Number** - Capturing Groups are numbered from left to right.</span></span>

  ```powershell
  'John D. Smith' -replace '(\w+) (\w+)\. (\w+)', '$1.$2.$3@contoso.com'
  ```

  ```Output
  John.D.Smith@contoso.com
  ```

- <span data-ttu-id="a7704-229">Nach **Namen** können auch nach Namen Erfassungs Gruppen verwiesen werden.</span><span class="sxs-lookup"><span data-stu-id="a7704-229">By **Name** - Capturing Groups can also be referenced by name.</span></span>

  ```powershell
  'CONTOSO\Administrator' -replace '\w+\\(?<user>\w+)', 'FABRIKAM\${user}'
  ```

  ```Output
  FABRIKAM\Administrator
  ```

<span data-ttu-id="a7704-230">Der `$&` Ausdruck stellt den gesamten übereinstimmenden Text dar.</span><span class="sxs-lookup"><span data-stu-id="a7704-230">The `$&` expression represents all the text matched.</span></span>

```powershell
'Gobble' -replace 'Gobble', '$& $&'
```

```Output
Gobble Gobble
```

> [!WARNING]
> <span data-ttu-id="a7704-231">Da das `$` Zeichen bei der Zeichen folgen Erweiterung verwendet wird, müssen Sie Literalzeichenfolgen mit Ersetzung verwenden oder das `$` Zeichen mit Escapezeichen versehen.</span><span class="sxs-lookup"><span data-stu-id="a7704-231">Since the `$` character is used in string expansion, you'll need to use literal strings with substitution, or escape the `$` character when using double quotes.</span></span>
>
> ```powershell
> 'Hello World' -replace '(\w+) \w+', '$1 Universe'
> "Hello World" -replace "(\w+) \w+", "`$1 Universe"
> ```
>
> ```Output
> Hello Universe
> Hello Universe
> ```
>
> <span data-ttu-id="a7704-232">Wenn Sie `$` als Literalzeichen verwenden möchten, verwenden Sie `$$` anstelle der normalen Escapezeichen.</span><span class="sxs-lookup"><span data-stu-id="a7704-232">Additionally, if you want to have the `$` as a literal character, use `$$` instead of the normal escape characters.</span></span> <span data-ttu-id="a7704-233">Wenn doppelte Anführungszeichen verwendet werden, werden trotzdem alle Instanzen von mit Escapezeichen versehen, `$` um eine falsche Ersetzung</span><span class="sxs-lookup"><span data-stu-id="a7704-233">When using double quotes, still escape all instances of `$` to avoid incorrect substitution.</span></span>
>
> ```powershell
> '5.72' -replace '(.+)', '$$$1'
> "5.72" -replace "(.+)", "`$`$`$1"
> ```
>
> ```Output
> $5.72
> $5.72
> ```

<span data-ttu-id="a7704-234">Weitere Informationen finden Sie unter Ersetzungen [in regulären Ausdrücken](/dotnet/standard/base-types/substitutions-in-regular-expressions).</span><span class="sxs-lookup"><span data-stu-id="a7704-234">For more information, see [Substitutions in Regular Expressions](/dotnet/standard/base-types/substitutions-in-regular-expressions).</span></span>

## <a name="see-also"></a><span data-ttu-id="a7704-235">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a7704-235">See also</span></span>

[<span data-ttu-id="a7704-236">about_Comparison_Operators</span><span class="sxs-lookup"><span data-stu-id="a7704-236">about_Comparison_Operators</span></span>](about_Comparison_Operators.md)

[<span data-ttu-id="a7704-237">about_Operators</span><span class="sxs-lookup"><span data-stu-id="a7704-237">about_Operators</span></span>](about_Operators.md)

