---
ms.date: 07/29/2020
keywords: powershell,cmdlet
ms.topic: how-to
title: Verwenden der PowerShell-Dokumentation
description: In diesem Artikel werden die Features dieser Website erläutert, einschließlich der Filterung zur Suche und der Versionsauswahl.
ms.openlocfilehash: 4779e6e4b17c461d71e9d613d1184b9ce2e7ab7b
ms.sourcegitcommit: df5e6f032ee2d4b556d50406832732d2f7dc2502
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/14/2021
ms.locfileid: "98216081"
---
# <a name="how-to-use-the-powershell-documentation"></a><span data-ttu-id="cea08-104">Verwenden der PowerShell-Dokumentation</span><span class="sxs-lookup"><span data-stu-id="cea08-104">How to use the PowerShell documentation</span></span>

<span data-ttu-id="cea08-105">Willkommen bei der PowerShell-Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="cea08-105">Welcome to the PowerShell online documentation.</span></span> <span data-ttu-id="cea08-106">Auf dieser Website finden Sie die Cmdlet-Referenz für die folgenden PowerShell-Versionen:</span><span class="sxs-lookup"><span data-stu-id="cea08-106">This site contains cmdlet reference for the following versions of PowerShell:</span></span>

- <span data-ttu-id="cea08-107">PowerShell 7.2 (Vorabversion)</span><span class="sxs-lookup"><span data-stu-id="cea08-107">PowerShell 7.2 (prerelease)</span></span>
- <span data-ttu-id="cea08-108">PowerShell 7.1 (aktuell)</span><span class="sxs-lookup"><span data-stu-id="cea08-108">PowerShell 7.1 (current)</span></span>
- <span data-ttu-id="cea08-109">PowerShell 7.0 (LTS)</span><span class="sxs-lookup"><span data-stu-id="cea08-109">PowerShell 7.0 (LTS)</span></span>
- <span data-ttu-id="cea08-110">PowerShell 5.1</span><span class="sxs-lookup"><span data-stu-id="cea08-110">PowerShell 5.1</span></span>

## <a name="finding-articles-and-selecting-a-version"></a><span data-ttu-id="cea08-111">Suchen von Artikeln und Auswählen einer Version</span><span class="sxs-lookup"><span data-stu-id="cea08-111">Finding articles and selecting a version</span></span>

<span data-ttu-id="cea08-112">Es gibt zwei Möglichkeiten, um in der Dokumentation nach Inhalten zu suchen. Der einfachste Weg ist die Verwendung des Filterfelds unter der Versionsauswahl.</span><span class="sxs-lookup"><span data-stu-id="cea08-112">There are two ways to search for content in Docs. The simplest way is to use the filter box under the version selector.</span></span> <span data-ttu-id="cea08-113">Geben Sie einfach ein Wort ein, das im Titel eines Artikels enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="cea08-113">Just enter a word that appears in the title of an article.</span></span> <span data-ttu-id="cea08-114">Es wird eine Liste der passenden Artikel angezeigt.</span><span class="sxs-lookup"><span data-stu-id="cea08-114">The page displays a list of matching articles.</span></span> <span data-ttu-id="cea08-115">Sie können auch festlegen, dass die gesamte Website anhand dieser Liste durchsucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="cea08-115">You can also select the option to search the entire site from that list.</span></span>

<span data-ttu-id="cea08-116">Standardmäßig ist auf dieser Website die Dokumentation für die neueste veröffentlichte Version von PowerShell zu sehen.</span><span class="sxs-lookup"><span data-stu-id="cea08-116">By default, this site displays documentation for the latest released version of PowerShell.</span></span> <span data-ttu-id="cea08-117">Einige Cmdlets funktionieren in verschiedenen Versionen von PowerShell unterschiedlich.</span><span class="sxs-lookup"><span data-stu-id="cea08-117">Some cmdlets work differently in various versions of PowerShell.</span></span> <span data-ttu-id="cea08-118">Stellen Sie sicher, dass Sie die Dokumentation für die von Ihnen verwendete Version von PowerShell anzeigen.</span><span class="sxs-lookup"><span data-stu-id="cea08-118">Be sure you are viewing the documentation for the version of PowerShell you are using.</span></span>

<span data-ttu-id="cea08-119">Verwenden Sie die Versionsauswahl oben auf der Seite, um die gewünschte Version von PowerShell auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="cea08-119">Use the version picker at the top of the page to select the version of PowerShell you want.</span></span>

![Verwenden der Versionsauswahl](media/how-to-use-docs/version-search.gif)

<span data-ttu-id="cea08-121">Anhand des Werts `$PSversionTable.PSVersion` können Sie erkennen, welche Version von PowerShell Sie verwenden.</span><span class="sxs-lookup"><span data-stu-id="cea08-121">You can verify the version of PowerShell you are using by inspecting the `$PSversionTable.PSVersion` value.</span></span> <span data-ttu-id="cea08-122">Das folgende Beispiel zeigt die Ausgabe für Windows PowerShell 5.1.</span><span class="sxs-lookup"><span data-stu-id="cea08-122">The following example shows the output for Windows PowerShell 5.1.</span></span>

```powershell
$PSVersionTable.PSVersion
```

```Output
Major  Minor  Build  Revision
-----  -----  -----  --------
5      1      19041  1
```

<span data-ttu-id="cea08-123">Wenn Sie noch nicht mit PowerShell vertraut sind und Hilfe zum Verstehen der Befehlssyntax benötigen, finden Sie weitere Informationen unter [about_Command_Syntax](/powershell/module/microsoft.powershell.core/about/about_command_syntax).</span><span class="sxs-lookup"><span data-stu-id="cea08-123">If you are new to PowerShell and need help understanding the command syntax, see [about_Command_Syntax](/powershell/module/microsoft.powershell.core/about/about_command_syntax).</span></span>

## <a name="finding-articles-for-previous-versions"></a><span data-ttu-id="cea08-124">Suchen von Artikeln für Vorgängerversionen</span><span class="sxs-lookup"><span data-stu-id="cea08-124">Finding articles for previous versions</span></span>

<span data-ttu-id="cea08-125">Die Dokumentation für ältere PowerShell-Versionen wurde auf unserer Website zu [Vorgängerversionen](https://aka.ms/PSLegacyDocs) archiviert.</span><span class="sxs-lookup"><span data-stu-id="cea08-125">Documentation for older versions of PowerShell has been archived in our [Previous Versions](https://aka.ms/PSLegacyDocs) site.</span></span>

<span data-ttu-id="cea08-126">Diese Website enthält die Dokumentation für die folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="cea08-126">This site contains documentation for the following topics:</span></span>

- <span data-ttu-id="cea08-127">PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="cea08-127">PowerShell 3.0</span></span>
- <span data-ttu-id="cea08-128">PowerShell 4.0</span><span class="sxs-lookup"><span data-stu-id="cea08-128">PowerShell 4.0</span></span>
- <span data-ttu-id="cea08-129">PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="cea08-129">PowerShell 5.0</span></span>
- <span data-ttu-id="cea08-130">PowerShell 6</span><span class="sxs-lookup"><span data-stu-id="cea08-130">PowerShell 6</span></span>
- <span data-ttu-id="cea08-131">PowerShell-Workflows</span><span class="sxs-lookup"><span data-stu-id="cea08-131">PowerShell Workflows</span></span>
- <span data-ttu-id="cea08-132">PowerShell Web Access</span><span class="sxs-lookup"><span data-stu-id="cea08-132">PowerShell Web Access</span></span>
