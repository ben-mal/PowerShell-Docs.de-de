---
title: Unterstützung für Platzhalter in Cmdlet-Parametern
ms.date: 08/26/2019
ms.openlocfilehash: 062e3d50dddd0bc84e57f5254a93289acbabe38b
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786406"
---
# <a name="supporting-wildcard-characters-in-cmdlet-parameters"></a><span data-ttu-id="4d02b-102">Unterstützung für Platzhalter in Cmdlet-Parametern</span><span class="sxs-lookup"><span data-stu-id="4d02b-102">Supporting Wildcard Characters in Cmdlet Parameters</span></span>

<span data-ttu-id="4d02b-103">Häufig müssen Sie ein Cmdlet so entwerfen, dass es für eine Gruppe von Ressourcen und nicht für eine einzelne Ressource ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="4d02b-103">Often, you will have to design a cmdlet to run against a group of resources rather than against a single resource.</span></span> <span data-ttu-id="4d02b-104">Beispielsweise muss ein Cmdlet möglicherweise alle Dateien in einem Datenspeicher mit dem gleichen Namen oder der gleichen Erweiterung suchen.</span><span class="sxs-lookup"><span data-stu-id="4d02b-104">For example, a cmdlet might need to locate all the files in a data store that have the same name or extension.</span></span> <span data-ttu-id="4d02b-105">Beim Entwerfen eines Cmdlets, das für eine Gruppe von Ressourcen ausgeführt werden soll, müssen Sie Unterstützung für Platzhalter Zeichen bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="4d02b-105">You must provide support for wildcard characters when you design a cmdlet that will be run against a group of resources.</span></span>

> [!NOTE]
> <span data-ttu-id="4d02b-106">Die Verwendung von Platzhalter Zeichen wird manchmal als " *glob"* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="4d02b-106">Using wildcard characters is sometimes referred to as *globbing*.</span></span>

## <a name="windows-powershell-cmdlets-that-use-wildcards"></a><span data-ttu-id="4d02b-107">Windows PowerShell-Cmdlets, die Platzhalter verwenden</span><span class="sxs-lookup"><span data-stu-id="4d02b-107">Windows PowerShell Cmdlets That Use Wildcards</span></span>

 <span data-ttu-id="4d02b-108">Viele Windows PowerShell-Cmdlets unterstützen Platzhalter Zeichen für Ihre Parameterwerte.</span><span class="sxs-lookup"><span data-stu-id="4d02b-108">Many Windows PowerShell cmdlets support wildcard characters for their parameter values.</span></span> <span data-ttu-id="4d02b-109">Beispielsweise unterstützt fast jedes Cmdlet mit dem-Parameter oder dem-Parameter Platzhalter `Name` `Path` Zeichen für diese Parameter.</span><span class="sxs-lookup"><span data-stu-id="4d02b-109">For example, almost every cmdlet that has a `Name` or `Path` parameter supports wildcard characters for these parameters.</span></span> <span data-ttu-id="4d02b-110">(Obwohl die meisten Cmdlets, die über einen Parameter verfügen, `Path` auch über einen `LiteralPath` Parameter verfügen, der keine Platzhalter Zeichen unterstützt.) Der folgende Befehl zeigt, wie ein Platzhalter Zeichen verwendet wird, um alle Cmdlets in der aktuellen Sitzung zurückzugeben, deren Name das Get-Verb enthält.</span><span class="sxs-lookup"><span data-stu-id="4d02b-110">(Although most cmdlets that have a `Path` parameter also have a `LiteralPath` parameter that does not support wildcard characters.) The following command shows how a wildcard character is used to return all the cmdlets in the current session whose name contains the Get verb.</span></span>

 `Get-Command get-*`

## <a name="supported-wildcard-characters"></a><span data-ttu-id="4d02b-111">Unterstützte Platzhalter Zeichen</span><span class="sxs-lookup"><span data-stu-id="4d02b-111">Supported Wildcard Characters</span></span>

<span data-ttu-id="4d02b-112">Windows PowerShell unterstützt die folgenden Platzhalter Zeichen.</span><span class="sxs-lookup"><span data-stu-id="4d02b-112">Windows PowerShell supports the following wildcard characters.</span></span>

