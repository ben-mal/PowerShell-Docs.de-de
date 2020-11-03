---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/21/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertfrom-stringdata?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertFrom-StringData
ms.openlocfilehash: 8ffb7a33bb1b4b5409c48445b88a8eb58f9b93b9
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93216831"
---
# <span data-ttu-id="81b0a-103">ConvertFrom-StringData</span><span class="sxs-lookup"><span data-stu-id="81b0a-103">ConvertFrom-StringData</span></span>

## <span data-ttu-id="81b0a-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="81b0a-104">SYNOPSIS</span></span>
<span data-ttu-id="81b0a-105">Konvertiert eine Zeichenfolge, die mindestens ein Schlüssel-Wert-Paar enthält, in eine Hashtabelle.</span><span class="sxs-lookup"><span data-stu-id="81b0a-105">Converts a string containing one or more key and value pairs to a hash table.</span></span>

## <span data-ttu-id="81b0a-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="81b0a-106">SYNTAX</span></span>

### <span data-ttu-id="81b0a-107">Alle</span><span class="sxs-lookup"><span data-stu-id="81b0a-107">All</span></span>

```
ConvertFrom-StringData [-StringData] <String> [<CommonParameters>]
```

## <span data-ttu-id="81b0a-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="81b0a-108">DESCRIPTION</span></span>

<span data-ttu-id="81b0a-109">Mit dem- `ConvertFrom-StringData` Cmdlet wird eine Zeichenfolge, die ein oder mehrere Schlüssel-Wert-Paare enthält, in eine Hash Tabelle konvertiert.</span><span class="sxs-lookup"><span data-stu-id="81b0a-109">The `ConvertFrom-StringData` cmdlet converts a string that contains one or more key and value pairs into a hash table.</span></span> <span data-ttu-id="81b0a-110">Da sich jedes Schlüssel-Wert-Paar in einer separaten Zeile befinden muss, werden diese Zeichen folgen häufig als Eingabeformat verwendet.</span><span class="sxs-lookup"><span data-stu-id="81b0a-110">Because each key-value pair must be on a separate line, here-strings are often used as the input format.</span></span> <span data-ttu-id="81b0a-111">Standardmäßig muss der **Schlüssel** von dem **Wert** durch ein Gleichheitszeichen () getrennt werden `=` .</span><span class="sxs-lookup"><span data-stu-id="81b0a-111">By default, the **key** must be separated from the **value** by an equals sign (`=`) character.</span></span>

<span data-ttu-id="81b0a-112">Das- `ConvertFrom-StringData` Cmdlet gilt als sicheres Cmdlet, das im- `DATA` Abschnitt eines Skripts oder einer Funktion verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="81b0a-112">The `ConvertFrom-StringData` cmdlet is considered to be a safe cmdlet that can be used in the `DATA` section of a script or function.</span></span> <span data-ttu-id="81b0a-113">Bei Verwendung in einem `DATA` Abschnitt muss der Inhalt der Zeichenfolge den Regeln für einen Daten Abschnitt entsprechen.</span><span class="sxs-lookup"><span data-stu-id="81b0a-113">When used in a `DATA` section, the contents of the string must conform to the rules for a DATA section.</span></span> <span data-ttu-id="81b0a-114">Weitere Informationen finden Sie unter [about_Data_Sections](../Microsoft.PowerShell.Core/About/about_Data_Sections.md).</span><span class="sxs-lookup"><span data-stu-id="81b0a-114">For more information, see [about_Data_Sections](../Microsoft.PowerShell.Core/About/about_Data_Sections.md).</span></span>

