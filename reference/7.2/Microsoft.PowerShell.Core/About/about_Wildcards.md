---
description: Beschreibt die Verwendung von Platzhalter Zeichen in PowerShell.
Locale: en-US
ms.date: 02/13/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_wildcards?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Wildcards
ms.openlocfilehash: 40620e54bb889d683192b346f3ba1c139895e4d0
ms.sourcegitcommit: 9777152e026c47ba8d319593051416054cb62246
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/16/2021
ms.locfileid: "100529973"
---
# <a name="about-wildcards"></a><span data-ttu-id="6f259-103">Informationen zu Platzhaltern</span><span class="sxs-lookup"><span data-stu-id="6f259-103">About Wildcards</span></span>

## <a name="short-description"></a><span data-ttu-id="6f259-104">KURZE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="6f259-104">SHORT DESCRIPTION</span></span>

<span data-ttu-id="6f259-105">Beschreibt die Verwendung von Platzhalter Zeichen in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6f259-105">Describes how to use wildcard characters in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="6f259-106">LANGE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="6f259-106">LONG DESCRIPTION</span></span>

<span data-ttu-id="6f259-107">Platzhalter Zeichen stellen ein oder mehrere Zeichen dar.</span><span class="sxs-lookup"><span data-stu-id="6f259-107">Wildcard characters represent one or many characters.</span></span> <span data-ttu-id="6f259-108">Sie können Sie zum Erstellen von Wort Mustern in Befehlen verwenden.</span><span class="sxs-lookup"><span data-stu-id="6f259-108">You can use them to create word patterns in commands.</span></span> <span data-ttu-id="6f259-109">Platzhalter Ausdrücke werden mit dem- `-like` Operator oder mit einem beliebigen Parameter verwendet, der Platzhalter akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="6f259-109">Wildcard expressions are used with the `-like` operator or with any parameter that accepts wildcards.</span></span>

<span data-ttu-id="6f259-110">Geben Sie z. b. Folgendes ein, um alle Dateien im `C:\Techdocs` Verzeichnis mit einer `.ppt` Dateinamenerweiterung abzugleichen:</span><span class="sxs-lookup"><span data-stu-id="6f259-110">For example, to match all the files in the `C:\Techdocs` directory with a `.ppt` file name extension, type:</span></span>

```powershell
Get-ChildItem C:\Techdocs\*.ppt
```

<span data-ttu-id="6f259-111">In diesem Fall stellt das Platzhalter `*` Zeichen Sternchen () alle Zeichen dar, die vor der `.ppt` Dateinamenerweiterung angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="6f259-111">In this case, the asterisk (`*`) wildcard character represents any characters that appear before the `.ppt` file name extension.</span></span>

<span data-ttu-id="6f259-112">Platzhalter Ausdrücke sind einfacher als reguläre Ausdrücke.</span><span class="sxs-lookup"><span data-stu-id="6f259-112">Wildcard expressions are simpler than regular expressions.</span></span> <span data-ttu-id="6f259-113">Weitere Informationen finden Sie unter [about_Regular_Expressions](./about_Regular_Expressions.md).</span><span class="sxs-lookup"><span data-stu-id="6f259-113">For more information, see [about_Regular_Expressions](./about_Regular_Expressions.md).</span></span>

<span data-ttu-id="6f259-114">PowerShell unterstützt die folgenden Platzhalter Zeichen:</span><span class="sxs-lookup"><span data-stu-id="6f259-114">PowerShell supports the following wildcard characters:</span></span>

|<span data-ttu-id="6f259-115">Platzhalter</span><span class="sxs-lookup"><span data-stu-id="6f259-115">Wildcard</span></span>|<span data-ttu-id="6f259-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6f259-116">Description</span></span>               |<span data-ttu-id="6f259-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6f259-117">Example</span></span> |<span data-ttu-id="6f259-118">Match</span><span class="sxs-lookup"><span data-stu-id="6f259-118">Match</span></span>        |<span data-ttu-id="6f259-119">Keine Entsprechung</span><span class="sxs-lookup"><span data-stu-id="6f259-119">No Match</span></span>|
|--------|--------------------------|--------|-------------|--------|
|\*      |<span data-ttu-id="6f259-120">Entsprechung für NULL oder mehr Zeichen</span><span class="sxs-lookup"><span data-stu-id="6f259-120">Match zero or more characters</span></span> | <span data-ttu-id="6f259-121">ein\*</span><span class="sxs-lookup"><span data-stu-id="6f259-121">a\*</span></span>  | <span data-ttu-id="6f259-122">AA, AG, Apple</span><span class="sxs-lookup"><span data-stu-id="6f259-122">aA, ag, Apple</span></span> | <span data-ttu-id="6f259-123">Bananen</span><span class="sxs-lookup"><span data-stu-id="6f259-123">banana</span></span> |
|<span data-ttu-id="6f259-124">?</span><span class="sxs-lookup"><span data-stu-id="6f259-124">?</span></span>       |<span data-ttu-id="6f259-125">Mit einem Zeichen an dieser Position vergleichen</span><span class="sxs-lookup"><span data-stu-id="6f259-125">Match one character in that position</span></span> | <span data-ttu-id="6f259-126">? n</span><span class="sxs-lookup"><span data-stu-id="6f259-126">?n</span></span> | <span data-ttu-id="6f259-127">ein, in, ein</span><span class="sxs-lookup"><span data-stu-id="6f259-127">an, in, on</span></span> | <span data-ttu-id="6f259-128">an</span><span class="sxs-lookup"><span data-stu-id="6f259-128">ran</span></span> |
|<span data-ttu-id="6f259-129">\[ \]</span><span class="sxs-lookup"><span data-stu-id="6f259-129">\[ \]</span></span>   |<span data-ttu-id="6f259-130">Mit einem Zeichenbereich vergleichen</span><span class="sxs-lookup"><span data-stu-id="6f259-130">Match a range of characters</span></span> | <span data-ttu-id="6f259-131">\[a-l \] ook</span><span class="sxs-lookup"><span data-stu-id="6f259-131">\[a-l\]ook</span></span> | <span data-ttu-id="6f259-132">Buch, Kochen, ansehen</span><span class="sxs-lookup"><span data-stu-id="6f259-132">book, cook, look</span></span> | <span data-ttu-id="6f259-133">dauerte</span><span class="sxs-lookup"><span data-stu-id="6f259-133">took</span></span> |
|<span data-ttu-id="6f259-134">\[ \]</span><span class="sxs-lookup"><span data-stu-id="6f259-134">\[ \]</span></span>   |<span data-ttu-id="6f259-135">Mit bestimmten Zeichen vergleichen</span><span class="sxs-lookup"><span data-stu-id="6f259-135">Match specific characters</span></span> | <span data-ttu-id="6f259-136">\[BC- \] ook</span><span class="sxs-lookup"><span data-stu-id="6f259-136">\[bc\]ook</span></span> | <span data-ttu-id="6f259-137">Buch, Kochen</span><span class="sxs-lookup"><span data-stu-id="6f259-137">book, cook</span></span> | <span data-ttu-id="6f259-138">Schließen</span><span class="sxs-lookup"><span data-stu-id="6f259-138">hook</span></span> |

