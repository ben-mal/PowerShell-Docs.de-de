---
description: Beschreibt die Verwendung von Platzhalter Zeichen in PowerShell.
Locale: en-US
ms.date: 03/28/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_wildcards?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Wildcards
ms.openlocfilehash: b5f13fdbfbc24e19e5ad0b1cd6ecc1b99f68914f
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99596548"
---
# <a name="about-wildcards"></a><span data-ttu-id="b5d1e-103">Informationen zu Platzhaltern</span><span class="sxs-lookup"><span data-stu-id="b5d1e-103">About Wildcards</span></span>

## <a name="short-description"></a><span data-ttu-id="b5d1e-104">KURZE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="b5d1e-104">SHORT DESCRIPTION</span></span>

<span data-ttu-id="b5d1e-105">Beschreibt die Verwendung von Platzhalter Zeichen in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b5d1e-105">Describes how to use wildcard characters in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="b5d1e-106">LANGE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="b5d1e-106">LONG DESCRIPTION</span></span>

<span data-ttu-id="b5d1e-107">Platzhalter Zeichen stellen ein oder mehrere Zeichen dar.</span><span class="sxs-lookup"><span data-stu-id="b5d1e-107">Wildcard characters represent one or many characters.</span></span> <span data-ttu-id="b5d1e-108">Sie können Sie zum Erstellen von Wort Mustern in Befehlen verwenden.</span><span class="sxs-lookup"><span data-stu-id="b5d1e-108">You can use them to create word patterns in commands.</span></span> <span data-ttu-id="b5d1e-109">Wenn Sie z. b. alle Dateien im `C:\Techdocs` Verzeichnis mit der `.ppt` Dateinamenerweiterung erhalten möchten, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="b5d1e-109">For example, to get all the files in the `C:\Techdocs` directory with a `.ppt` file name extension, type:</span></span>

```powershell
Get-ChildItem C:\Techdocs\*.ppt
```

<span data-ttu-id="b5d1e-110">In diesem Fall stellt das Platzhalter `*` Zeichen Sternchen () alle Zeichen dar, die vor der `.ppt` Dateinamenerweiterung angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="b5d1e-110">In this case, the asterisk (`*`) wildcard character represents any characters that appear before the `.ppt` file name extension.</span></span>

<span data-ttu-id="b5d1e-111">PowerShell unterstützt die folgenden Platzhalter Zeichen:</span><span class="sxs-lookup"><span data-stu-id="b5d1e-111">PowerShell supports the following wildcard characters:</span></span>

|<span data-ttu-id="b5d1e-112">Platzhalter</span><span class="sxs-lookup"><span data-stu-id="b5d1e-112">Wildcard</span></span>|<span data-ttu-id="b5d1e-113">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="b5d1e-113">Description</span></span>               |<span data-ttu-id="b5d1e-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b5d1e-114">Example</span></span> |<span data-ttu-id="b5d1e-115">Match</span><span class="sxs-lookup"><span data-stu-id="b5d1e-115">Match</span></span>        |<span data-ttu-id="b5d1e-116">Keine Entsprechung</span><span class="sxs-lookup"><span data-stu-id="b5d1e-116">No Match</span></span>|
|--------|--------------------------|--------|-------------|--------|
|\*      |<span data-ttu-id="b5d1e-117">Entsprechung für NULL oder mehr Zeichen</span><span class="sxs-lookup"><span data-stu-id="b5d1e-117">Match zero or more characters</span></span> | <span data-ttu-id="b5d1e-118">ein\*</span><span class="sxs-lookup"><span data-stu-id="b5d1e-118">a\*</span></span>  | <span data-ttu-id="b5d1e-119">AA, AG, Apple</span><span class="sxs-lookup"><span data-stu-id="b5d1e-119">aA, ag, Apple</span></span> | <span data-ttu-id="b5d1e-120">Bananen</span><span class="sxs-lookup"><span data-stu-id="b5d1e-120">banana</span></span> |
|<span data-ttu-id="b5d1e-121">?</span><span class="sxs-lookup"><span data-stu-id="b5d1e-121">?</span></span>       |<span data-ttu-id="b5d1e-122">Mit einem Zeichen an dieser Position vergleichen</span><span class="sxs-lookup"><span data-stu-id="b5d1e-122">Match one character in that position</span></span> | <span data-ttu-id="b5d1e-123">? n</span><span class="sxs-lookup"><span data-stu-id="b5d1e-123">?n</span></span> | <span data-ttu-id="b5d1e-124">ein, in, ein</span><span class="sxs-lookup"><span data-stu-id="b5d1e-124">an, in, on</span></span> | <span data-ttu-id="b5d1e-125">an</span><span class="sxs-lookup"><span data-stu-id="b5d1e-125">ran</span></span> |
|<span data-ttu-id="b5d1e-126">\[ \]</span><span class="sxs-lookup"><span data-stu-id="b5d1e-126">\[ \]</span></span>   |<span data-ttu-id="b5d1e-127">Mit einem Zeichenbereich vergleichen</span><span class="sxs-lookup"><span data-stu-id="b5d1e-127">Match a range of characters</span></span> | <span data-ttu-id="b5d1e-128">\[a-l \] ook</span><span class="sxs-lookup"><span data-stu-id="b5d1e-128">\[a-l\]ook</span></span> | <span data-ttu-id="b5d1e-129">Buch, Kochen, ansehen</span><span class="sxs-lookup"><span data-stu-id="b5d1e-129">book, cook, look</span></span> | <span data-ttu-id="b5d1e-130">dauerte</span><span class="sxs-lookup"><span data-stu-id="b5d1e-130">took</span></span> |
|<span data-ttu-id="b5d1e-131">\[ \]</span><span class="sxs-lookup"><span data-stu-id="b5d1e-131">\[ \]</span></span>   |<span data-ttu-id="b5d1e-132">Mit bestimmten Zeichen vergleichen</span><span class="sxs-lookup"><span data-stu-id="b5d1e-132">Match specific characters</span></span> | <span data-ttu-id="b5d1e-133">\[BC- \] ook</span><span class="sxs-lookup"><span data-stu-id="b5d1e-133">\[bc\]ook</span></span> | <span data-ttu-id="b5d1e-134">Buch, Kochen</span><span class="sxs-lookup"><span data-stu-id="b5d1e-134">book, cook</span></span> | <span data-ttu-id="b5d1e-135">Schließen</span><span class="sxs-lookup"><span data-stu-id="b5d1e-135">hook</span></span> |

