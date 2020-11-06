---
title: Grundlegendes zur Dateicodierung in VS Code und PowerShell
description: Konfigurieren der Dateicodierung in VS Code und PowerShell
ms.date: 02/28/2019
ms.openlocfilehash: afad189ff20a4e73d25f15c48d6c4982b18f29a3
ms.sourcegitcommit: 196c7f8cd24560cac70c88acc89909f17a86aea9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2020
ms.locfileid: "93142547"
---
# <a name="understanding-file-encoding-in-vs-code-and-powershell"></a><span data-ttu-id="e11e0-103">Grundlegendes zur Dateicodierung in VS Code und PowerShell</span><span class="sxs-lookup"><span data-stu-id="e11e0-103">Understanding file encoding in VS Code and PowerShell</span></span>

<span data-ttu-id="e11e0-104">Wenn Sie mit VS Code PowerShell-Skripts erstellen und bearbeiten, ist es wichtig, dass Ihre Dateien im korrekten Zeichencodierungsformat gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="e11e0-104">When using VS Code to create and edit PowerShell scripts, it is important that your files are saved using the correct character encoding format.</span></span>

## <a name="what-is-file-encoding-and-why-is-it-important"></a><span data-ttu-id="e11e0-105">Was ist die Dateicodierung und weshalb ist sie wichtig?</span><span class="sxs-lookup"><span data-stu-id="e11e0-105">What is file encoding and why is it important?</span></span>

<span data-ttu-id="e11e0-106">VS Code fungiert als Schnittstelle zwischen einem Menschen, der Zeichenfolgen in einen Puffer eingibt, und dem Lesen/Schreiben von Byteblocks in das Dateisystem.</span><span class="sxs-lookup"><span data-stu-id="e11e0-106">VS Code manages the interface between a human entering strings of characters into a buffer and reading/writing blocks of bytes to the filesystem.</span></span> <span data-ttu-id="e11e0-107">Wenn VS Code eine Datei speichert, wird mithilfe einer Textcodierung festgelegt, in welche Bytes jedes Zeichen umgewandelt wird.</span><span class="sxs-lookup"><span data-stu-id="e11e0-107">When VS Code saves a file, it uses a text encoding to decide what bytes each character becomes.</span></span> <span data-ttu-id="e11e0-108">Weitere Informationen finden Sie unter [about_Character_Encoding](/powershell/module/microsoft.powershell.core/about/about_character_encoding).</span><span class="sxs-lookup"><span data-stu-id="e11e0-108">For more information, see [about_Character_Encoding](/powershell/module/microsoft.powershell.core/about/about_character_encoding).</span></span>

<span data-ttu-id="e11e0-109">Wenn PowerShell ein Skript ausführt, muss es die Bytes in einer Datei entsprechend in Zeichen konvertieren, um die Datei in einem PowerShell-Programm zu rekonstruieren.</span><span class="sxs-lookup"><span data-stu-id="e11e0-109">Similarly, when PowerShell runs a script it must convert the bytes in a file to characters to reconstruct the file into a PowerShell program.</span></span> <span data-ttu-id="e11e0-110">Da VS Code die Datei schreibt und PowerShell diese liest, müssen sie dasselbe Codierungssystem verwenden.</span><span class="sxs-lookup"><span data-stu-id="e11e0-110">Since VS Code writes the file and PowerShell reads the file, they need to use the same encoding system.</span></span> <span data-ttu-id="e11e0-111">Die Analyse eines PowerShell-Skripts sieht folgendermaßen aus: _Bytes_ -> _Zeichen_ -> _Token_ -> _abstrakte Syntaxstruktur_ -> _Ausführung_.</span><span class="sxs-lookup"><span data-stu-id="e11e0-111">This process of parsing a PowerShell script goes: _bytes_ -> _characters_ -> _tokens_ -> _abstract syntax tree_ -> _execution_.</span></span>

<span data-ttu-id="e11e0-112">Sowohl VS Code als auch PowerShell werden mit einer zweckmäßigen Standardcodierungskonfiguration installiert.</span><span class="sxs-lookup"><span data-stu-id="e11e0-112">Both VS Code and PowerShell are installed with a sensible default encoding configuration.</span></span> <span data-ttu-id="e11e0-113">Mit der Veröffentlichung von PowerShell Core v6.x hat sich die Standardcodierung von PowerShell jedoch geändert.</span><span class="sxs-lookup"><span data-stu-id="e11e0-113">However, the default encoding used by PowerShell has changed with the release of PowerShell Core (v6.x).</span></span> <span data-ttu-id="e11e0-114">Legen Sie Ihre VS Code- und PowerShell-Einstellungen entsprechend fest, um sicherzustellen, dass bei der Verwendung von PowerShell oder einer PowerShell-Erweiterung in VS Code keine Probleme auftreten.</span><span class="sxs-lookup"><span data-stu-id="e11e0-114">To ensure you have no problems using PowerShell or the PowerShell extension in VS Code, you need to configure your VS Code and PowerShell settings properly.</span></span>

## <a name="common-causes-of-encoding-issues"></a><span data-ttu-id="e11e0-115">Häufige Gründe für Codierungsprobleme</span><span class="sxs-lookup"><span data-stu-id="e11e0-115">Common causes of encoding issues</span></span>

<span data-ttu-id="e11e0-116">Codierungsprobleme treten auf, wenn die Codierung von VS Code oder der Skriptdatei nicht der Codierung entspricht, die von PowerShell erwartet wird.</span><span class="sxs-lookup"><span data-stu-id="e11e0-116">Encoding problems occur when the encoding of VS Code or your script file does not match the expected encoding of PowerShell.</span></span> <span data-ttu-id="e11e0-117">PowerShell hat keine Möglichkeit, die Dateicodierung automatisch zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="e11e0-117">There is no way for PowerShell to automatically determine the file encoding.</span></span>