| <span data-ttu-id="4d02b-113">Platzhalter</span><span class="sxs-lookup"><span data-stu-id="4d02b-113">Wildcard</span></span> |                             <span data-ttu-id="4d02b-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4d02b-114">Description</span></span>                             |  <span data-ttu-id="4d02b-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4d02b-115">Example</span></span>   |     <span data-ttu-id="4d02b-116">Treffer</span><span class="sxs-lookup"><span data-stu-id="4d02b-116">Matches</span></span>      | <span data-ttu-id="4d02b-117">Stimmt nicht überein mit</span><span class="sxs-lookup"><span data-stu-id="4d02b-117">Does not match</span></span> |
| -------- | ------------------------------------------------------------------- | ---------- | ---------------- | -------------- |
| *        | <span data-ttu-id="4d02b-118">Entspricht 0 (null) oder mehr Zeichen, beginnend an der angegebenen Position.</span><span class="sxs-lookup"><span data-stu-id="4d02b-118">Matches zero or more characters, starting at the specified position</span></span> | `a*`       | <span data-ttu-id="4d02b-119">A, AG, Apple</span><span class="sxs-lookup"><span data-stu-id="4d02b-119">A, ag, Apple</span></span>     |                |
| <span data-ttu-id="4d02b-120">?</span><span class="sxs-lookup"><span data-stu-id="4d02b-120">?</span></span>        | <span data-ttu-id="4d02b-121">Entspricht einem beliebigen Zeichen an der angegebenen Position.</span><span class="sxs-lookup"><span data-stu-id="4d02b-121">Matches any character at the specified position</span></span>                     | `?n`       | <span data-ttu-id="4d02b-122">Ein, in, ein</span><span class="sxs-lookup"><span data-stu-id="4d02b-122">An, in, on</span></span>       | <span data-ttu-id="4d02b-123">an</span><span class="sxs-lookup"><span data-stu-id="4d02b-123">ran</span></span>            |
| <span data-ttu-id="4d02b-124">[ ]</span><span class="sxs-lookup"><span data-stu-id="4d02b-124">[ ]</span></span>      | <span data-ttu-id="4d02b-125">Entspricht einem Zeichenbereich.</span><span class="sxs-lookup"><span data-stu-id="4d02b-125">Matches a range of characters</span></span>                                       | `[a-l]ook` | <span data-ttu-id="4d02b-126">Buch, Kochen, ansehen</span><span class="sxs-lookup"><span data-stu-id="4d02b-126">book, cook, look</span></span> | <span data-ttu-id="4d02b-127">Nook, hat</span><span class="sxs-lookup"><span data-stu-id="4d02b-127">nook, took</span></span>     |
| <span data-ttu-id="4d02b-128">[ ]</span><span class="sxs-lookup"><span data-stu-id="4d02b-128">[ ]</span></span>      | <span data-ttu-id="4d02b-129">Entspricht den angegebenen Zeichen</span><span class="sxs-lookup"><span data-stu-id="4d02b-129">Matches the specified characters</span></span>                                    | `[bn]ook`  | <span data-ttu-id="4d02b-130">Buch, Nook</span><span class="sxs-lookup"><span data-stu-id="4d02b-130">book, nook</span></span>       | <span data-ttu-id="4d02b-131">Kochen, sehen</span><span class="sxs-lookup"><span data-stu-id="4d02b-131">cook, look</span></span>     |

<span data-ttu-id="4d02b-132">Wenn Sie Cmdlets entwerfen, die Platzhalter Zeichen unterstützen, lassen Sie Kombinationen von Platzhalter Zeichen zu.</span><span class="sxs-lookup"><span data-stu-id="4d02b-132">When you design cmdlets that support wildcard characters, allow for combinations of wildcard characters.</span></span> <span data-ttu-id="4d02b-133">Der folgende Befehl verwendet z. b. das `Get-ChildItem` Cmdlet zum Abrufen aller txt-Dateien, die sich im Ordner c:\techdocs befinden und mit den Buchstaben "a" bis "l" beginnen.</span><span class="sxs-lookup"><span data-stu-id="4d02b-133">For example, the following command uses the `Get-ChildItem` cmdlet to retrieve all the .txt files that are in the c:\Techdocs folder and that begin with the letters "a" through "l."</span></span>

`Get-ChildItem c:\techdocs\[a-l]\*.txt`

<span data-ttu-id="4d02b-134">Der vorherige Befehl verwendet den Bereichs `[a-l]` Platzhalter, um anzugeben, dass der Dateiname mit den Zeichen "a" bis "l" beginnen soll, und verwendet das `*` Platzhalter Zeichen als Platzhalter für alle Zeichen zwischen dem ersten Buchstaben des Datei namens und der Erweiterung " **. txt** ".</span><span class="sxs-lookup"><span data-stu-id="4d02b-134">The previous command uses the range wildcard `[a-l]` to specify that the file name should begin with the characters "a" through "l" and uses the `*` wildcard character as a placeholder for any characters between the first letter of the filename and the **.txt** extension.</span></span>

<span data-ttu-id="4d02b-135">Im folgenden Beispiel wird ein Bereichs Halter Muster verwendet, das den Buchstaben "d" ausschließt, aber alle anderen Buchstaben von "a" bis "f" umfasst.</span><span class="sxs-lookup"><span data-stu-id="4d02b-135">The following example uses a range wildcard pattern that excludes the letter "d" but includes all the other letters from "a" through "f."</span></span>

`Get-ChildItem c:\techdocs\[a-cef]\*.txt`

## <a name="handling-literal-characters-in-wildcard-patterns"></a><span data-ttu-id="4d02b-136">Verarbeiten von Literalzeichen in Platzhalter Mustern</span><span class="sxs-lookup"><span data-stu-id="4d02b-136">Handling Literal Characters in Wildcard Patterns</span></span>