<span data-ttu-id="81b0a-115">`ConvertFrom-StringData` unterstützt Escapezeichenfolgen, die von herkömmlichen maschinellen Übersetzungstools zugelassen werden.</span><span class="sxs-lookup"><span data-stu-id="81b0a-115">`ConvertFrom-StringData` supports escape character sequences that are allowed by conventional machine translation tools.</span></span> <span data-ttu-id="81b0a-116">Das heißt, das Cmdlet kann umgekehrte Schrägstriche ( `\` ) als Escapezeichen in den Zeichen folgen Daten mit der [Regex. unescape-Methode und nicht](/dotnet/api/system.text.regularexpressions.regex.unescape)mit dem PowerShell-Graviszeichen-Zeichen () interpretieren, \` das normalerweise das Ende einer Zeile in einem Skript signalisiert.</span><span class="sxs-lookup"><span data-stu-id="81b0a-116">That is, the cmdlet can interpret backslashes (`\`) as escape characters in the string data by using the [Regex.Unescape Method](/dotnet/api/system.text.regularexpressions.regex.unescape), instead of the PowerShell backtick character (\`) that would normally signal the end of a line in a script.</span></span> <span data-ttu-id="81b0a-117">In der here-Zeichenfolge funktioniert das Hochkommazeichen nicht.</span><span class="sxs-lookup"><span data-stu-id="81b0a-117">Inside the here-string, the backtick character does not work.</span></span> <span data-ttu-id="81b0a-118">Sie können auch einen literalen umgekehrten Schrägstrich in den Ergebnissen beibehalten, indem Sie ihn mit einem vorangehenden umgekehrten Schrägstrich versehen, wie folgt: `\\` .</span><span class="sxs-lookup"><span data-stu-id="81b0a-118">You can also preserve a literal backslash in your results by escaping it with a preceding backslash, like this: `\\`.</span></span> <span data-ttu-id="81b0a-119">Umgekehrte Schrägstriche ohne Escapezeichen, wie z. B. solche, die häufig in Dateipfaden verwendet werden, können in den Ergebnissen als unzulässige Escapesequenzen gerendert werden.</span><span class="sxs-lookup"><span data-stu-id="81b0a-119">Unescaped backslash characters, such as those that are commonly used in file paths, can render as illegal escape sequences in your results.</span></span>

## <span data-ttu-id="81b0a-120">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="81b0a-120">EXAMPLES</span></span>

### <span data-ttu-id="81b0a-121">Beispiel 1: Konvertieren einer here-Zeichenfolge in einfachen Anführungszeichen in eine Hash Tabelle</span><span class="sxs-lookup"><span data-stu-id="81b0a-121">Example 1: Convert a single-quoted here-string to a hash table</span></span>

<span data-ttu-id="81b0a-122">In diesem Beispiel wird eine here-Zeichenfolge von Benutzer Nachrichten in einfache Anführungszeichen in eine Hash Tabelle konvertiert.</span><span class="sxs-lookup"><span data-stu-id="81b0a-122">This example converts a single-quoted here-string of user messages into a hash table.</span></span> <span data-ttu-id="81b0a-123">In einer Zeichenfolge in einfachen Anführungszeichen werden Werte nicht durch Variablen ersetzt und Ausdrücke nicht ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="81b0a-123">In a single-quoted string, values are not substituted for variables and expressions are not evaluated.</span></span>
<span data-ttu-id="81b0a-124">Mit dem- `ConvertFrom-StringData` Cmdlet wird der Wert in der- `$Here` Variablen in eine Hash Tabelle konvertiert.</span><span class="sxs-lookup"><span data-stu-id="81b0a-124">The `ConvertFrom-StringData` cmdlet converts the value in the `$Here` variable to a hash table.</span></span>

```powershell
$Here = @'
Msg1 = The string parameter is required.
Msg2 = Credentials are required for this command.
Msg3 = The specified variable does not exist.
'@
ConvertFrom-StringData -StringData $Here
```

```Output
Name                           Value
----                           -----
Msg3                           The specified variable does not exist.
Msg2                           Credentials are required for this command.
Msg1                           The string parameter is required.
```

### <span data-ttu-id="81b0a-125">Beispiel 2: Konvertieren einer here-Zeichenfolge mit einem Kommentar</span><span class="sxs-lookup"><span data-stu-id="81b0a-125">Example 2: Convert a here-string containing a comment</span></span>

<span data-ttu-id="81b0a-126">In diesem Beispiel wird eine here-Zeichenfolge, die einen Kommentar und mehrere Schlüssel-Wert-Paare enthält, in eine Hash Tabelle konvertiert.</span><span class="sxs-lookup"><span data-stu-id="81b0a-126">This example converts a here-string that contains a comment and multiple key-value pairs into a hash table.</span></span>

```powershell
ConvertFrom-StringData -StringData @'
Name = Disks.ps1

# Category is optional.

Category = Storage
Cost = Free
'@
```

```Output
Name                           Value
----                           -----
Cost                           Free
Category                       Storage
Name                           Disks.ps1
```

<span data-ttu-id="81b0a-127">Der Wert des **StringData** -Parameters ist eine here-Zeichenfolge anstelle einer Variablen, die eine here-Zeichenfolge enthält.</span><span class="sxs-lookup"><span data-stu-id="81b0a-127">The value of the **StringData** parameter is a here-string, instead of a variable that contains a here-string.</span></span> <span data-ttu-id="81b0a-128">Beide Formate sind gültig.</span><span class="sxs-lookup"><span data-stu-id="81b0a-128">Either format is valid.</span></span> <span data-ttu-id="81b0a-129">Die here-Zeichenfolge enthält einen Kommentar zu einer der Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="81b0a-129">The here-string includes a comment about one of the strings.</span></span>
<span data-ttu-id="81b0a-130">`ConvertFrom-StringData` ignoriert einzeilige Kommentare, aber das `#` Zeichen muss das erste Zeichen in der Zeile sein, das kein Leerzeichen ist.</span><span class="sxs-lookup"><span data-stu-id="81b0a-130">`ConvertFrom-StringData` ignores single-line comments, but the `#` character must be the first non-whitespace character on the line.</span></span> <span data-ttu-id="81b0a-131">Alle Zeichen in der Zeile nach dem `#` werden ignoriert.</span><span class="sxs-lookup"><span data-stu-id="81b0a-131">All characters on the line after the `#` are ignored.</span></span>

### <span data-ttu-id="81b0a-132">Beispiel 3: Konvertieren einer Zeichenfolge in eine Hash Tabelle</span><span class="sxs-lookup"><span data-stu-id="81b0a-132">Example 3: Convert a string to a hash table</span></span>

<span data-ttu-id="81b0a-133">In diesem Beispiel wird eine reguläre Zeichenfolge in doppelten Anführungszeichen (keine here-Zeichenfolge) in eine Hash Tabelle konvertiert und in der `$A` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="81b0a-133">This example converts a regular double-quoted string (not a here-string) into a hash table and saves it in the `$A` variable.</span></span>

```powershell
$A = ConvertFrom-StringData -StringData "Top = Red `n Bottom = Blue"
$A
```

```Output
Name             Value
----             -----
Bottom           Blue
Top              Red
```

<span data-ttu-id="81b0a-134">Um die Bedingung zu erfüllen, dass sich jedes Schlüssel-Wert-Paar in einer separaten Zeile befinden muss, verwendet die Zeichenfolge das PowerShell-Zeilen vorformat ( \` n), um die Paare voneinander zu trennen.</span><span class="sxs-lookup"><span data-stu-id="81b0a-134">To satisfy the condition that each key-value pair must be on a separate line, the string uses the PowerShell newline character (\`n) to separate the pairs.</span></span>

### <span data-ttu-id="81b0a-135">Beispiel 4: Verwenden von ConvertFrom-StringData im Daten Abschnitt eines Skripts</span><span class="sxs-lookup"><span data-stu-id="81b0a-135">Example 4: Use ConvertFrom-StringData in the DATA section of a script</span></span>

<span data-ttu-id="81b0a-136">Dieses Beispiel zeigt einen `ConvertFrom-StringData` Befehl, der im Daten Abschnitt eines Skripts verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="81b0a-136">This example shows a `ConvertFrom-StringData` command used in the DATA section of a script.</span></span>
<span data-ttu-id="81b0a-137">Die Anweisungen unter dem DATA-Abschnitt zeigen den Text für den Benutzer an.</span><span class="sxs-lookup"><span data-stu-id="81b0a-137">The statements below the DATA section display the text to the user.</span></span>

```powershell
$TextMsgs = DATA {
ConvertFrom-StringData @'
Text001 = The $Notebook variable contains the name of the user's system notebook.
Text002 = The $MyNotebook variable contains the name of the user's private notebook.
'@
}
$TextMsgs
```

```Output
Name             Value
----             -----
Text001          The $Notebook variable contains the name of the user's system notebook.
Text002          The $MyNotebook variable contains the name of the user's private notebook.
```

<span data-ttu-id="81b0a-138">Da der Text Variablennamen enthält, muss er in einer Zeichenfolge in einfachen Anführungszeichen eingeschlossen werden, damit die Variablen wörtlich interpretiert und nicht erweitert werden.</span><span class="sxs-lookup"><span data-stu-id="81b0a-138">Because the text includes variable names, it must be enclosed in a single-quoted string so that the variables are interpreted literally and not expanded.</span></span> <span data-ttu-id="81b0a-139">Variablen sind im **Data** -Abschnitt nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="81b0a-139">Variables are not permitted in the **DATA** section.</span></span>

### <span data-ttu-id="81b0a-140">Beispiel 5: Verwenden des Pipeline-Operators zum Übergeben einer Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="81b0a-140">Example 5: Use the pipeline operator to pass a string</span></span>

<span data-ttu-id="81b0a-141">Dieses Beispiel zeigt, dass Sie einen Pipeline Operator () verwenden können, um `|` eine Zeichenfolge an zu senden `ConvertFrom-StringData` .</span><span class="sxs-lookup"><span data-stu-id="81b0a-141">This example shows that you can use a pipeline operator (`|`) to send a string to `ConvertFrom-StringData`.</span></span> <span data-ttu-id="81b0a-142">Der Wert der `$Here` Variablen wird an weitergeleitet `ConvertFrom-StringData` und das Ergebnis in der `$Hash` Variablen.</span><span class="sxs-lookup"><span data-stu-id="81b0a-142">The the value of the `$Here` variable is piped to `ConvertFrom-StringData` and the result in the `$Hash` variable.</span></span>

```powershell
$Here = @'
Msg1 = The string parameter is required.
Msg2 = Credentials are required for this command.
Msg3 = The specified variable does not exist.
'@
$Hash = $Here | ConvertFrom-StringData
$Hash
```

```Output
Name     Value
----     -----
Msg3     The specified variable does not exist.
Msg2     Credentials are required for this command.
Msg1     The string parameter is required.
```

### <span data-ttu-id="81b0a-143">Beispiel 6: Verwenden von Escapezeichen zum Hinzufügen neuer Zeilen und Zurückgeben von Zeichen</span><span class="sxs-lookup"><span data-stu-id="81b0a-143">Example 6: Use escape characters to add new lines and return characters</span></span>

<span data-ttu-id="81b0a-144">Dieses Beispiel zeigt die Verwendung von Escapezeichen zum Erstellen neuer Zeilen und zum Zurückgeben von Zeichen in den Quelldaten.</span><span class="sxs-lookup"><span data-stu-id="81b0a-144">This example shows the use of escape characters to create new lines and return characters in source data.</span></span> <span data-ttu-id="81b0a-145">Die Escapesequenz `\n` wird verwendet, um neue Zeilen in einem TextBlock zu erstellen, der mit einem Namen oder einem Element in der resultierenden Hash Tabelle verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="81b0a-145">The escape sequence `\n` is used to create new lines within a block of text that is associated with a name or item in the resulting hash table.</span></span>

```powershell
ConvertFrom-StringData @"
Vincentio = Heaven doth with us as we with torches do,\nNot light them for themselves; for if our virtues\nDid not go forth of us, 'twere all alike\nAs if we had them not.
Angelo = Let there be some more test made of my metal,\nBefore so noble and so great a figure\nBe stamp'd upon it.
"@ | Format-List
```

```Output
Name  : Angelo
Value : Let there be some more test made of my metal,
        Before so noble and so great a figure
        Be stamp'd upon it.

Name  : Vincentio
Value : Heaven doth with us as we with torches do,
        Not light them for themselves; for if our virtues
        Did not go forth of us, 'twere all alike
        As if we had them not.
```

### <span data-ttu-id="81b0a-146">Beispiel 7: Verwenden eines umgekehrten Schrägstrichs zum ordnungsgemäßen Rendering eines Dateipfads</span><span class="sxs-lookup"><span data-stu-id="81b0a-146">Example 7: Use backslash escape character to correctly render a file path</span></span>

<span data-ttu-id="81b0a-147">In diesem Beispiel wird gezeigt, wie der umgekehrte Schrägstrich-Escapezeichen in den Zeichen folgen Daten verwendet wird, damit ein Dateipfad in der resultierenden Hash Tabelle ordnungsgemäß dargestellt werden kann `ConvertFrom-StringData` .</span><span class="sxs-lookup"><span data-stu-id="81b0a-147">This example shows how to use of the backslash escape character in the string data to allow a file path to render correctly in the resulting `ConvertFrom-StringData` hash table.</span></span> <span data-ttu-id="81b0a-148">Der doppelte umgekehrte Schrägstrich stellt sicher, dass der umgekehrte Literalschrägstrich in der Ausgabe der Hashtabelle ordnungsgemäß gerendert wird.</span><span class="sxs-lookup"><span data-stu-id="81b0a-148">The double backslash ensures that the literal backslash characters render correctly in the hash table output.</span></span>

```powershell
ConvertFrom-StringData "Message=Look in c:\\Windows\\System32"
```

```Output
Name                           Value
----                           -----
Message                        Look in c:\Windows\System32
```

## <span data-ttu-id="81b0a-149">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="81b0a-149">PARAMETERS</span></span>

### <span data-ttu-id="81b0a-150">-StringData</span><span class="sxs-lookup"><span data-stu-id="81b0a-150">-StringData</span></span>

<span data-ttu-id="81b0a-151">Gibt die zu konvertierende Zeichenfolge an.</span><span class="sxs-lookup"><span data-stu-id="81b0a-151">Specifies the string to be converted.</span></span> <span data-ttu-id="81b0a-152">Sie können diesen Parameter verwenden oder eine Zeichenfolge an die Pipeline übergeben `ConvertFrom-StringData` .</span><span class="sxs-lookup"><span data-stu-id="81b0a-152">You can use this parameter or pipe a string to `ConvertFrom-StringData`.</span></span> <span data-ttu-id="81b0a-153">Der Parametername ist optional.</span><span class="sxs-lookup"><span data-stu-id="81b0a-153">The parameter name is optional.</span></span>

<span data-ttu-id="81b0a-154">Der Wert dieses Parameters muss eine Zeichenfolge sein, die mindestens ein Schlüssel-Wert-Paar enthält.</span><span class="sxs-lookup"><span data-stu-id="81b0a-154">The value of this parameter must be a string that contains one or more key-value pairs.</span></span> <span data-ttu-id="81b0a-155">Jedes Schlüssel-Wert-Paar muss sich in einer separaten Zeile befinden, oder jedes Paar muss durch Zeilen vorzeichenzeichen ( \` n) getrennt werden.</span><span class="sxs-lookup"><span data-stu-id="81b0a-155">Each key-value pair must be on a separate line, or each pair must be separated by newline characters (\`n).</span></span>

<span data-ttu-id="81b0a-156">Sie können Kommentare in die Zeichenfolge einschließen, aber die Kommentare dürfen sich nicht in derselben Zeile wie ein Schlüssel-Wert-Paar befinden.</span><span class="sxs-lookup"><span data-stu-id="81b0a-156">You can include comments in the string, but the comments cannot be on the same line as a key-value pair.</span></span> <span data-ttu-id="81b0a-157">`ConvertFrom-StringData` ignoriert einzeilige Kommentare.</span><span class="sxs-lookup"><span data-stu-id="81b0a-157">`ConvertFrom-StringData` ignores single-line comments.</span></span> <span data-ttu-id="81b0a-158">Das `#` Zeichen muss das erste Zeichen in der Zeile sein, das kein Leerzeichen ist.</span><span class="sxs-lookup"><span data-stu-id="81b0a-158">The `#` character must be the first non-whitespace character on the line.</span></span> <span data-ttu-id="81b0a-159">Alle Zeichen in der Zeile nach dem `#` werden ignoriert.</span><span class="sxs-lookup"><span data-stu-id="81b0a-159">All characters on the line after the `#` are ignored.</span></span> <span data-ttu-id="81b0a-160">Die Kommentare sind nicht in der Hashtabelle enthalten.</span><span class="sxs-lookup"><span data-stu-id="81b0a-160">The comments are not included in the hash table.</span></span>

<span data-ttu-id="81b0a-161">Eine here-Zeichenfolge ist eine Zeichenfolge, die aus einer oder mehreren Zeilen besteht.</span><span class="sxs-lookup"><span data-stu-id="81b0a-161">A here-string is a string consisting of one or more lines.</span></span> <span data-ttu-id="81b0a-162">Anführungszeichen in der here-Zeichenfolge werden buchstäblich als Teil der Zeichen folgen Daten interpretiert.</span><span class="sxs-lookup"><span data-stu-id="81b0a-162">Quotation marks within the here-string are interpreted literally as part of the string data.</span></span> <span data-ttu-id="81b0a-163">Weitere Informationen finden Sie unter [about_Quoting_Rules](../Microsoft.PowerShell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="81b0a-163">For more information, see [about_Quoting_Rules](../Microsoft.PowerShell.Core/About/about_Quoting_Rules.md).</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="81b0a-164">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="81b0a-164">CommonParameters</span></span>

<span data-ttu-id="81b0a-165">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="81b0a-165">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="81b0a-166">Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="81b0a-166">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="81b0a-167">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="81b0a-167">INPUTS</span></span>

### <span data-ttu-id="81b0a-168">System.String</span><span class="sxs-lookup"><span data-stu-id="81b0a-168">System.String</span></span>

<span data-ttu-id="81b0a-169">Sie können eine Zeichenfolge mit einem Schlüssel-Wert-Paar über die Pipeline an übergeben `ConvertFrom-StringData` .</span><span class="sxs-lookup"><span data-stu-id="81b0a-169">You can pipe a string containing a key-value pair to `ConvertFrom-StringData`.</span></span>

## <span data-ttu-id="81b0a-170">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="81b0a-170">OUTPUTS</span></span>

### <span data-ttu-id="81b0a-171">System.Collections.Hashtable</span><span class="sxs-lookup"><span data-stu-id="81b0a-171">System.Collections.Hashtable</span></span>

<span data-ttu-id="81b0a-172">Dieses Cmdlet gibt eine Hash Tabelle zurück, die aus den Schlüssel-Wert-Paaren erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="81b0a-172">This cmdlet returns a hash table that it creates from the key-value pairs.</span></span>

## <span data-ttu-id="81b0a-173">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="81b0a-173">NOTES</span></span>

<span data-ttu-id="81b0a-174">Eine here-Zeichenfolge ist eine Zeichenfolge, die aus mindestens einer Zeile besteht und in der Anführungszeichen als solche interpretiert werden.</span><span class="sxs-lookup"><span data-stu-id="81b0a-174">A here-string is a string consisting of one or more lines within which quotation marks are interpreted literally.</span></span>

<span data-ttu-id="81b0a-175">Dieses Cmdlet kann in Skripts hilfreich sein, in denen Benutzer Meldungen in mehreren gesprochenen Sprachen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="81b0a-175">This cmdlet can be useful in scripts that display user messages in multiple spoken languages.</span></span> <span data-ttu-id="81b0a-176">Sie können die wörterbuchähnlichen Hashtabellen verwenden, um Textzeichenfolgen z. B. in Ressourcendateien von Code zu isolieren und die Textzeichenfolgen für die Verwendung in Übersetzungstools zu formatieren.</span><span class="sxs-lookup"><span data-stu-id="81b0a-176">You can use the dictionary-style hash tables to isolate text strings from code, such as in resource files, and to format the text strings for use in translation tools.</span></span>

## <span data-ttu-id="81b0a-177">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="81b0a-177">RELATED LINKS</span></span>