<span data-ttu-id="e11e0-118">Es ist wahrscheinlicher, dass Codierungsprobleme auftreten, wenn Sie Zeichen verwenden, die nicht im [7-Bit-ASCII-Zeichensatz](https://ascii.cl/) enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="e11e0-118">You're more likely to have encoding problems when you're using characters not in the [7-bit ASCII character set](https://ascii.cl/).</span></span> <span data-ttu-id="e11e0-119">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="e11e0-119">For example:</span></span>

<!-- markdownlint-disable MD038 -->
- <span data-ttu-id="e11e0-120">Erweiterte Zeichen, bei denen es sich nicht um Buchstaben handelt – z. B. Geviertstrich (`—`), geschützte Leerzeichen (` `) oder doppelte linke Anführungszeichen (`"`)</span><span class="sxs-lookup"><span data-stu-id="e11e0-120">Extended non-letter characters like em-dash (`—`), non-breaking space (` `) or left double quotation mark (`"`)</span></span>
- <span data-ttu-id="e11e0-121">Lateinische Buchstaben mit Akzenten und Umlaute (`É`, `ü`)</span><span class="sxs-lookup"><span data-stu-id="e11e0-121">Accented latin characters (`É`, `ü`)</span></span>
- <span data-ttu-id="e11e0-122">Nicht lateinische Zeichen wie Kyrillisch (`Д`, `Ц`)</span><span class="sxs-lookup"><span data-stu-id="e11e0-122">Non-latin characters like Cyrillic (`Д`, `Ц`)</span></span>
- <span data-ttu-id="e11e0-123">CJK-Zeichen (`本`, `화`, `が`)</span><span class="sxs-lookup"><span data-stu-id="e11e0-123">CJK characters (`本`, `화`, `が`)</span></span>

<span data-ttu-id="e11e0-124">Aus den folgenden Gründen kann es zu Codierungsproblemen kommen:</span><span class="sxs-lookup"><span data-stu-id="e11e0-124">Common reasons for encoding issues are:</span></span>

- <span data-ttu-id="e11e0-125">Die Codierungen von VS Code und PowerShell weisen immer noch die Standardeinstellungen auf.</span><span class="sxs-lookup"><span data-stu-id="e11e0-125">The encodings of VS Code and PowerShell have not been changed from their defaults.</span></span> <span data-ttu-id="e11e0-126">Für PowerShell 5.1 und früher unterscheidet sich die Standardcodierung von derjenigen von VS Code.</span><span class="sxs-lookup"><span data-stu-id="e11e0-126">For PowerShell 5.1 and below, the default encoding is different from VS Code's.</span></span>
- <span data-ttu-id="e11e0-127">Ein weiterer Editor wurde geöffnet und hat die Datei in einer neuen Codierung überschrieben.</span><span class="sxs-lookup"><span data-stu-id="e11e0-127">Another editor has opened and overwritten the file in a new encoding.</span></span> <span data-ttu-id="e11e0-128">Dies geschieht häufig mit der ISE.</span><span class="sxs-lookup"><span data-stu-id="e11e0-128">This often happens with the ISE.</span></span>
- <span data-ttu-id="e11e0-129">Die Datei wird in der Quellcodeverwaltung in einer Codierung eingecheckt, die sich von der von VS Code bzw. PowerShell erwarteten Codierung unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="e11e0-129">The file is checked into source control in an encoding that is different from what VS Code or PowerShell expects.</span></span> <span data-ttu-id="e11e0-130">Das kann passieren, wenn Beteiligte einen Editor mit anderen Codierungskonfigurationen verwenden.</span><span class="sxs-lookup"><span data-stu-id="e11e0-130">This can happen when collaborators use editors with different encoding configurations.</span></span>

### <a name="how-to-tell-when-you-have-encoding-issues"></a><span data-ttu-id="e11e0-131">Erkennen von Codierungsproblemen</span><span class="sxs-lookup"><span data-stu-id="e11e0-131">How to tell when you have encoding issues</span></span>

<span data-ttu-id="e11e0-132">Codierungsfehler treten häufig als Analysefehler in Skripts auf.</span><span class="sxs-lookup"><span data-stu-id="e11e0-132">Often encoding errors present themselves as parse errors in scripts.</span></span> <span data-ttu-id="e11e0-133">Wenn Sie in Ihren Skripts ungewöhnliche Zeichensequenzen sehen, kann das der Grund für das Problem sein.</span><span class="sxs-lookup"><span data-stu-id="e11e0-133">If you find strange character sequences in your script, this can be the problem.</span></span> <span data-ttu-id="e11e0-134">Im Beispiel unten wird ein Halbgeviertstrich (`–`) als `â&euro;"` angezeigt:</span><span class="sxs-lookup"><span data-stu-id="e11e0-134">In the example below, an en-dash (`–`) appears as the characters `â&euro;"`:</span></span>

```Output
Send-MailMessage : A positional parameter cannot be found that accepts argument 'Testing FuseMail SMTP...'.
At C:\Users\<User>\<OneDrive>\Development\PowerShell\Scripts\Send-EmailUsingSmtpRelay.ps1:6 char:1
+ Send-MailMessage â&euro;"From $from â&euro;"To $recipient1 â&euro;"Subject $subject  ...
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidArgument: (:) [Send-MailMessage], ParameterBindingException
    + FullyQualifiedErrorId : PositionalParameterNotFound,Microsoft.PowerShell.Commands.SendMailMessage
```

<span data-ttu-id="e11e0-135">Dieses Problem tritt auf, weil VS Code das Zeichen `–` in UTF-8 als `0xE2 0x80 0x93` codiert.</span><span class="sxs-lookup"><span data-stu-id="e11e0-135">This problem occurs because VS Code encodes the character `–` in UTF-8 as the bytes `0xE2 0x80 0x93`.</span></span> <span data-ttu-id="e11e0-136">Wenn diese Bytes als Windows-1252 decodiert werden, werden sie als die Zeichen `â&euro;"` interpretiert.</span><span class="sxs-lookup"><span data-stu-id="e11e0-136">When these bytes are decoded as Windows-1252, they are interpreted as the characters `â&euro;"`.</span></span>

<span data-ttu-id="e11e0-137">Weitere ungewöhnliche Zeichensequenzen, die Sie eventuell sehen, sind die folgenden:</span><span class="sxs-lookup"><span data-stu-id="e11e0-137">Some strange character sequences that you might see include:</span></span>

<!-- markdownlint-disable MD038 -->
- <span data-ttu-id="e11e0-138">`â&euro;"` anstelle von `–`</span><span class="sxs-lookup"><span data-stu-id="e11e0-138">`â&euro;"` instead of `–`</span></span>
- <span data-ttu-id="e11e0-139">`â&euro;"` anstelle von `—`</span><span class="sxs-lookup"><span data-stu-id="e11e0-139">`â&euro;"` instead of `—`</span></span>
- <span data-ttu-id="e11e0-140">`Ã„2` anstelle von `Ä`</span><span class="sxs-lookup"><span data-stu-id="e11e0-140">`Ã„2` instead of `Ä`</span></span>
- <span data-ttu-id="e11e0-141">`Â` anstelle von ` ` (ein geschütztes Leerzeichen)</span><span class="sxs-lookup"><span data-stu-id="e11e0-141">`Â` instead of ` `  (a non-breaking space)</span></span>
- <span data-ttu-id="e11e0-142">`Ã&copy;` anstelle von `é`</span><span class="sxs-lookup"><span data-stu-id="e11e0-142">`Ã&copy;` instead of `é`</span></span>
<!-- markdownlint-enable MD038 -->

<span data-ttu-id="e11e0-143">In dieser praktischen [Referenz](https://www.i18nqa.com/debug/utf8-debug.html) werden gängige Muster aufgelistet, die auf Codierungsprobleme zwischen UTF-8 und Windows-1252 hindeuten.</span><span class="sxs-lookup"><span data-stu-id="e11e0-143">This handy [reference](https://www.i18nqa.com/debug/utf8-debug.html) lists the common patterns that indicate a UTF-8/Windows-1252 encoding problem.</span></span>

## <a name="how-the-powershell-extension-in-vs-code-interacts-with-encodings"></a><span data-ttu-id="e11e0-144">Interaktion der PowerShell-Erweiterung in VS Code mit Codierungen</span><span class="sxs-lookup"><span data-stu-id="e11e0-144">How the PowerShell extension in VS Code interacts with encodings</span></span>

<span data-ttu-id="e11e0-145">Die PowerShell-Erweiterung interagiert auf unterschiedliche Weise mit den Skripts:</span><span class="sxs-lookup"><span data-stu-id="e11e0-145">The PowerShell extension interacts with scripts in a number of ways:</span></span>

1. <span data-ttu-id="e11e0-146">Wenn Skripts in VS Code bearbeitet werden, werden die Inhalte von VS Code an die Erweiterung gesendet.</span><span class="sxs-lookup"><span data-stu-id="e11e0-146">When scripts are edited in VS Code, the contents are sent by VS Code to the extension.</span></span> <span data-ttu-id="e11e0-147">Das [Sprachserverprotokoll][] gibt vor, dass dieser Inhalt in UTF-8 übertragen wird.</span><span class="sxs-lookup"><span data-stu-id="e11e0-147">The [Language Server Protocol][] mandates that this content is transferred in UTF-8.</span></span> <span data-ttu-id="e11e0-148">Deshalb ist es gar nicht möglich, dass die Erweiterung den Inhalt in einer falschen Codierung erhält.</span><span class="sxs-lookup"><span data-stu-id="e11e0-148">Therefore, it is not possible for the extension to get the wrong encoding.</span></span>
1. <span data-ttu-id="e11e0-149">Wenn Skripts direkt in der integrierten Konsole ausgeführt werden, liest PowerShell diese direkt aus der Datei.</span><span class="sxs-lookup"><span data-stu-id="e11e0-149">When scripts are executed directly in the Integrated Console, they're read from the file by PowerShell directly.</span></span> <span data-ttu-id="e11e0-150">Wenn die Codierung von PowerShell sich von derjenigen von VS Code unterscheidet, kann es zu Problemen kommen.</span><span class="sxs-lookup"><span data-stu-id="e11e0-150">If PowerShell's encoding differs from VS Code's, something can go wrong here.</span></span>
1. <span data-ttu-id="e11e0-151">Wenn ein Skript, das in VS Code geöffnet wird, auf ein anderes Skript verweist, das nicht in VS Code geöffnet ist, lädt die Erweiterung den Inhalt dieses Skripts aus dem Dateisystem.</span><span class="sxs-lookup"><span data-stu-id="e11e0-151">When a script that is open in VS Code references another script that is not open in VS Code, the extension falls back to loading that script's content from the file system.</span></span> <span data-ttu-id="e11e0-152">Die Standardeinstellung der PowerShell-Erweiterung ist UTF-8. Die Erkennung der [Bytereihenfolge-Marke][] oder Byte-Order Mark (BOM) wird jedoch verwendet, um die korrekte Codierung auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="e11e0-152">The PowerShell extension defaults to UTF-8 encoding, but uses [byte-order mark][], or BOM, detection to select the correct encoding.</span></span>

<span data-ttu-id="e11e0-153">Das Problem tritt auf, wenn die Codierung von Formaten ohne BOM angenommen wird (z.B. [UTF-8][] ohne BOM und [Windows-1252][]).</span><span class="sxs-lookup"><span data-stu-id="e11e0-153">The problem occurs when assuming the encoding of BOM-less formats (like [UTF-8][] with no BOM and [Windows-1252][]).</span></span> <span data-ttu-id="e11e0-154">Die Standardeinstellung der PowerShell-Erweiterung ist UTF-8.</span><span class="sxs-lookup"><span data-stu-id="e11e0-154">The PowerShell extension defaults to UTF-8.</span></span> <span data-ttu-id="e11e0-155">Die Erweiterung kann die Codierungseinstellungen von VS Code nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="e11e0-155">The extension cannot change VS Code's encoding settings.</span></span> <span data-ttu-id="e11e0-156">Weitere Informationen finden Sie im [Issue #824](https://github.com/Microsoft/VSCode/issues/824).</span><span class="sxs-lookup"><span data-stu-id="e11e0-156">For more information, see [issue #824](https://github.com/Microsoft/VSCode/issues/824).</span></span>

## <a name="choosing-the-right-encoding"></a><span data-ttu-id="e11e0-157">Entscheidung für die richtige Codierung</span><span class="sxs-lookup"><span data-stu-id="e11e0-157">Choosing the right encoding</span></span>

<span data-ttu-id="e11e0-158">Unterschiedliche Systeme und Anwendungen können unterschiedliche Codierungen verwenden:</span><span class="sxs-lookup"><span data-stu-id="e11e0-158">Different systems and applications can use different encodings:</span></span>

- <span data-ttu-id="e11e0-159">In .NET Standard, im Internet und im Zusammenhang mit Linux ist UTF-8 mittlerweile die häufigste Codierung.</span><span class="sxs-lookup"><span data-stu-id="e11e0-159">In .NET Standard, on the web, and in the Linux world, UTF-8 is now the dominant encoding.</span></span>
- <span data-ttu-id="e11e0-160">Viele .NET Framework-Anwendungen verwenden [UTF-16][].</span><span class="sxs-lookup"><span data-stu-id="e11e0-160">Many .NET Framework applications use [UTF-16][].</span></span> <span data-ttu-id="e11e0-161">Aus historischen Gründen wird dies manchmal als „Unicode“ bezeichnet, ein Begriff, der mittlerweile einen breiten [Standard](https://en.wikipedia.org/wiki/Unicode) bezeichnet, der sowohl UTF-8 als auch UTF-16 umfasst.</span><span class="sxs-lookup"><span data-stu-id="e11e0-161">For historical reasons, this is sometimes called "Unicode", a term that now refers to a broad [standard](https://en.wikipedia.org/wiki/Unicode) that includes both UTF-8 and UTF-16.</span></span>
- <span data-ttu-id="e11e0-162">Unter Windows verwenden native Anwendungen aus der Zeit vor Unicode weiterhin standardmäßig Windows-1252.</span><span class="sxs-lookup"><span data-stu-id="e11e0-162">On Windows, many native applications that predate Unicode continue to use Windows-1252 by default.</span></span>

<span data-ttu-id="e11e0-163">Unicodecodierungen verwenden auch Bytereihenfolge-Marken.</span><span class="sxs-lookup"><span data-stu-id="e11e0-163">Unicode encodings also have the concept of a byte-order mark (BOM).</span></span> <span data-ttu-id="e11e0-164">BOMs stehen am Textanfang, um einen Decoder darüber zu informieren, welche Codierung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e11e0-164">BOMs occur at the beginning of text to tell a decoder which encoding the text is using.</span></span> <span data-ttu-id="e11e0-165">Für Mehrbytecodierungen gibt die BOM auch die [Bytereihenfolge](https://en.wikipedia.org/wiki/Endianness) der Codierung an.</span><span class="sxs-lookup"><span data-stu-id="e11e0-165">For multi-byte encodings, the BOM also indicates [endianness](https://en.wikipedia.org/wiki/Endianness) of the encoding.</span></span> <span data-ttu-id="e11e0-166">BOMs sollen Bytes sein, die nur selten in Nicht-Unicodetexten auftauchen, sodass eine vorhandene BOM darauf hinweist, dass ein Text mit hoher Wahrscheinlichkeit Unicode ist.</span><span class="sxs-lookup"><span data-stu-id="e11e0-166">BOMs are designed to be bytes that rarely occur in non-Unicode text, allowing a reasonable guess that text is Unicode when a BOM is present.</span></span>

<span data-ttu-id="e11e0-167">BOMs sind optional und ihre Verwendung ist im Linux-Kontext nicht sonderlich beliebt, da eine verlässliche UTF-8-Konvention überall verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e11e0-167">BOMs are optional and their adoption isn't as popular in the Linux world because a dependable convention of UTF-8 is used everywhere.</span></span> <span data-ttu-id="e11e0-168">Die meisten Linux-Anwendungen gehen davon aus, dass Eingaben in UTF-8 codiert sind.</span><span class="sxs-lookup"><span data-stu-id="e11e0-168">Most Linux applications presume that text input is encoded in UTF-8.</span></span> <span data-ttu-id="e11e0-169">Die meisten Linux-Anwendungen erkennen eine BOM ordnungsgemäß und verarbeiten sie richtig. Einige Anwendungen erkennen sie jedoch nicht, was in Texten, die mit diesen Anwendungen bearbeitet wurden, zu ungewollten Abweichungen führt.</span><span class="sxs-lookup"><span data-stu-id="e11e0-169">While many Linux applications will recognize and correctly handle a BOM, a number do not, leading to artifacts in text manipulated with those applications.</span></span>

<span data-ttu-id="e11e0-170">**Deshalb gilt Folgendes** :</span><span class="sxs-lookup"><span data-stu-id="e11e0-170">**Therefore** :</span></span>

- <span data-ttu-id="e11e0-171">Wenn Sie überwiegend mit Windows-Anwendungen und Windows-PowerShell arbeiten, eignet sich UTF-8 mit BOM oder UTF-16 für Sie.</span><span class="sxs-lookup"><span data-stu-id="e11e0-171">If you work primarily with Windows applications and Windows PowerShell, you should prefer an encoding like UTF-8 with BOM or UTF-16.</span></span>
- <span data-ttu-id="e11e0-172">Wenn Sie plattformübergreifend arbeiten, eignet sich UTF-8 mit BOM für Sie.</span><span class="sxs-lookup"><span data-stu-id="e11e0-172">If you work across platforms, you should prefer UTF-8 with BOM.</span></span>
- <span data-ttu-id="e11e0-173">Wenn Sie überwiegend in Linux-Kontexten arbeiten, ist UTF-8 ohne BOM die richtige Wahl für Sie.</span><span class="sxs-lookup"><span data-stu-id="e11e0-173">If you work mainly in Linux-associated contexts, you should prefer UTF-8 without BOM.</span></span>
- <span data-ttu-id="e11e0-174">Windows-1252 und Latin-1 sind im Wesentlichen Legacycodierungen, die Sie wenn möglich vermeiden sollten.</span><span class="sxs-lookup"><span data-stu-id="e11e0-174">Windows-1252 and latin-1 are essentially legacy encodings that you should avoid if possible.</span></span>
  <span data-ttu-id="e11e0-175">Es kann jedoch sein, dass ältere Windows-Anwendungen noch von diesen abhängig sind.</span><span class="sxs-lookup"><span data-stu-id="e11e0-175">However, some older Windows applications may depend on them.</span></span>
- <span data-ttu-id="e11e0-176">Außerdem sollten Sie beachten, dass die Skriptsignierung [codierungsabhängig](https://github.com/PowerShell/PowerShell/issues/3466) ist, d.h., dass durch die Änderung der Codierung eines Skripts das Skript erneut signiert werden muss.</span><span class="sxs-lookup"><span data-stu-id="e11e0-176">It's also worth noting that script signing is [encoding-dependent](https://github.com/PowerShell/PowerShell/issues/3466), meaning a change of encoding on a signed script will require resigning.</span></span>

## <a name="configuring-vs-code"></a><span data-ttu-id="e11e0-177">Konfigurieren von VS Code</span><span class="sxs-lookup"><span data-stu-id="e11e0-177">Configuring VS Code</span></span>

<span data-ttu-id="e11e0-178">Die Standardcodierung von VS Code ist UTF-8 ohne BOM.</span><span class="sxs-lookup"><span data-stu-id="e11e0-178">VS Code's default encoding is UTF-8 without BOM.</span></span>

<span data-ttu-id="e11e0-179">Navigieren Sie zu den VS Code-Einstelllungen (<kbd>STRG</kbd>+<kbd>,</kbd>), und legen Sie die Einstellung `"files.encoding"` fest, um die [Codierung in VS Code][] festzulegen:</span><span class="sxs-lookup"><span data-stu-id="e11e0-179">To set [VS Code's encoding][], go to the VS Code settings (<kbd>Ctrl</kbd>+<kbd>,</kbd>) and set the `"files.encoding"` setting:</span></span>

```json
"files.encoding": "utf8bom"
```

<span data-ttu-id="e11e0-180">U.a. die folgenden Werte sind möglich:</span><span class="sxs-lookup"><span data-stu-id="e11e0-180">Some possible values are:</span></span>

- <span data-ttu-id="e11e0-181">`utf8`: [UTF-8] ohne BOM</span><span class="sxs-lookup"><span data-stu-id="e11e0-181">`utf8`: [UTF-8] without BOM</span></span>
- <span data-ttu-id="e11e0-182">`utf8bom`: [UTF-8] mit BOM</span><span class="sxs-lookup"><span data-stu-id="e11e0-182">`utf8bom`: [UTF-8] with BOM</span></span>
- <span data-ttu-id="e11e0-183">`utf16le`: Little-Endian [UTF-16]</span><span class="sxs-lookup"><span data-stu-id="e11e0-183">`utf16le`: Little endian [UTF-16]</span></span>
- <span data-ttu-id="e11e0-184">`utf16be`: Big-Endian [UTF-16]</span><span class="sxs-lookup"><span data-stu-id="e11e0-184">`utf16be`: Big endian [UTF-16]</span></span>
- <span data-ttu-id="e11e0-185">`windows1252`: [Windows-1252]</span><span class="sxs-lookup"><span data-stu-id="e11e0-185">`windows1252`: [Windows-1252]</span></span>

<span data-ttu-id="e11e0-186">Sie sollte dafür eine Dropdownliste in der GUI-Ansicht und Vorschläge in der JSON-Ansicht sehen.</span><span class="sxs-lookup"><span data-stu-id="e11e0-186">You should get a dropdown for this in the GUI view, or completions for it in the JSON view.</span></span>

<span data-ttu-id="e11e0-187">Sie können auch den folgenden Code hinzufügen, um die Codierung wenn möglich automatisch zu erkennen:</span><span class="sxs-lookup"><span data-stu-id="e11e0-187">You can also add the following to autodetect encoding when possible:</span></span>

```json
"files.autoGuessEncoding": true
```

<span data-ttu-id="e11e0-188">Wenn Sie nicht möchten, dass diese Einstellungen für alle Dateitypen gelten, können Sie in VS Code auch sprachspezifische Konfigurationen vornehmen.</span><span class="sxs-lookup"><span data-stu-id="e11e0-188">If you don't want these settings to affect all files types, VS Code also allows per-language configurations.</span></span> <span data-ttu-id="e11e0-189">Sie können sprachspezifische Einstellungen erstellen, indem Sie Einstellungen in ein `[<language-name>]` einfügen.</span><span class="sxs-lookup"><span data-stu-id="e11e0-189">Create a language-specific setting by putting settings in a `[<language-name>]` field.</span></span> <span data-ttu-id="e11e0-190">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="e11e0-190">For example:</span></span>

```json
"[powershell]": {
    "files.encoding": "utf8bom",
    "files.autoGuessEncoding": true
}
```

<span data-ttu-id="e11e0-191">Möglicherweise möchten Sie auch den [Gremlins Tracker][] für Visual Studio Code installieren.</span><span class="sxs-lookup"><span data-stu-id="e11e0-191">You may also want to consider installing the [Gremlins tracker][] for Visual Studio Code.</span></span> <span data-ttu-id="e11e0-192">Diese Erweiterung deckt bestimmte Unicode-Zeichen auf, die leicht beschädigt werden können, weil sie unsichtbar sind oder wie andere normale Zeichen aussehen.</span><span class="sxs-lookup"><span data-stu-id="e11e0-192">This extension reveals certain Unicode characters that easily corrupted because they are invisible or look like other normal characters.</span></span>

## <a name="configuring-powershell"></a><span data-ttu-id="e11e0-193">Konfiguration von PowerShell</span><span class="sxs-lookup"><span data-stu-id="e11e0-193">Configuring PowerShell</span></span>

<span data-ttu-id="e11e0-194">Die Standardcodierung von PowerShell variiert je nach Version:</span><span class="sxs-lookup"><span data-stu-id="e11e0-194">PowerShell's default encoding varies depending on version:</span></span>

- <span data-ttu-id="e11e0-195">In PowerShell 6 und höher, ist die Standardcodierung auf allen Plattformen UTF-8 ohne BOM.</span><span class="sxs-lookup"><span data-stu-id="e11e0-195">In PowerShell 6+, the default encoding is UTF-8 without BOM on all platforms.</span></span>
- <span data-ttu-id="e11e0-196">In Windows PowerShell ist die Standardcodierung normalerweise Windows-1252, eine Erweiterung von [Latin-1][], die auch als ISO 8859-1 bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="e11e0-196">In Windows PowerShell, the default encoding is usually Windows-1252, an extension of [latin-1][], also known as ISO 8859-1.</span></span>

<span data-ttu-id="e11e0-197">In PowerShell 5 und höher können Sie die Standardcodierung mit dem folgenden Code herausfinden:</span><span class="sxs-lookup"><span data-stu-id="e11e0-197">In PowerShell 5+ you can find your default encoding with this:</span></span>

```powershell
[psobject].Assembly.GetTypes() | Where-Object { $_.Name -eq 'ClrFacade'} |
  ForEach-Object {
    $_.GetMethod('GetDefaultEncoding', [System.Reflection.BindingFlags]'nonpublic,static').Invoke($null, @())
  }
```

<span data-ttu-id="e11e0-198">Mit dem folgenden [Skript](https://gist.github.com/rjmholt/3d8dd4849f718c914132ce3c5b278e0e) können Sie bestimmen, welche Codierung Ihre PowerShell-Sitzung für ein Skript ohne BOM annimmt.</span><span class="sxs-lookup"><span data-stu-id="e11e0-198">The following [script](https://gist.github.com/rjmholt/3d8dd4849f718c914132ce3c5b278e0e) can be used to determine what encoding your PowerShell session infers for a script without a BOM.</span></span>

```powershell
$badBytes = [byte[]]@(0xC3, 0x80)
$utf8Str = [System.Text.Encoding]::UTF8.GetString($badBytes)
$bytes = [System.Text.Encoding]::ASCII.GetBytes('Write-Output "') + [byte[]]@(0xC3, 0x80) + [byte[]]@(0x22)
$path = Join-Path ([System.IO.Path]::GetTempPath()) 'encodingtest.ps1'

try
{
    [System.IO.File]::WriteAllBytes($path, $bytes)

    switch (& $path)
    {
        $utf8Str
        {
            return 'UTF-8'
            break
        }

        default
        {
            return 'Windows-1252'
            break
        }
    }
}
finally
{
    Remove-Item $path
}
```

<span data-ttu-id="e11e0-199">Sie können in den Profileinstellungen PowerShell so konfigurieren, dass es eine bestimmte Codierung allgemeiner verwendet.</span><span class="sxs-lookup"><span data-stu-id="e11e0-199">It's possible to configure PowerShell to use a given encoding more generally using profile settings.</span></span>
<span data-ttu-id="e11e0-200">Weitere Informationen finden Sie in folgenden Artikeln:</span><span class="sxs-lookup"><span data-stu-id="e11e0-200">See the following articles:</span></span>

- <span data-ttu-id="e11e0-201">Antwort von [@mklement0] zum [Verwenden der PowerShell-Codierung auf Stack Overflow](https://stackoverflow.com/a/40098904).</span><span class="sxs-lookup"><span data-stu-id="e11e0-201">[@mklement0]'s [answer about PowerShell encoding on StackOverflow](https://stackoverflow.com/a/40098904).</span></span>
- <span data-ttu-id="e11e0-202">Blogbeitrag von [@rkeithhill] zum [Behandeln von UTF-8-Eingaben ohne BOM in PowerShell](https://rkeithhill.wordpress.com/2010/05/26/handling-native-exe-output-encoding-in-utf8-with-no-bom/).</span><span class="sxs-lookup"><span data-stu-id="e11e0-202">[@rkeithhill]'s [blog post about dealing with BOM-less UTF-8 input in PowerShell](https://rkeithhill.wordpress.com/2010/05/26/handling-native-exe-output-encoding-in-utf8-with-no-bom/).</span></span>

<span data-ttu-id="e11e0-203">Die Verwendung einer bestimmten Eingabecodierung kann in PowerShell nicht erzwungen werden.</span><span class="sxs-lookup"><span data-stu-id="e11e0-203">It's not possible to force PowerShell to use a specific input encoding.</span></span> <span data-ttu-id="e11e0-204">PowerShell 5.1 und niedrigere Versionen, die unter Windows mit dem Gebietsschema „en-US“ ausgeführt werden, verwenden standardmäßig die Windows-1252-Codierung, wenn keine BOM vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="e11e0-204">PowerShell 5.1 and below, running on Windows with the locale set to en-US, defaults to Windows-1252 encoding when there's no BOM.</span></span> <span data-ttu-id="e11e0-205">Bei anderen Gebietsschemaeinstellungen wird möglicherweise eine andere Codierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="e11e0-205">Other locale settings may use a different encoding.</span></span> <span data-ttu-id="e11e0-206">Zur Gewährleistung der Interoperabilität wird empfohlen, Skripts in einem Unicode-Format mit einer BOM zu speichern.</span><span class="sxs-lookup"><span data-stu-id="e11e0-206">To ensure interoperability, it's best to save scripts in a Unicode format with a BOM.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e11e0-207">Alle Tools, die mit PowerShell-Skripten interagieren, können von der gewählten Codierung betroffen sein oder Ihre Skripts in ein anderes Codierungsformat umcodieren.</span><span class="sxs-lookup"><span data-stu-id="e11e0-207">Any other tools you have that touch PowerShell scripts may be affected by your encoding choices or re-encode your scripts to another encoding.</span></span>

### <a name="existing-scripts"></a><span data-ttu-id="e11e0-208">Vorhandene Skripts</span><span class="sxs-lookup"><span data-stu-id="e11e0-208">Existing scripts</span></span>

<span data-ttu-id="e11e0-209">Skripts, die sich bereits im Dateisystem befinden, müssen möglicherweise in die neue Codierung umcodiert werden.</span><span class="sxs-lookup"><span data-stu-id="e11e0-209">Scripts already on the file system may need to be re-encoded to your new chosen encoding.</span></span> <span data-ttu-id="e11e0-210">In der unteren Leiste in VS Code wird UTF-8 angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e11e0-210">In the bottom bar of VS Code, you'll see the label UTF-8.</span></span> <span data-ttu-id="e11e0-211">Klicken Sie darauf, um die Aktionsleiste zu öffnen, und wählen Sie **Mit Codierung speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="e11e0-211">Click it to open the action bar and select **Save with encoding**.</span></span> <span data-ttu-id="e11e0-212">Jetzt können Sie für diese Datei eine neue Codierung festlegen.</span><span class="sxs-lookup"><span data-stu-id="e11e0-212">You can now pick a new encoding for that file.</span></span> <span data-ttu-id="e11e0-213">Im Artikel zur [Codierung in VS Code][] finden Sie alle Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="e11e0-213">See [VS Code's encoding][] for full instructions.</span></span>

<span data-ttu-id="e11e0-214">Wenn Sie mehrere Dateien erneut codieren müssen, können Sie das folgende Skript verwenden:</span><span class="sxs-lookup"><span data-stu-id="e11e0-214">If you need to re-encode multiple files, you can use the following script:</span></span>

```powershell
Get-ChildItem *.ps1 -Recurse | ForEach-Object {
    $content = Get-Content -Path $_
    Set-Content -Path $_.Fullname -Value $content -Encoding UTF8 -PassThru -Force
}
```

### <a name="the-powershell-integrated-scripting-environment-ise"></a><span data-ttu-id="e11e0-215">PowerShell Integrated Scripting Environment (ISE)</span><span class="sxs-lookup"><span data-stu-id="e11e0-215">The PowerShell Integrated Scripting Environment (ISE)</span></span>

<span data-ttu-id="e11e0-216">Wenn Sie auch Skripts mit der PowerShell ISE verwenden, müssen Sie dort Ihre Codierungseinstellungen synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="e11e0-216">If you also edit scripts using the PowerShell ISE, you need to synchronize your encoding settings there.</span></span>

<span data-ttu-id="e11e0-217">Die ISE sollte eine BOM beachten. Es ist jedoch auch möglich, die [Codierung mit der Reflexion festzulegen](https://bensonxion.wordpress.com/2012/04/25/powershell-ise-default-saveas-encoding/).</span><span class="sxs-lookup"><span data-stu-id="e11e0-217">The ISE should honor a BOM, but it's also possible to use reflection to [set the encoding](https://bensonxion.wordpress.com/2012/04/25/powershell-ise-default-saveas-encoding/).</span></span>
<span data-ttu-id="e11e0-218">Beachten Sie, dass diese Einstellung beim erneuten Öffnen nicht beibehalten wird.</span><span class="sxs-lookup"><span data-stu-id="e11e0-218">Note that this wouldn't be persisted between startups.</span></span>

### <a name="source-control-software"></a><span data-ttu-id="e11e0-219">Quellcodeverwaltungssoftware</span><span class="sxs-lookup"><span data-stu-id="e11e0-219">Source control software</span></span>

<span data-ttu-id="e11e0-220">Einige Quellcodeverwaltungstools wie z.B. Git ignorieren Codierungen. Git verfolgt nur die Bytes.</span><span class="sxs-lookup"><span data-stu-id="e11e0-220">Some source control tools, such as git, ignore encodings; git just tracks the bytes.</span></span> <span data-ttu-id="e11e0-221">Bei anderen Tools, z.B. Azure DevOps oder Mercurial, ist dies nicht der Fall.</span><span class="sxs-lookup"><span data-stu-id="e11e0-221">Others, like Azure DevOps or Mercurial, may not.</span></span> <span data-ttu-id="e11e0-222">Einige Git-basierte Tools sind vom Decodieren von Text abhängig.</span><span class="sxs-lookup"><span data-stu-id="e11e0-222">Even some git-based tools rely on decoding text.</span></span>

<span data-ttu-id="e11e0-223">Wenn dies so ist, achten Sie auf Folgendes:</span><span class="sxs-lookup"><span data-stu-id="e11e0-223">When this is the case, make sure you:</span></span>

- <span data-ttu-id="e11e0-224">Achten Sie darauf, dass die Textcodierung Ihrer Quellcodeverwaltung mit der Konfiguration in VS Code übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="e11e0-224">Configure the text encoding in your source control to match your VS Code configuration.</span></span>
- <span data-ttu-id="e11e0-225">Achten Sie darauf, dass Ihre Dateien in der Quellcodeverwaltung in der entsprechenden Codierung eingecheckt werden.</span><span class="sxs-lookup"><span data-stu-id="e11e0-225">Ensure all your files are checked into source control in the relevant encoding.</span></span>
- <span data-ttu-id="e11e0-226">Achten Sie auf Änderungen der Codierung, die Sie von der Quellcodeverwaltung erhalten.</span><span class="sxs-lookup"><span data-stu-id="e11e0-226">Be wary of changes to the encoding received through source control.</span></span> <span data-ttu-id="e11e0-227">Darauf deutet primär ein Unterschied hin, der Änderungen angibt, obwohl keine offensichtlichen Änderungen zu erkennen sind (weil sich nur Bytes aber keine Zeichen geändert haben).</span><span class="sxs-lookup"><span data-stu-id="e11e0-227">A key sign of this is a diff indicating changes but where nothing seems to have changed (because bytes have but characters have not).</span></span>

### <a name="collaborators-environments"></a><span data-ttu-id="e11e0-228">Einstellungen Mitwirkender</span><span class="sxs-lookup"><span data-stu-id="e11e0-228">Collaborators' environments</span></span>

<span data-ttu-id="e11e0-229">Achten Sie neben der Quellcodeverwaltung auch darauf, dass Personen, die an freigegebenen Dateien mitwirken, keine Einstellungen haben, die Ihre Codierung durch das erneute Codieren von PowerShell-Dateien überschreiben.</span><span class="sxs-lookup"><span data-stu-id="e11e0-229">On top of configuring source control, ensure that your collaborators on any files you share don't have settings that override your encoding by re-encoding PowerShell files.</span></span>

### <a name="other-programs"></a><span data-ttu-id="e11e0-230">Andere Programme</span><span class="sxs-lookup"><span data-stu-id="e11e0-230">Other programs</span></span>

<span data-ttu-id="e11e0-231">Alle anderen Programme, die ein PowerShell-Skript lesen oder schreiben, codieren dieses möglicherweise neu.</span><span class="sxs-lookup"><span data-stu-id="e11e0-231">Any other program that reads or writes a PowerShell script may re-encode it.</span></span>

<span data-ttu-id="e11e0-232">Beispiele:</span><span class="sxs-lookup"><span data-stu-id="e11e0-232">Some examples are:</span></span>

- <span data-ttu-id="e11e0-233">Die Zwischenablage zum Kopieren und Einfügen eines Skripts.</span><span class="sxs-lookup"><span data-stu-id="e11e0-233">Using the clipboard to copy and paste a script.</span></span> <span data-ttu-id="e11e0-234">Dies geschieht z.B. in den folgenden Szenarios:</span><span class="sxs-lookup"><span data-stu-id="e11e0-234">This is common in scenarios like:</span></span>
  - <span data-ttu-id="e11e0-235">Kopieren eines Skripts in eine VM</span><span class="sxs-lookup"><span data-stu-id="e11e0-235">Copying a script into a VM</span></span>
  - <span data-ttu-id="e11e0-236">Kopieren eines Skripts aus einer E-Mail oder von einer Webseite</span><span class="sxs-lookup"><span data-stu-id="e11e0-236">Copying a script out of an email or webpage</span></span>
  - <span data-ttu-id="e11e0-237">Kopieren eines Skripts in ein oder aus einem Microsoft Word- oder PowerPoint-Dokument</span><span class="sxs-lookup"><span data-stu-id="e11e0-237">Copying a script into or out of a Microsoft Word or PowerPoint document</span></span>
- <span data-ttu-id="e11e0-238">Andere Text-Editors, z.B.:</span><span class="sxs-lookup"><span data-stu-id="e11e0-238">Other text editors, such as:</span></span>
  - <span data-ttu-id="e11e0-239">Notepad</span><span class="sxs-lookup"><span data-stu-id="e11e0-239">Notepad</span></span>
  - <span data-ttu-id="e11e0-240">vim</span><span class="sxs-lookup"><span data-stu-id="e11e0-240">vim</span></span>
  - <span data-ttu-id="e11e0-241">Andere PowerShell-Skript-Editors</span><span class="sxs-lookup"><span data-stu-id="e11e0-241">Any other PowerShell script editor</span></span>
- <span data-ttu-id="e11e0-242">Textbearbeitungshilfsprogramme, z.B.:</span><span class="sxs-lookup"><span data-stu-id="e11e0-242">Text editing utilities, like:</span></span>
  - `Get-Content`/`Set-Content`/`Out-File`
  - <span data-ttu-id="e11e0-243">PowerShell-Umleitungsoperatoren wie `>` und `>>`</span><span class="sxs-lookup"><span data-stu-id="e11e0-243">PowerShell redirection operators like `>` and `>>`</span></span>
  - `sed`/`awk`
- <span data-ttu-id="e11e0-244">Dateiübertragungsprogramme, z.B.:</span><span class="sxs-lookup"><span data-stu-id="e11e0-244">File transfer programs, like:</span></span>
  - <span data-ttu-id="e11e0-245">Ein Webbrowser beim Herunterladen von Skripts</span><span class="sxs-lookup"><span data-stu-id="e11e0-245">A web browser, when downloading scripts</span></span>
  - <span data-ttu-id="e11e0-246">Eine Dateifreigabe</span><span class="sxs-lookup"><span data-stu-id="e11e0-246">A file share</span></span>

<span data-ttu-id="e11e0-247">Einige dieser Tools arbeiten mit Bytes und nicht mit Text und andere bieten Codierungskonfigurationen.</span><span class="sxs-lookup"><span data-stu-id="e11e0-247">Some of these tools deal in bytes rather than text, but others offer encoding configurations.</span></span> <span data-ttu-id="e11e0-248">Wenn Sie eine Codierung konfigurieren müssen, muss diese mit der Codierung Ihres Editors übereinstimmen, um Probleme zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="e11e0-248">In those cases where you need to configure an encoding, you need to make it the same as your editor encoding to prevent problems.</span></span>

## <a name="other-resources-on-encoding-in-powershell"></a><span data-ttu-id="e11e0-249">Weitere Informationen zur Codierung in PowerShell</span><span class="sxs-lookup"><span data-stu-id="e11e0-249">Other resources on encoding in PowerShell</span></span>

<span data-ttu-id="e11e0-250">Es gibt einige weitere nützliche Beiträge zur Codierung und Konfiguration der Codierung in PowerShell, die Sie sich ansehen können:</span><span class="sxs-lookup"><span data-stu-id="e11e0-250">There are a few other nice posts on encoding and configuring encoding in PowerShell that are worth a read:</span></span>

- [<span data-ttu-id="e11e0-251">about_Character_Encoding</span><span class="sxs-lookup"><span data-stu-id="e11e0-251">about_Character_Encoding</span></span>](/powershell/module/microsoft.powershell.core/about/about_character_encoding)
- <span data-ttu-id="e11e0-252">die Zusammenfassung von [@mklement0] zum [Verwenden der PowerShell-Codierung auf Stack Overflow](https://stackoverflow.com/questions/40098771/changing-powershells-default-output-encoding-to-utf-8)</span><span class="sxs-lookup"><span data-stu-id="e11e0-252">[@mklement0]'s [summary of PowerShell encoding on StackOverflow](https://stackoverflow.com/questions/40098771/changing-powershells-default-output-encoding-to-utf-8)</span></span>
- <span data-ttu-id="e11e0-253">Frühere Probleme bezüglich der Codierung bei VS Code und PowerShell:</span><span class="sxs-lookup"><span data-stu-id="e11e0-253">Previous issues opened on VS Code-PowerShell for encoding problems:</span></span>
  - [<span data-ttu-id="e11e0-254">#1308</span><span class="sxs-lookup"><span data-stu-id="e11e0-254">#1308</span></span>](https://github.com/PowerShell/VSCode-powershell/issues/1308)
  - [<span data-ttu-id="e11e0-255">#1628</span><span class="sxs-lookup"><span data-stu-id="e11e0-255">#1628</span></span>](https://github.com/PowerShell/VSCode-powershell/issues/1628)
  - [<span data-ttu-id="e11e0-256">#1680</span><span class="sxs-lookup"><span data-stu-id="e11e0-256">#1680</span></span>](https://github.com/PowerShell/VSCode-powershell/issues/1680)
  - [<span data-ttu-id="e11e0-257">#1744</span><span class="sxs-lookup"><span data-stu-id="e11e0-257">#1744</span></span>](https://github.com/PowerShell/VSCode-powershell/issues/1744)
  - [<span data-ttu-id="e11e0-258">#1751</span><span class="sxs-lookup"><span data-stu-id="e11e0-258">#1751</span></span>](https://github.com/PowerShell/VSCode-powershell/issues/1751)
- [<span data-ttu-id="e11e0-259">Der Klassiker: Zusammenfassung von _Joel on Software_ zu Unicode</span><span class="sxs-lookup"><span data-stu-id="e11e0-259">The classic _Joel on Software_ write up about Unicode</span></span>](https://www.joelonsoftware.com/2003/10/08/the-absolute-minimum-every-software-developer-absolutely-positively-must-know-about-unicode-and-character-sets-no-excuses/)
- [<span data-ttu-id="e11e0-260">Codierung in .NET Standard</span><span class="sxs-lookup"><span data-stu-id="e11e0-260">Encoding in .NET Standard</span></span>](https://github.com/dotnet/standard/issues/260#issuecomment-289549508)

[@mklement0]: https://github.com/mklement0
[@rkeithhill]: https://github.com/rkeithhill
[Windows-1252]: https://wikipedia.org/wiki/Windows-1252
[latin-1]: https://wikipedia.org/wiki/ISO/IEC_8859-1
[UTF-8]: https://wikipedia.org/wiki/UTF-8
[Bytereihenfolge-Marke]: https://wikipedia.org/wiki/Byte_order_mark
[byte-order mark]: https://wikipedia.org/wiki/Byte_order_mark
[UTF-16]: https://wikipedia.org/wiki/UTF-16
[Sprachserverprotokoll]: https://microsoft.github.io/language-server-protocol/
[Language Server Protocol]: https://microsoft.github.io/language-server-protocol/
[Codierung in VS Code]: https://code.visualstudio.com/docs/editor/codebasics#_file-encoding-support
[VS Code's encoding]: https://code.visualstudio.com/docs/editor/codebasics#_file-encoding-support
[Gremlins Tracker]: https://marketplace.visualstudio.com/items?itemName=nhoizey.gremlins
[Gremlins tracker]: https://marketplace.visualstudio.com/items?itemName=nhoizey.gremlins
