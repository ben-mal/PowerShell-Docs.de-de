---
title: about_Character_Encoding
description: Beschreibt, wie PowerShell die Zeichencodierung für die Eingabe und Ausgabe von Zeichen folgen Daten verwendet.
ms.date: 10/21/2020
Locale: en-US
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_character_encoding?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
ms.openlocfilehash: 0dff2a2cd3915a84c80627abdd0388e9722df806
ms.sourcegitcommit: df80c558e9a4b89c9798f084bd04012ece15155c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/23/2020
ms.locfileid: "93225156"
---
# <a name="about_character_encoding"></a><span data-ttu-id="b3111-103">about_Character_Encoding</span><span class="sxs-lookup"><span data-stu-id="b3111-103">about_Character_Encoding</span></span>

## <a name="short-description"></a><span data-ttu-id="b3111-104">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b3111-104">Short description</span></span>
<span data-ttu-id="b3111-105">Beschreibt, wie PowerShell die Zeichencodierung für die Eingabe und Ausgabe von Zeichen folgen Daten verwendet.</span><span class="sxs-lookup"><span data-stu-id="b3111-105">Describes how PowerShell uses character encoding for input and output of string data.</span></span>

## <a name="long-description"></a><span data-ttu-id="b3111-106">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b3111-106">Long description</span></span>

