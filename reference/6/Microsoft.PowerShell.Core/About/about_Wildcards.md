---
description: Beschreibt die Verwendung von Platzhalter Zeichen in PowerShell.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 3/28/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_wildcards?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Wildcards
ms.openlocfilehash: ccd869e46ee682f6dade31ef0c782ff17653ba38
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93221047"
---
# <a name="about-wildcards"></a><span data-ttu-id="488f6-104">Informationen zu Platzhaltern</span><span class="sxs-lookup"><span data-stu-id="488f6-104">About Wildcards</span></span>

## <a name="short-description"></a><span data-ttu-id="488f6-105">KURZE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="488f6-105">SHORT DESCRIPTION</span></span>

<span data-ttu-id="488f6-106">Beschreibt die Verwendung von Platzhalter Zeichen in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="488f6-106">Describes how to use wildcard characters in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="488f6-107">LANGE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="488f6-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="488f6-108">Platzhalter Zeichen stellen ein oder mehrere Zeichen dar.</span><span class="sxs-lookup"><span data-stu-id="488f6-108">Wildcard characters represent one or many characters.</span></span> <span data-ttu-id="488f6-109">Sie können Sie zum Erstellen von Wort Mustern in Befehlen verwenden.</span><span class="sxs-lookup"><span data-stu-id="488f6-109">You can use them to create word patterns in commands.</span></span> <span data-ttu-id="488f6-110">Wenn Sie z. b. alle Dateien im `C:\Techdocs` Verzeichnis mit der `.ppt` Dateinamenerweiterung erhalten möchten, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="488f6-110">For example, to get all the files in the `C:\Techdocs` directory with a `.ppt` file name extension, type:</span></span>

```powershell
Get-ChildItem C:\Techdocs\*.ppt
```

<span data-ttu-id="488f6-111">In diesem Fall stellt das Platzhalter `*` Zeichen Sternchen () alle Zeichen dar, die vor der `.ppt` Dateinamenerweiterung angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="488f6-111">In this case, the asterisk (`*`) wildcard character represents any characters that appear before the `.ppt` file name extension.</span></span>

<span data-ttu-id="488f6-112">PowerShell unterstützt die folgenden Platzhalter Zeichen:</span><span class="sxs-lookup"><span data-stu-id="488f6-112">PowerShell supports the following wildcard characters:</span></span>

|<span data-ttu-id="488f6-113">Platzhalter</span><span class="sxs-lookup"><span data-stu-id="488f6-113">Wildcard</span></span>|<span data-ttu-id="488f6-114">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="488f6-114">Description</span></span>               |<span data-ttu-id="488f6-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="488f6-115">Example</span></span> |<span data-ttu-id="488f6-116">Match</span><span class="sxs-lookup"><span data-stu-id="488f6-116">Match</span></span>        |<span data-ttu-id="488f6-117">Keine Entsprechung</span><span class="sxs-lookup"><span data-stu-id="488f6-117">No Match</span></span>|
|--------|--------------------------|--------|-------------|--------|
|\*      |<span data-ttu-id="488f6-118">Entsprechung für NULL oder mehr Zeichen</span><span class="sxs-lookup"><span data-stu-id="488f6-118">Match zero or more characters</span></span> | <span data-ttu-id="488f6-119">ein\*</span><span class="sxs-lookup"><span data-stu-id="488f6-119">a\*</span></span>  | <span data-ttu-id="488f6-120">AA, AG, Apple</span><span class="sxs-lookup"><span data-stu-id="488f6-120">aA, ag, Apple</span></span> | <span data-ttu-id="488f6-121">Bananen</span><span class="sxs-lookup"><span data-stu-id="488f6-121">banana</span></span> |
|<span data-ttu-id="488f6-122">?</span><span class="sxs-lookup"><span data-stu-id="488f6-122">?</span></span>       |<span data-ttu-id="488f6-123">Mit einem Zeichen an dieser Position vergleichen</span><span class="sxs-lookup"><span data-stu-id="488f6-123">Match one character in that position</span></span> | <span data-ttu-id="488f6-124">? n</span><span class="sxs-lookup"><span data-stu-id="488f6-124">?n</span></span> | <span data-ttu-id="488f6-125">ein, in, ein</span><span class="sxs-lookup"><span data-stu-id="488f6-125">an, in, on</span></span> | <span data-ttu-id="488f6-126">an</span><span class="sxs-lookup"><span data-stu-id="488f6-126">ran</span></span> |
|<span data-ttu-id="488f6-127">\[ \]</span><span class="sxs-lookup"><span data-stu-id="488f6-127">\[ \]</span></span>   |<span data-ttu-id="488f6-128">Mit einem Zeichenbereich vergleichen</span><span class="sxs-lookup"><span data-stu-id="488f6-128">Match a range of characters</span></span> | <span data-ttu-id="488f6-129">\[a-l \] ook</span><span class="sxs-lookup"><span data-stu-id="488f6-129">\[a-l\]ook</span></span> | <span data-ttu-id="488f6-130">Buch, Kochen, ansehen</span><span class="sxs-lookup"><span data-stu-id="488f6-130">book, cook, look</span></span> | <span data-ttu-id="488f6-131">dauerte</span><span class="sxs-lookup"><span data-stu-id="488f6-131">took</span></span> |
|<span data-ttu-id="488f6-132">\[ \]</span><span class="sxs-lookup"><span data-stu-id="488f6-132">\[ \]</span></span>   |<span data-ttu-id="488f6-133">Mit bestimmten Zeichen vergleichen</span><span class="sxs-lookup"><span data-stu-id="488f6-133">Match specific characters</span></span> | <span data-ttu-id="488f6-134">\[BC- \] ook</span><span class="sxs-lookup"><span data-stu-id="488f6-134">\[bc\]ook</span></span> | <span data-ttu-id="488f6-135">Buch, Kochen</span><span class="sxs-lookup"><span data-stu-id="488f6-135">book, cook</span></span> | <span data-ttu-id="488f6-136">Schließen</span><span class="sxs-lookup"><span data-stu-id="488f6-136">hook</span></span> |