<span data-ttu-id="4d02b-137">Wenn das von Ihnen angegebene Platzhalter Muster Literalzeichen enthält, die nicht als Platzhalter Zeichen interpretiert werden sollen, verwenden Sie das Graviszeichen-Zeichen ( `` ` `` ) als Escapezeichen.</span><span class="sxs-lookup"><span data-stu-id="4d02b-137">If the wildcard pattern you specify contains literal characters that should not be interpretted as wildcard characters, use the backtick character (`` ` ``) as an escape character.</span></span> <span data-ttu-id="4d02b-138">Wenn Sie die Literalzeichen int der PowerShell-API angeben, verwenden Sie einen einzigen Backtick.</span><span class="sxs-lookup"><span data-stu-id="4d02b-138">When you specify literal characters int the PowerShell API, use a single backtick.</span></span> <span data-ttu-id="4d02b-139">Wenn Sie an der PowerShell-Eingabeaufforderung Literalzeichen angeben, verwenden Sie zwei Backticks.</span><span class="sxs-lookup"><span data-stu-id="4d02b-139">When you specify literal characters at the PowerShell command prompt, use two backticks.</span></span>

<span data-ttu-id="4d02b-140">Das folgende Muster enthält z. b. zwei eckige Klammern, die wörtlich genommen werden müssen.</span><span class="sxs-lookup"><span data-stu-id="4d02b-140">For example, the following pattern contains two brackets that must be taken literally.</span></span>

<span data-ttu-id="4d02b-141">Wenn Sie in der PowerShell-API verwendet wird, verwenden Sie:</span><span class="sxs-lookup"><span data-stu-id="4d02b-141">When used in the PowerShell API use:</span></span>

- <span data-ttu-id="4d02b-142">"John Smith \` [\* ']"</span><span class="sxs-lookup"><span data-stu-id="4d02b-142">"John Smith \`[\*\`]"</span></span>

<span data-ttu-id="4d02b-143">Wenn Sie von der PowerShell-Eingabeaufforderung verwendet wird:</span><span class="sxs-lookup"><span data-stu-id="4d02b-143">When used from the PowerShell command prompt:</span></span>

- <span data-ttu-id="4d02b-144">"John Smith \` \` [\* \` ']"</span><span class="sxs-lookup"><span data-stu-id="4d02b-144">"John Smith \`\`[\*\`\`]"</span></span>

<span data-ttu-id="4d02b-145">Dieses Muster entspricht "John Smith [Marketing]" oder "John Smith [Development]".</span><span class="sxs-lookup"><span data-stu-id="4d02b-145">This pattern matches "John Smith [Marketing]" or "John Smith [Development]".</span></span> <span data-ttu-id="4d02b-146">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="4d02b-146">For example:</span></span>

```
PS> "John Smith [Marketing]" -like "John Smith ``[*``]"
True

PS> "John Smith [Development]" -like "John Smith ``[*``]"
True
```

## <a name="cmdlet-output-and-wildcard-characters"></a><span data-ttu-id="4d02b-147">Cmdlet-Ausgabe und Platzhalter Zeichen</span><span class="sxs-lookup"><span data-stu-id="4d02b-147">Cmdlet Output and Wildcard Characters</span></span>

<span data-ttu-id="4d02b-148">Wenn Cmdlet-Parameter Platzhalter Zeichen unterstützen, generiert der Vorgang normalerweise eine Array Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="4d02b-148">When cmdlet parameters support wildcard characters, the operation usually generates an array output.</span></span>
<span data-ttu-id="4d02b-149">Gelegentlich ist es nicht sinnvoll, eine Array Ausgabe zu unterstützen, da der Benutzer möglicherweise nur ein einzelnes Element verwendet.</span><span class="sxs-lookup"><span data-stu-id="4d02b-149">Occasionally, it makes no sense to support an array output because the user might use only a single item.</span></span> <span data-ttu-id="4d02b-150">Beispielsweise `Set-Location` unterstützt das Cmdlet die Array Ausgabe nicht, da der Benutzer nur einen einzigen Speicherort festlegt.</span><span class="sxs-lookup"><span data-stu-id="4d02b-150">For example, the `Set-Location` cmdlet does not support array output because the user sets only a single location.</span></span> <span data-ttu-id="4d02b-151">In diesem Fall unterstützt das Cmdlet weiterhin Platzhalter Zeichen, aber es erzwingt die Auflösung an einem einzelnen Speicherort.</span><span class="sxs-lookup"><span data-stu-id="4d02b-151">In this instance, the cmdlet still supports wildcard characters, but it forces resolution to a single location.</span></span>

## <a name="see-also"></a><span data-ttu-id="4d02b-152">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4d02b-152">See Also</span></span>

[<span data-ttu-id="4d02b-153">Schreiben eines Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="4d02b-153">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

[<span data-ttu-id="4d02b-154">Wildcardpattern-Klasse</span><span class="sxs-lookup"><span data-stu-id="4d02b-154">WildcardPattern Class</span></span>](/dotnet/api/system.management.automation.wildcardpattern)