<span data-ttu-id="6f259-139">Sie können mehrere Platzhalter Zeichen in das gleiche Word-Muster einschließen.</span><span class="sxs-lookup"><span data-stu-id="6f259-139">You can include multiple wildcard characters in the same word pattern.</span></span> <span data-ttu-id="6f259-140">Wenn Sie z. b. Textdateien suchen möchten, deren Namen mit den Buchstaben **a** bis **l** beginnen, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="6f259-140">For example, to find text files with names that begin with the letters **a** through **l**, type:</span></span>

```powershell
Get-ChildItem C:\Techdocs\[a-l]*.txt
```

<span data-ttu-id="6f259-141">Viele Cmdlets akzeptieren Platzhalter Zeichen in Parameterwerten.</span><span class="sxs-lookup"><span data-stu-id="6f259-141">Many cmdlets accept wildcard characters in parameter values.</span></span> <span data-ttu-id="6f259-142">Im Hilfethema für jedes Cmdlet wird beschrieben, welche Parameter Platzhalter Zeichen akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="6f259-142">The Help topic for each cmdlet describes which parameters accept wildcard characters.</span></span> <span data-ttu-id="6f259-143">Bei Parametern, die Platzhalter Zeichen akzeptieren, wird bei der Verwendung die Groß-/Kleinschreibung</span><span class="sxs-lookup"><span data-stu-id="6f259-143">For parameters that accept wildcard characters, their use is case-insensitive.</span></span>

<span data-ttu-id="6f259-144">Sie können Platzhalter Zeichen in Befehlen und Skript Blöcken verwenden, z. b. zum Erstellen eines Word-Musters, das Eigenschaftswerte darstellt.</span><span class="sxs-lookup"><span data-stu-id="6f259-144">You can use wildcard characters in commands and script blocks, such as to create a word pattern that represents property values.</span></span> <span data-ttu-id="6f259-145">Beispielsweise werden mit dem folgenden Befehl Dienste abgerufen, in denen der **serviceType** -Eigenschafts Wert **interaktiv** enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="6f259-145">For example, the following command gets services in which the **ServiceType** property value includes **Interactive**.</span></span>

```powershell
Get-Service | Where-Object {$_.ServiceType -Like "*Interactive*"}
```

<span data-ttu-id="6f259-146">Im folgenden Beispiel enthält die- `If` Anweisung eine Bedingung, die Platzhalter Zeichen verwendet, um Eigenschaftswerte zu suchen.</span><span class="sxs-lookup"><span data-stu-id="6f259-146">In the following example, the `If` statement includes a condition that uses wildcard characters to find property values.</span></span> <span data-ttu-id="6f259-147">Wenn die **Beschreibung** des Wiederherstellungs Punkts **PowerShell** enthält, fügt der Befehl den Wert **der Eigenschaft "** " der Wiederherstellungspunkt-Eigenschaft einer Protokolldatei hinzu.</span><span class="sxs-lookup"><span data-stu-id="6f259-147">If the restore point's **Description** includes **PowerShell**, the command adds the value of the restore point's **CreationTime** property to a log file.</span></span>

```powershell
$p = Get-ComputerRestorePoint
foreach ($point in $p) {
  if ($point.description -like "*PowerShell*") {
    Add-Content -Path C:\TechDocs\RestoreLog.txt "$($point.CreationTime)"
  }
}
```

## <a name="see-also"></a><span data-ttu-id="6f259-148">SIEHE AUCH</span><span class="sxs-lookup"><span data-stu-id="6f259-148">SEE ALSO</span></span>

[<span data-ttu-id="6f259-149">about_Language_Keywords</span><span class="sxs-lookup"><span data-stu-id="6f259-149">about_Language_Keywords</span></span>](about_Language_Keywords.md)

[<span data-ttu-id="6f259-150">about_If</span><span class="sxs-lookup"><span data-stu-id="6f259-150">about_If</span></span>](about_If.md)

[<span data-ttu-id="6f259-151">about_Script_Blocks</span><span class="sxs-lookup"><span data-stu-id="6f259-151">about_Script_Blocks</span></span>](about_Script_Blocks.md)