<span data-ttu-id="b5d1e-136">Sie können mehrere Platzhalter Zeichen in das gleiche Word-Muster einschließen.</span><span class="sxs-lookup"><span data-stu-id="b5d1e-136">You can include multiple wildcard characters in the same word pattern.</span></span> <span data-ttu-id="b5d1e-137">Wenn Sie z. b. Textdateien suchen möchten, deren Namen mit den Buchstaben **a** bis **l** beginnen, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="b5d1e-137">For example, to find text files with names that begin with the letters **a** through **l**, type:</span></span>

```powershell
Get-ChildItem C:\Techdocs\[a-l]*.txt
```

<span data-ttu-id="b5d1e-138">Viele Cmdlets akzeptieren Platzhalter Zeichen in Parameterwerten.</span><span class="sxs-lookup"><span data-stu-id="b5d1e-138">Many cmdlets accept wildcard characters in parameter values.</span></span> <span data-ttu-id="b5d1e-139">Im Hilfethema für jedes Cmdlet wird beschrieben, welche Parameter Platzhalter Zeichen akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="b5d1e-139">The Help topic for each cmdlet describes which parameters accept wildcard characters.</span></span> <span data-ttu-id="b5d1e-140">Bei Parametern, die Platzhalter Zeichen akzeptieren, wird bei der Verwendung die Groß-/Kleinschreibung</span><span class="sxs-lookup"><span data-stu-id="b5d1e-140">For parameters that accept wildcard characters, their use is case-insensitive.</span></span>

<span data-ttu-id="b5d1e-141">Sie können Platzhalter Zeichen in Befehlen und Skript Blöcken verwenden, z. b. zum Erstellen eines Word-Musters, das Eigenschaftswerte darstellt.</span><span class="sxs-lookup"><span data-stu-id="b5d1e-141">You can use wildcard characters in commands and script blocks, such as to create a word pattern that represents property values.</span></span> <span data-ttu-id="b5d1e-142">Beispielsweise werden mit dem folgenden Befehl Dienste abgerufen, in denen der **serviceType** -Eigenschafts Wert **interaktiv** enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="b5d1e-142">For example, the following command gets services in which the **ServiceType** property value includes **Interactive**.</span></span>

```powershell
Get-Service | Where-Object {$_.ServiceType -Like "*Interactive*"}
```

<span data-ttu-id="b5d1e-143">Im folgenden Beispiel enthält die- `If` Anweisung eine Bedingung, die Platzhalter Zeichen verwendet, um Eigenschaftswerte zu suchen.</span><span class="sxs-lookup"><span data-stu-id="b5d1e-143">In the following example, the `If` statement includes a condition that uses wildcard characters to find property values.</span></span> <span data-ttu-id="b5d1e-144">Wenn die **Beschreibung** des Wiederherstellungs Punkts **PowerShell** enthält, fügt der Befehl den Wert **der Eigenschaft "** " der Wiederherstellungspunkt-Eigenschaft einer Protokolldatei hinzu.</span><span class="sxs-lookup"><span data-stu-id="b5d1e-144">If the restore point's **Description** includes **PowerShell**, the command adds the value of the restore point's **CreationTime** property to a log file.</span></span>

```powershell
$p = Get-ComputerRestorePoint
foreach ($point in $p) {
  if ($point.description -like "*PowerShell*") {
    Add-Content -Path C:\TechDocs\RestoreLog.txt "$($point.CreationTime)"
  }
}
```

## <a name="see-also"></a><span data-ttu-id="b5d1e-145">SIEHE AUCH</span><span class="sxs-lookup"><span data-stu-id="b5d1e-145">SEE ALSO</span></span>

[<span data-ttu-id="b5d1e-146">about_Language_Keywords</span><span class="sxs-lookup"><span data-stu-id="b5d1e-146">about_Language_Keywords</span></span>](about_Language_Keywords.md)

[<span data-ttu-id="b5d1e-147">about_If</span><span class="sxs-lookup"><span data-stu-id="b5d1e-147">about_If</span></span>](about_If.md)

[<span data-ttu-id="b5d1e-148">about_Script_Blocks</span><span class="sxs-lookup"><span data-stu-id="b5d1e-148">about_Script_Blocks</span></span>](about_Script_Blocks.md)