<span data-ttu-id="488f6-137">Sie können mehrere Platzhalter Zeichen in das gleiche Word-Muster einschließen.</span><span class="sxs-lookup"><span data-stu-id="488f6-137">You can include multiple wildcard characters in the same word pattern.</span></span> <span data-ttu-id="488f6-138">Wenn Sie z. b. Textdateien suchen möchten, deren Namen mit den Buchstaben **a** bis **l** beginnen, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="488f6-138">For example, to find text files with names that begin with the letters **a** through **l** , type:</span></span>

```powershell
Get-ChildItem C:\Techdocs\[a-l]*.txt
```

<span data-ttu-id="488f6-139">Viele Cmdlets akzeptieren Platzhalter Zeichen in Parameterwerten.</span><span class="sxs-lookup"><span data-stu-id="488f6-139">Many cmdlets accept wildcard characters in parameter values.</span></span> <span data-ttu-id="488f6-140">Im Hilfethema für jedes Cmdlet wird beschrieben, welche Parameter Platzhalter Zeichen akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="488f6-140">The Help topic for each cmdlet describes which parameters accept wildcard characters.</span></span> <span data-ttu-id="488f6-141">Bei Parametern, die Platzhalter Zeichen akzeptieren, wird bei der Verwendung die Groß-/Kleinschreibung</span><span class="sxs-lookup"><span data-stu-id="488f6-141">For parameters that accept wildcard characters, their use is case-insensitive.</span></span>

<span data-ttu-id="488f6-142">Sie können Platzhalter Zeichen in Befehlen und Skript Blöcken verwenden, z. b. zum Erstellen eines Word-Musters, das Eigenschaftswerte darstellt.</span><span class="sxs-lookup"><span data-stu-id="488f6-142">You can use wildcard characters in commands and script blocks, such as to create a word pattern that represents property values.</span></span> <span data-ttu-id="488f6-143">Beispielsweise werden mit dem folgenden Befehl Dienste abgerufen, in denen der **serviceType** -Eigenschafts Wert **interaktiv** enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="488f6-143">For example, the following command gets services in which the **ServiceType** property value includes **Interactive**.</span></span>

```powershell
Get-Service | Where-Object {$_.ServiceType -Like "*Interactive*"}
```

<span data-ttu-id="488f6-144">Im folgenden Beispiel enthält die- `If` Anweisung eine Bedingung, die Platzhalter Zeichen verwendet, um Eigenschaftswerte zu suchen.</span><span class="sxs-lookup"><span data-stu-id="488f6-144">In the following example, the `If` statement includes a condition that uses wildcard characters to find property values.</span></span> <span data-ttu-id="488f6-145">Wenn die **Beschreibung** des Wiederherstellungs Punkts **PowerShell** enthält, fügt der Befehl den Wert **der Eigenschaft "** " der Wiederherstellungspunkt-Eigenschaft einer Protokolldatei hinzu.</span><span class="sxs-lookup"><span data-stu-id="488f6-145">If the restore point's **Description** includes **PowerShell** , the command adds the value of the restore point's **CreationTime** property to a log file.</span></span>

```powershell
$p = Get-ComputerRestorePoint
foreach ($point in $p) {
  if ($point.description -like "*PowerShell*") {
    Add-Content -Path C:\TechDocs\RestoreLog.txt "$($point.CreationTime)"
  }
}
```

## <a name="see-also"></a><span data-ttu-id="488f6-146">SIEHE AUCH</span><span class="sxs-lookup"><span data-stu-id="488f6-146">SEE ALSO</span></span>

[<span data-ttu-id="488f6-147">about_Language_Keywords</span><span class="sxs-lookup"><span data-stu-id="488f6-147">about_Language_Keywords</span></span>](about_Language_Keywords.md)

[<span data-ttu-id="488f6-148">about_If</span><span class="sxs-lookup"><span data-stu-id="488f6-148">about_If</span></span>](about_If.md)

[<span data-ttu-id="488f6-149">about_Script_Blocks</span><span class="sxs-lookup"><span data-stu-id="488f6-149">about_Script_Blocks</span></span>](about_Script_Blocks.md)