<span data-ttu-id="b3111-107">Unicode ist ein weltweiter Zeichen Codierungsstandard.</span><span class="sxs-lookup"><span data-stu-id="b3111-107">Unicode is a worldwide character-encoding standard.</span></span> <span data-ttu-id="b3111-108">Das System verwendet Unicode exklusiv für Zeichen-und Zeichen folgen Bearbeitung.</span><span class="sxs-lookup"><span data-stu-id="b3111-108">The system uses Unicode exclusively for character and string manipulation.</span></span> <span data-ttu-id="b3111-109">Eine ausführliche Beschreibung aller Aspekte von Unicode finden Sie unter Unicode- [Standard](https://www.unicode.org/standard/standard.html).</span><span class="sxs-lookup"><span data-stu-id="b3111-109">For a detailed description of all aspects of Unicode, refer to [The Unicode Standard](https://www.unicode.org/standard/standard.html).</span></span>

<span data-ttu-id="b3111-110">Windows unterstützt Unicode-und herkömmliche Zeichensätze.</span><span class="sxs-lookup"><span data-stu-id="b3111-110">Windows supports Unicode and traditional character sets.</span></span> <span data-ttu-id="b3111-111">Herkömmliche Zeichensätze, wie z. b. Windows-Codepages, verwenden 8-Bit-Werte oder Kombinationen von 8-Bit-Werten, um die in einer bestimmten Sprache oder in geografischen Regions Einstellungen verwendeten Zeichen darzustellen.</span><span class="sxs-lookup"><span data-stu-id="b3111-111">Traditional character sets, such as Windows code pages, use 8-bit values or combinations of 8-bit values to represent the characters used in a specific language or geographical region settings.</span></span>

<span data-ttu-id="b3111-112">PowerShell verwendet standardmäßig einen Unicode-Zeichensatz.</span><span class="sxs-lookup"><span data-stu-id="b3111-112">PowerShell uses a Unicode character set by default.</span></span> <span data-ttu-id="b3111-113">Mehrere Cmdlets verfügen jedoch über einen **Codierungs** Parameter, mit dem die Codierung für einen anderen Zeichensatz angegeben werden kann.</span><span class="sxs-lookup"><span data-stu-id="b3111-113">However, several cmdlets have an **Encoding** parameter that can specify encoding for a different character set.</span></span> <span data-ttu-id="b3111-114">Mit diesem Parameter können Sie die jeweilige Zeichencodierung auswählen, die für die Interoperabilität mit anderen Systemen und Anwendungen erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="b3111-114">This parameter allows you to choose the specific the character encoding you need for interoperability with other systems and applications.</span></span>

<span data-ttu-id="b3111-115">Die folgenden Cmdlets haben den **Codierungs** Parameter:</span><span class="sxs-lookup"><span data-stu-id="b3111-115">The following cmdlets have the **Encoding** parameter:</span></span>

- <span data-ttu-id="b3111-116">Microsoft.PowerShell.Management</span><span class="sxs-lookup"><span data-stu-id="b3111-116">Microsoft.PowerShell.Management</span></span>
  - <span data-ttu-id="b3111-117">Add-Content</span><span class="sxs-lookup"><span data-stu-id="b3111-117">Add-Content</span></span>
  - <span data-ttu-id="b3111-118">Get-Content</span><span class="sxs-lookup"><span data-stu-id="b3111-118">Get-Content</span></span>
  - <span data-ttu-id="b3111-119">Set-Content</span><span class="sxs-lookup"><span data-stu-id="b3111-119">Set-Content</span></span>
- <span data-ttu-id="b3111-120">Microsoft.PowerShell.Utility</span><span class="sxs-lookup"><span data-stu-id="b3111-120">Microsoft.PowerShell.Utility</span></span>
  - <span data-ttu-id="b3111-121">Export-Clixml</span><span class="sxs-lookup"><span data-stu-id="b3111-121">Export-Clixml</span></span>
  - <span data-ttu-id="b3111-122">Export-Csv</span><span class="sxs-lookup"><span data-stu-id="b3111-122">Export-Csv</span></span>
  - <span data-ttu-id="b3111-123">Export-PSSession</span><span class="sxs-lookup"><span data-stu-id="b3111-123">Export-PSSession</span></span>
  - <span data-ttu-id="b3111-124">Format-Hex</span><span class="sxs-lookup"><span data-stu-id="b3111-124">Format-Hex</span></span>
  - <span data-ttu-id="b3111-125">Import-Csv</span><span class="sxs-lookup"><span data-stu-id="b3111-125">Import-Csv</span></span>
  - <span data-ttu-id="b3111-126">Out-File</span><span class="sxs-lookup"><span data-stu-id="b3111-126">Out-File</span></span>
  - <span data-ttu-id="b3111-127">Select-String</span><span class="sxs-lookup"><span data-stu-id="b3111-127">Select-String</span></span>
  - <span data-ttu-id="b3111-128">Send-MailMessage</span><span class="sxs-lookup"><span data-stu-id="b3111-128">Send-MailMessage</span></span>

## <a name="the-byte-order-mark"></a><span data-ttu-id="b3111-129">Byte-Reihenfolge Markierung</span><span class="sxs-lookup"><span data-stu-id="b3111-129">The byte-order-mark</span></span>

<span data-ttu-id="b3111-130">Byte-Order-Mark (BOM) ist eine _Unicode-Signatur_ in den ersten Bytes einer Datei oder eines Textstreams, die angeben, welche Unicode-Codierung für die Daten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b3111-130">The byte-order-mark (BOM) is a _Unicode signature_ in the first few bytes of a file or text stream that indicate which Unicode encoding used for the data.</span></span> <span data-ttu-id="b3111-131">Weitere Informationen finden Sie im Artikel zur [Byte Reihenfolge-Markierung](https://wikipedia.org/wiki/Byte_order_mark) in Wikipedia.</span><span class="sxs-lookup"><span data-stu-id="b3111-131">For more information, see the [Byte order mark](https://wikipedia.org/wiki/Byte_order_mark) article in Wikipedia.</span></span>

<span data-ttu-id="b3111-132">In Windows PowerShell erstellt jede Unicode-Codierung, außer `UTF7` , immer eine BOM.</span><span class="sxs-lookup"><span data-stu-id="b3111-132">In Windows PowerShell, any Unicode encoding, except `UTF7`, always creates a BOM.</span></span> <span data-ttu-id="b3111-133">PowerShell Core wird standardmäßig `utf8NoBOM` für die gesamte Textausgabe verwendet.</span><span class="sxs-lookup"><span data-stu-id="b3111-133">PowerShell Core defaults to `utf8NoBOM` for all text output.</span></span>

<span data-ttu-id="b3111-134">Vermeiden Sie die Verwendung von BOMs in UTF-8-Dateien, um eine optimale Gesamt Kompatibilität zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="b3111-134">For best overall compatibility, avoid using BOMs in UTF-8 files.</span></span> <span data-ttu-id="b3111-135">Auf Windows-Plattformen verwendete UNIX-und UNIX-Dienstprogramme unterstützen BOMs nicht.</span><span class="sxs-lookup"><span data-stu-id="b3111-135">Unix platforms and Unix-heritage utilities also used on Windows Platforms don't support BOMs.</span></span>

<span data-ttu-id="b3111-136">Ebenso `UTF7` sollte die Codierung vermieden werden.</span><span class="sxs-lookup"><span data-stu-id="b3111-136">Similarly, `UTF7` encoding should be avoided.</span></span> <span data-ttu-id="b3111-137">UTF-7 ist keine standardmäßige Unicode-Codierung und wird in allen Versionen von PowerShell ohne eine BOM geschrieben.</span><span class="sxs-lookup"><span data-stu-id="b3111-137">UTF-7 is not a standard Unicode encoding and is written without a BOM in all versions of PowerShell.</span></span>

<span data-ttu-id="b3111-138">Das Erstellen von PowerShell-Skripts auf einer Unix-ähnlichen Plattform oder die Verwendung eines plattformübergreifenden Editors unter Windows, z. b. Visual Studio Code, führt zu einer Datei, die mit codiert ist `UTF8NoBOM`</span><span class="sxs-lookup"><span data-stu-id="b3111-138">Creating PowerShell scripts on a Unix-like platform or using a cross-platform editor on Windows, such as Visual Studio Code, results in a file encoded using `UTF8NoBOM`.</span></span> <span data-ttu-id="b3111-139">Diese Dateien funktionieren in PowerShell Core einwandfrei, können aber in Windows PowerShell unterbrechen, wenn die Datei nicht-ASCII-Zeichen enthält.</span><span class="sxs-lookup"><span data-stu-id="b3111-139">These files work fine on PowerShell Core, but may break in Windows PowerShell if the file contains non-Ascii characters.</span></span>

<span data-ttu-id="b3111-140">Wenn Sie nicht-ASCII-Zeichen in Ihren Skripts verwenden müssen, speichern Sie Sie als UTF-8 mit BOM.</span><span class="sxs-lookup"><span data-stu-id="b3111-140">If you need to use non-Ascii characters in your scripts, save them as UTF-8 with BOM.</span></span> <span data-ttu-id="b3111-141">Ohne die BOM interpretiert Windows PowerShell das Skript so, als dass es auf der Legacy-Codepage "ANSI" codiert wird.</span><span class="sxs-lookup"><span data-stu-id="b3111-141">Without the BOM, Windows PowerShell misinterprets your script as being encoded in the legacy "ANSI" codepage.</span></span> <span data-ttu-id="b3111-142">Im Gegensatz dazu können Dateien, die die UTF-8-BOM aufweisen, auf Unix-ähnlichen Plattformen problematisch sein.</span><span class="sxs-lookup"><span data-stu-id="b3111-142">Conversely, files that do have the UTF-8 BOM can be problematic on Unix-like platforms.</span></span> <span data-ttu-id="b3111-143">Viele Unix-Tools wie `cat` , `sed` , `awk` und einige Editoren, wie z `gedit` . b., wissen nicht, wie die BOM behandelt werden kann.</span><span class="sxs-lookup"><span data-stu-id="b3111-143">Many Unix tools such as `cat`, `sed`, `awk`, and some editors such as `gedit` don't know how to treat the BOM.</span></span>

## <a name="character-encoding-in-windows-powershell"></a><span data-ttu-id="b3111-144">Zeichencodierung in Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b3111-144">Character encoding in Windows PowerShell</span></span>

<span data-ttu-id="b3111-145">In PowerShell 5,1 unterstützt der **Encoding** -Parameter die folgenden Werte:</span><span class="sxs-lookup"><span data-stu-id="b3111-145">In PowerShell 5.1, the **Encoding** parameter supports the following values:</span></span>

- <span data-ttu-id="b3111-146">`Ascii` Verwendet den ASCII-Zeichensatz (7-Bit).</span><span class="sxs-lookup"><span data-stu-id="b3111-146">`Ascii` Uses Ascii (7-bit) character set.</span></span>
- <span data-ttu-id="b3111-147">`BigEndianUnicode` Verwendet UTF-16 mit der Big-Endian-Byte Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="b3111-147">`BigEndianUnicode` Uses UTF-16 with the big-endian byte order.</span></span>
- <span data-ttu-id="b3111-148">`BigEndianUTF32` Verwendet UTF-32 mit der Big-Endian-Byte Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="b3111-148">`BigEndianUTF32` Uses UTF-32 with the big-endian byte order.</span></span>
- <span data-ttu-id="b3111-149">`Byte` Codiert eine Reihe von Zeichen in eine Bytefolge.</span><span class="sxs-lookup"><span data-stu-id="b3111-149">`Byte` Encodes a set of characters into a sequence of bytes.</span></span>
- <span data-ttu-id="b3111-150">`Default` Verwendet die Codierung, die der aktiven Codepage des Systems entspricht (normalerweise ANSI).</span><span class="sxs-lookup"><span data-stu-id="b3111-150">`Default` Uses the encoding that corresponds to the system's active code page (usually ANSI).</span></span>
- <span data-ttu-id="b3111-151">`Oem` Verwendet die Codierung, die der aktuellen OEM-Codepage des Systems entspricht.</span><span class="sxs-lookup"><span data-stu-id="b3111-151">`Oem` Uses the encoding that corresponds to the system's current OEM code page.</span></span>
- <span data-ttu-id="b3111-152">`String` Identisch mit `Unicode`.</span><span class="sxs-lookup"><span data-stu-id="b3111-152">`String` Same as `Unicode`.</span></span>
- <span data-ttu-id="b3111-153">`Unicode` Verwendet UTF-16 mit der Little-Endian-Byte Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="b3111-153">`Unicode` Uses UTF-16 with the little-endian byte order.</span></span>
- <span data-ttu-id="b3111-154">`Unknown` Identisch mit `Unicode`.</span><span class="sxs-lookup"><span data-stu-id="b3111-154">`Unknown` Same as `Unicode`.</span></span>
- <span data-ttu-id="b3111-155">`UTF32` Verwendet UTF-32 mit der Little-Endian-Byte Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="b3111-155">`UTF32` Uses UTF-32 with the little-endian byte order.</span></span>
- <span data-ttu-id="b3111-156">`UTF7` Verwendet UTF-7.</span><span class="sxs-lookup"><span data-stu-id="b3111-156">`UTF7` Uses UTF-7.</span></span>
- <span data-ttu-id="b3111-157">`UTF8` Verwendet UTF-8 (mit BOM).</span><span class="sxs-lookup"><span data-stu-id="b3111-157">`UTF8` Uses UTF-8 (with BOM).</span></span>

<span data-ttu-id="b3111-158">Im Allgemeinen verwendet Windows PowerShell standardmäßig die [UTF-16LE-Unicode-](https://wikipedia.org/wiki/UTF-16) Codierung.</span><span class="sxs-lookup"><span data-stu-id="b3111-158">In general, Windows PowerShell uses the Unicode [UTF-16LE](https://wikipedia.org/wiki/UTF-16) encoding by default.</span></span> <span data-ttu-id="b3111-159">Die Standard Codierung, die von Cmdlets in Windows PowerShell verwendet wird, ist jedoch nicht konsistent.</span><span class="sxs-lookup"><span data-stu-id="b3111-159">However, the default encoding used by cmdlets in Windows PowerShell is not consistent.</span></span>

> [!NOTE]
> <span data-ttu-id="b3111-160">Bei Verwendung einer beliebigen Unicode-Codierung, mit Ausnahme von `UTF7` , wird immer eine BOM erstellt.</span><span class="sxs-lookup"><span data-stu-id="b3111-160">Using any Unicode encoding, except `UTF7`, always creates a BOM.</span></span>

<span data-ttu-id="b3111-161">Für Cmdlets, die die Ausgabe in Dateien schreiben:</span><span class="sxs-lookup"><span data-stu-id="b3111-161">For cmdlets that write output to files:</span></span>

- <span data-ttu-id="b3111-162">`Out-File` und die Umleitungs Operatoren `>` und `>>` Erstellen UTF-16LE, die sich insbesondere von und unterscheiden `Set-Content` `Add-Content` .</span><span class="sxs-lookup"><span data-stu-id="b3111-162">`Out-File` and the redirection operators `>` and `>>` create UTF-16LE, which notably differs from `Set-Content` and `Add-Content`.</span></span>

- <span data-ttu-id="b3111-163">`New-ModuleManifest``Export-CliXml`außerdem werden UTF-16LE-Dateien erstellt.</span><span class="sxs-lookup"><span data-stu-id="b3111-163">`New-ModuleManifest` and `Export-CliXml` also create UTF-16LE files.</span></span>

- <span data-ttu-id="b3111-164">Wenn die Zieldatei leer ist oder nicht vorhanden ist, verwenden Sie die `Set-Content` - `Add-Content` `Default` Codierung.</span><span class="sxs-lookup"><span data-stu-id="b3111-164">When the target file is empty or doesn't exist, `Set-Content` and `Add-Content` use `Default` encoding.</span></span> <span data-ttu-id="b3111-165">`Default` die durch die ANSI-Legacy Codepage des aktiven System Gebiets Schemas angegebene Codierung.</span><span class="sxs-lookup"><span data-stu-id="b3111-165">`Default` is the encoding specified by the active system locale's ANSI legacy code page.</span></span>

- <span data-ttu-id="b3111-166">`Export-Csv` erstellt `Ascii` Dateien, verwendet jedoch unterschiedliche Codierungen, wenn der **Append** -Parameter verwendet wird (siehe unten).</span><span class="sxs-lookup"><span data-stu-id="b3111-166">`Export-Csv` creates `Ascii` files but uses different encoding when using **Append** parameter (see below).</span></span>

- <span data-ttu-id="b3111-167">`Export-PSSession` erstellt standardmäßig UTF-8-Dateien mit BOM.</span><span class="sxs-lookup"><span data-stu-id="b3111-167">`Export-PSSession` creates UTF-8 files with BOM by default.</span></span>

- <span data-ttu-id="b3111-168">`New-Item -Type File -Value` erstellt eine BOM-lose UTF-8-Datei.</span><span class="sxs-lookup"><span data-stu-id="b3111-168">`New-Item -Type File -Value` creates a BOM-less UTF-8 file.</span></span>

- <span data-ttu-id="b3111-169">`Send-MailMessage` verwendet `Default` standardmäßig die Codierung.</span><span class="sxs-lookup"><span data-stu-id="b3111-169">`Send-MailMessage` uses `Default` encoding by default.</span></span>

- <span data-ttu-id="b3111-170">`Start-Transcript` erstellt `Utf8` Dateien mit einer BOM.</span><span class="sxs-lookup"><span data-stu-id="b3111-170">`Start-Transcript` creates `Utf8` files with a BOM.</span></span> <span data-ttu-id="b3111-171">Wenn der **Append** -Parameter verwendet wird, kann die Codierung abweichen (siehe unten).</span><span class="sxs-lookup"><span data-stu-id="b3111-171">When the **Append** parameter is used, the encoding can be different (see below).</span></span>

<span data-ttu-id="b3111-172">Für Befehle, die an eine vorhandene Datei anfügen:</span><span class="sxs-lookup"><span data-stu-id="b3111-172">For commands that append to an existing file:</span></span>

- <span data-ttu-id="b3111-173">`Out-File -Append` und der `>>` Umleitungs Operator versuchen nicht, die Codierung des Inhalts der vorhandenen Zieldatei abzugleichen.</span><span class="sxs-lookup"><span data-stu-id="b3111-173">`Out-File -Append` and the `>>` redirection operator make no attempt to match the encoding of the existing target file's content.</span></span> <span data-ttu-id="b3111-174">Stattdessen verwenden Sie die Standard Codierung, es sei denn, der **Encoding** -Parameter wird verwendet.</span><span class="sxs-lookup"><span data-stu-id="b3111-174">Instead, they use the default encoding unless the **Encoding** parameter is used.</span></span> <span data-ttu-id="b3111-175">Sie müssen die ursprünglichen Codierungs Dateien verwenden, wenn Sie Inhalt anfügen.</span><span class="sxs-lookup"><span data-stu-id="b3111-175">You must use the files original encoding when appending content.</span></span>

- <span data-ttu-id="b3111-176">Wenn kein expliziter **Codierungs** Parameter vorhanden ist, wird `Add-Content` die vorhandene Codierung von erkannt und automatisch auf den neuen Inhalt angewendet.</span><span class="sxs-lookup"><span data-stu-id="b3111-176">In the absence of an explicit **Encoding** parameter, `Add-Content` detects the existing encoding and automatically applies it to the new content.</span></span> <span data-ttu-id="b3111-177">Wenn für den vorhandenen Inhalt keine BOM vorhanden ist, `Default` wird die ANSI-Codierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="b3111-177">If the existing content has no BOM, `Default` ANSI encoding is used.</span></span> <span data-ttu-id="b3111-178">Das Verhalten von `Add-Content` ist in PowerShell Core (V6 und höher) identisch, mit dem Unterschied, dass die Standard Codierung ist `Utf8` .</span><span class="sxs-lookup"><span data-stu-id="b3111-178">The behavior of `Add-Content` is the same in PowerShell Core (v6 and higher) except the default encoding is `Utf8`.</span></span>

- <span data-ttu-id="b3111-179">`Export-Csv -Append` entspricht der vorhandenen Codierung, wenn die Zieldatei eine BOM enthält.</span><span class="sxs-lookup"><span data-stu-id="b3111-179">`Export-Csv -Append` matches the existing encoding when the target file contains a BOM.</span></span> <span data-ttu-id="b3111-180">Wenn keine BOM vorhanden ist, wird die `Utf8` Codierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="b3111-180">In the absence of a BOM, it uses `Utf8` encoding.</span></span>

- <span data-ttu-id="b3111-181">`Start-Transcript -Append` entspricht der vorhandenen Codierung von Dateien, die eine BOM enthalten.</span><span class="sxs-lookup"><span data-stu-id="b3111-181">`Start-Transcript -Append` matches the existing encoding of files that include a BOM.</span></span> <span data-ttu-id="b3111-182">Wenn keine BOM vorhanden ist, wird standardmäßig die `Ascii` Codierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="b3111-182">In the absence of a BOM, it defaults to `Ascii` encoding.</span></span> <span data-ttu-id="b3111-183">Diese Codierung kann zu Datenverlusten oder Zeichen Beschädigungen führen, wenn die Daten in der Aufzeichnung Multibytezeichen enthalten.</span><span class="sxs-lookup"><span data-stu-id="b3111-183">This encoding can result in data loss or character corruption when the data in the transcript contains multibyte characters.</span></span>

<span data-ttu-id="b3111-184">Für Cmdlets, die Zeichen folgen Daten lesen, wenn keine BOM vorhanden ist:</span><span class="sxs-lookup"><span data-stu-id="b3111-184">For cmdlets that read string data in the absence of a BOM:</span></span>

- <span data-ttu-id="b3111-185">`Get-Content` und `Import-PowerShellDataFile` verwenden die `Default` ANSI-Codierung.</span><span class="sxs-lookup"><span data-stu-id="b3111-185">`Get-Content` and `Import-PowerShellDataFile` uses the `Default` ANSI encoding.</span></span> <span data-ttu-id="b3111-186">ANSI ist auch das, was die PowerShell-Engine verwendet, wenn Sie Quellcode aus Dateien liest.</span><span class="sxs-lookup"><span data-stu-id="b3111-186">ANSI is also what the PowerShell engine uses when it reads source code from files.</span></span>

- <span data-ttu-id="b3111-187">`Import-Csv`, `Import-CliXml` und `Select-String` gehen davon aus, dass `Utf8` keine BOM vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="b3111-187">`Import-Csv`, `Import-CliXml`, and `Select-String` assume `Utf8` in the absence of a BOM.</span></span>

## <a name="character-encoding-in-powershell-core"></a><span data-ttu-id="b3111-188">Zeichencodierung in PowerShell Core</span><span class="sxs-lookup"><span data-stu-id="b3111-188">Character encoding in PowerShell Core</span></span>

<span data-ttu-id="b3111-189">In PowerShell Core (V6 und höher) unterstützt der **Encoding** -Parameter die folgenden Werte:</span><span class="sxs-lookup"><span data-stu-id="b3111-189">In PowerShell Core (v6 and higher), the **Encoding** parameter supports the following values:</span></span>

- <span data-ttu-id="b3111-190">`ascii`: Verwendet die Codierung für den ASCII-Zeichensatz (7-Bit).</span><span class="sxs-lookup"><span data-stu-id="b3111-190">`ascii`: Uses the encoding for the ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="b3111-191">`bigendianunicode`: Codiert im UTF-16-Format unter Verwendung der Big-Endian-Byte Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="b3111-191">`bigendianunicode`: Encodes in UTF-16 format using the big-endian byte order.</span></span>
- <span data-ttu-id="b3111-192">`oem`: Verwendet die Standard Codierung für MS-DOS-und-Konsolen Programme.</span><span class="sxs-lookup"><span data-stu-id="b3111-192">`oem`: Uses the default encoding for MS-DOS and console programs.</span></span>
- <span data-ttu-id="b3111-193">`unicode`: Codiert im UTF-16-Format unter Verwendung der Little-Endian-Byte Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="b3111-193">`unicode`: Encodes in UTF-16 format using the little-endian byte order.</span></span>
- <span data-ttu-id="b3111-194">`utf7`: Codiert im UTF-7-Format.</span><span class="sxs-lookup"><span data-stu-id="b3111-194">`utf7`: Encodes in UTF-7 format.</span></span>
- <span data-ttu-id="b3111-195">`utf8`: Codiert im UTF-8-Format (keine BOM).</span><span class="sxs-lookup"><span data-stu-id="b3111-195">`utf8`: Encodes in UTF-8 format (no BOM).</span></span>
- <span data-ttu-id="b3111-196">`utf8BOM`: Codiert im UTF-8-Format mit Byte Reihenfolge Markierung (BOM).</span><span class="sxs-lookup"><span data-stu-id="b3111-196">`utf8BOM`: Encodes in UTF-8 format with Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="b3111-197">`utf8NoBOM`: Codiert im UTF-8-Format ohne Byte Reihenfolge-Markierung (BOM).</span><span class="sxs-lookup"><span data-stu-id="b3111-197">`utf8NoBOM`: Encodes in UTF-8 format without Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="b3111-198">`utf32`: Codiert im UTF-32-Format.</span><span class="sxs-lookup"><span data-stu-id="b3111-198">`utf32`: Encodes in UTF-32 format.</span></span>

<span data-ttu-id="b3111-199">PowerShell Core wird standardmäßig `utf8NoBOM` für alle Ausgaben verwendet.</span><span class="sxs-lookup"><span data-stu-id="b3111-199">PowerShell Core defaults to `utf8NoBOM` for all output.</span></span>

<span data-ttu-id="b3111-200">Ab PowerShell 6,2 ermöglicht der **Encoding** -Parameter auch numerische IDs registrierter Codepages (z `-Encoding 1251` . b.) oder Zeichen folgen Namen registrierter Codepages (z `-Encoding "windows-1251"` . b.).</span><span class="sxs-lookup"><span data-stu-id="b3111-200">Beginning with PowerShell 6.2, the **Encoding** parameter also allows numeric IDs of registered code pages (like `-Encoding 1251`) or string names of registered code pages (like `-Encoding "windows-1251"`).</span></span> <span data-ttu-id="b3111-201">Weitere Informationen finden Sie in der .NET-Dokumentation für [Encoding. Codepage](/dotnet/api/system.text.encoding.codepage).</span><span class="sxs-lookup"><span data-stu-id="b3111-201">For more information, see the .NET documentation for [Encoding.CodePage](/dotnet/api/system.text.encoding.codepage).</span></span>

## <a name="changing-the-default-encoding"></a><span data-ttu-id="b3111-202">Ändern der Standard Codierung</span><span class="sxs-lookup"><span data-stu-id="b3111-202">Changing the default encoding</span></span>

<span data-ttu-id="b3111-203">PowerShell verfügt über zwei Standardvariablen, mit denen das Standard Codierungs Verhalten geändert werden kann.</span><span class="sxs-lookup"><span data-stu-id="b3111-203">PowerShell has two default variables that can be used to change the default encoding behavior.</span></span>

- `$PSDefaultParameterValues`
- `$OutputEncoding`

<span data-ttu-id="b3111-204">Weitere Informationen finden Sie unter [about_Preference_Variables](about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="b3111-204">For more information, see [about_Preference_Variables](about_Preference_Variables.md).</span></span>

<span data-ttu-id="b3111-205">Ab PowerShell 5,1 wird das-Cmdlet von den Umleitungs Operatoren ( `>` und `>>` ) aufgerufen `Out-File` .</span><span class="sxs-lookup"><span data-stu-id="b3111-205">Beginning in PowerShell 5.1, the redirection operators (`>` and `>>`) call the `Out-File` cmdlet.</span></span> <span data-ttu-id="b3111-206">Daher können Sie die Standard Codierung für diese mithilfe der Preference- `$PSDefaultParameterValues` Variablen festlegen, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="b3111-206">Therefore, you can set the default encoding of them using the `$PSDefaultParameterValues` preference variable as shown in this example:</span></span>

```powershell
$PSDefaultParameterValues['Out-File:Encoding'] = 'utf8'
```

<span data-ttu-id="b3111-207">Verwenden Sie die folgende Anweisung, um die Standard Codierung für alle Cmdlets zu ändern, die über den **Encoding** -Parameter verfügen.</span><span class="sxs-lookup"><span data-stu-id="b3111-207">Use the following statement to change the default encoding for all cmdlets that have the **Encoding** parameter.</span></span>

```powershell
$PSDefaultParameterValues['*:Encoding'] = 'utf8'
```

> [!IMPORTANT]
> <span data-ttu-id="b3111-208">Wenn Sie diesen Befehl in das PowerShell-Profil einfügen, ist dies eine Einstellung für eine Sitzungs globale Einstellung, die sich auf alle Befehle und Skripts auswirkt, die nicht explizit eine Codierung angeben.</span><span class="sxs-lookup"><span data-stu-id="b3111-208">Putting this command in your PowerShell profile makes the preference a session-global setting that affects all commands and scripts that do not explicitly specify an encoding.</span></span>
>
> <span data-ttu-id="b3111-209">Ebenso sollten Sie solche Befehle in Ihre Skripts oder Module einschließen, die Sie auf dieselbe Weise Verhalten möchten.</span><span class="sxs-lookup"><span data-stu-id="b3111-209">Similarly, you should include such commands in your scripts or modules that you want to behave the same way.</span></span> <span data-ttu-id="b3111-210">Wenn Sie diese Befehle verwenden, stellen Sie sicher, dass sich Cmdlets auch dann Verhalten, wenn Sie von einem anderen Benutzer, einem anderen Computer oder einer anderen Version von PowerShell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="b3111-210">Using these commands ensure that cmdlets behave the same way even when run by another user, on a different computer, or in a different version of PowerShell.</span></span>

<span data-ttu-id="b3111-211">Die automatische Variable `$OutputEncoding` wirkt sich auf die Codierung aus, die von PowerShell zur Kommunikation mit externen Programmen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b3111-211">The automatic variable `$OutputEncoding` affects the encoding PowerShell uses to communicate with external programs.</span></span> <span data-ttu-id="b3111-212">Dies hat keine Auswirkung auf die Codierung, die von den Ausgabe Umleitungs Operatoren und PowerShell-Cmdlets zum Speichern in Dateien verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b3111-212">It has no effect on the encoding that the output redirection operators and PowerShell cmdlets use to save to files.</span></span>

## <a name="see-also"></a><span data-ttu-id="b3111-213">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b3111-213">See also</span></span>

- [<span data-ttu-id="b3111-214">Einführung in die Zeichencodierung in .NET</span><span class="sxs-lookup"><span data-stu-id="b3111-214">Introduction to character encoding in .NET</span></span>](/dotnet/standard/base-types/character-encoding-introduction)
- [<span data-ttu-id="b3111-215">Codepages-Win32-apps</span><span class="sxs-lookup"><span data-stu-id="b3111-215">Code Pages - Win32 apps</span></span>](/windows/win32/intl/code-pages)
- [<span data-ttu-id="b3111-216">Der Unicode-Standard</span><span class="sxs-lookup"><span data-stu-id="b3111-216">The Unicode Standard</span></span>](https://www.unicode.org/standard/standard.html)
- [<span data-ttu-id="b3111-217">Encoding. Codepage</span><span class="sxs-lookup"><span data-stu-id="b3111-217">Encoding.CodePage</span></span>](/dotnet/api/system.text.encoding.codepage)
- [<span data-ttu-id="b3111-218">UTF-16LE</span><span class="sxs-lookup"><span data-stu-id="b3111-218">UTF-16LE</span></span>](https://wikipedia.org/wiki/UTF-16)
- [<span data-ttu-id="b3111-219">Byte Reihenfolge Markierung</span><span class="sxs-lookup"><span data-stu-id="b3111-219">Byte order mark</span></span>](https://wikipedia.org/wiki/Byte_order_mark)
- [<span data-ttu-id="b3111-220">about_Preference_Variables</span><span class="sxs-lookup"><span data-stu-id="b3111-220">about_Preference_Variables</span></span>](about_Preference_Variables.md)
