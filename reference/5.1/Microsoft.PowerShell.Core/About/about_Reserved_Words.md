---
description: Listet die reservierten Wörter auf, die nicht als Bezeichner verwendet werden können, da Sie in PowerShell eine besondere Bedeutung haben.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 07/23/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_reserved_words?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Reserved_Words
ms.openlocfilehash: 99b56e433ccb39ba0f199068086bcdaddf36590e
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93222572"
---
# <a name="about-reserved-words"></a><span data-ttu-id="e6a69-104">Informationen zu reservierten Wörtern</span><span class="sxs-lookup"><span data-stu-id="e6a69-104">About Reserved Words</span></span>

## <a name="short-description"></a><span data-ttu-id="e6a69-105">KURZE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e6a69-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="e6a69-106">Listet die reservierten Wörter auf, die nicht als Bezeichner verwendet werden können, da Sie in PowerShell eine besondere Bedeutung haben.</span><span class="sxs-lookup"><span data-stu-id="e6a69-106">Lists the reserved words that cannot be used as identifiers because they have a special meaning in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="e6a69-107">LANGE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e6a69-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="e6a69-108">Es gibt bestimmte Wörter, die in PowerShell eine besondere Bedeutung haben.</span><span class="sxs-lookup"><span data-stu-id="e6a69-108">There are certain words that have special meaning in PowerShell.</span></span> <span data-ttu-id="e6a69-109">Wenn diese Wörter ohne Anführungszeichen angezeigt werden, versucht PowerShell, ihre besondere Bedeutung anzuwenden, anstatt Sie als Zeichen folgen zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="e6a69-109">When these words appear without quotation marks, PowerShell attempts to apply their special meaning rather than treating them as character strings.</span></span> <span data-ttu-id="e6a69-110">Um diese Wörter in einem Befehl oder Skript als Parameter Argumente zu verwenden, ohne Ihre besondere Bedeutung aufzurufen, müssen Sie die reservierten Wörter in Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="e6a69-110">To use these words as parameter arguments in a command or script without invoking their special meaning, enclose the reserved words in quotation marks.</span></span>

<span data-ttu-id="e6a69-111">Im folgenden finden Sie die reservierten Wörter in PowerShell:</span><span class="sxs-lookup"><span data-stu-id="e6a69-111">The following are the reserved words in PowerShell:</span></span>

```
assembly         exit            process
base             filter          public
begin            finally         return
break            for             sequence
catch            foreach         static
class            from (*)        switch
command          function        throw
configuration    hidden          trap
continue         if              try
data             in              type
define (*)       inlinescript    until
do               interface       using
dynamicparam     module          var (*)
else             namespace       while
elseif           parallel        workflow
end              param
enum             private

(*) These keywords are reserved for future use.
```

<span data-ttu-id="e6a69-112">Mehrere sprach Schlüsselwörter, einschließlich `Foreach` , `If` , `For` und `While` , verfügen über eigene Hilfeartikel.</span><span class="sxs-lookup"><span data-stu-id="e6a69-112">Several language keywords, including `Foreach`, `If`, `For`, and `While`, have their own help articles.</span></span> <span data-ttu-id="e6a69-113">Um diese anzuzeigen, geben Sie ein, `Get-Help about_` und fügen Sie es hinzu.</span><span class="sxs-lookup"><span data-stu-id="e6a69-113">To view them, type `Get-Help about_` and add the keyword.</span></span> <span data-ttu-id="e6a69-114">Um z. b. Informationen zur-Anweisung zu erhalten, geben Sie Folgendes ein `Foreach` :</span><span class="sxs-lookup"><span data-stu-id="e6a69-114">For example, to get information about the `Foreach` statement, type:</span></span>

```powershell
Get-Help about_ForEach
```

<span data-ttu-id="e6a69-115">Informationen zur- `Filter` Anweisung oder der- `Return` Anweisungs Syntax erhalten Sie, wenn Sie Folgendes eingeben:</span><span class="sxs-lookup"><span data-stu-id="e6a69-115">For information about the `Filter` statement or the `Return` statement syntax, type:</span></span>

```powershell
Get-Help about_Functions
```

<span data-ttu-id="e6a69-116">Weitere Informationen zu anderen reservierten Wörtern erhalten Sie, wenn Sie Folgendes eingeben:</span><span class="sxs-lookup"><span data-stu-id="e6a69-116">For information about other reserved words, type:</span></span>

```powershell
Get-Help <Reserved_Word>
```

> [!NOTE]
> <span data-ttu-id="e6a69-117">Nicht jedes reservierte Wort hat einen eigenen Hilfeartikel.</span><span class="sxs-lookup"><span data-stu-id="e6a69-117">Not every reserved word has its own help article.</span></span> <span data-ttu-id="e6a69-118">Wenn keinen `Get-Help` Artikel zurückgibt, können Sie mithilfe des folgenden Befehls nach Artikeln suchen, die über das reservierte Wort sprechen:</span><span class="sxs-lookup"><span data-stu-id="e6a69-118">If `Get-Help` does not return an article, you can search for articles that talk about the reserved word using the following command:</span></span>
>
> ```powershell
> Get-Help <Reserved_Word> -Category:HelpFile
> ```

## <a name="see-also"></a><span data-ttu-id="e6a69-119">SIEHE AUCH</span><span class="sxs-lookup"><span data-stu-id="e6a69-119">SEE ALSO</span></span>

- [<span data-ttu-id="e6a69-120">about_Command_Syntax</span><span class="sxs-lookup"><span data-stu-id="e6a69-120">about_Command_Syntax</span></span>](about_Command_Syntax.md)
- [<span data-ttu-id="e6a69-121">about_Language_Keywords</span><span class="sxs-lookup"><span data-stu-id="e6a69-121">about_Language_Keywords</span></span>](about_Language_Keywords.md)
- [<span data-ttu-id="e6a69-122">about_Parsing</span><span class="sxs-lookup"><span data-stu-id="e6a69-122">about_Parsing</span></span>](about_Parsing.md)
- [<span data-ttu-id="e6a69-123">about_Quoting_Rules</span><span class="sxs-lookup"><span data-stu-id="e6a69-123">about_Quoting_Rules</span></span>](about_Quoting_Rules.md)
- [<span data-ttu-id="e6a69-124">about_Script_Blocks</span><span class="sxs-lookup"><span data-stu-id="e6a69-124">about_Script_Blocks</span></span>](about_Script_Blocks.md)
- [<span data-ttu-id="e6a69-125">about_Special_Characters</span><span class="sxs-lookup"><span data-stu-id="e6a69-125">about_Special_Characters</span></span>](about_Special_Characters.md)
