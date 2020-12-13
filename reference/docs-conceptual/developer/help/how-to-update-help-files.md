---
ms.date: 09/12/2016
ms.topic: reference
title: Aktualisieren von Hilfedateien
description: Aktualisieren von Hilfedateien
ms.openlocfilehash: 19bf501cf91b1eb5dabb334c2179953590b40232
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92649582"
---
# <a name="how-to-update-help-files"></a><span data-ttu-id="f8e7e-103">Aktualisieren von Hilfedateien</span><span class="sxs-lookup"><span data-stu-id="f8e7e-103">How to Update Help Files</span></span>

<span data-ttu-id="f8e7e-104">In diesem Thema wird erläutert, wie Sie Hilfedateien für ein Modul aktualisieren, das aktualisierbare Hilfe unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f8e7e-104">This topic explains how to update help files for a module that supports Updatable Help.</span></span>

## <a name="updating-help-files"></a><span data-ttu-id="f8e7e-105">Aktualisieren von Hilfedateien</span><span class="sxs-lookup"><span data-stu-id="f8e7e-105">Updating Help Files</span></span>

<span data-ttu-id="f8e7e-106">Es gibt viele Gründe, Hilfedateien zu aktualisieren, wie z. b. das Beheben von Fehlern, das verdeutlichen eines Konzepts, das Beantworten einer häufig gestellten Frage, das Hinzufügen neuer Dateien oder das Hinzufügen neuer und besserer Beispiele.</span><span class="sxs-lookup"><span data-stu-id="f8e7e-106">There are many reasons to update help files, such as correcting errors, clarifying a concept, answering a frequently-asked question, adding new files, or adding new and better examples.</span></span>

<span data-ttu-id="f8e7e-107">So aktualisieren Sie eine Hilfedatei:</span><span class="sxs-lookup"><span data-stu-id="f8e7e-107">To update a help file:</span></span>

1. <span data-ttu-id="f8e7e-108">Ändern Sie die Dateien.</span><span class="sxs-lookup"><span data-stu-id="f8e7e-108">Change the files.</span></span>
1. <span data-ttu-id="f8e7e-109">Übersetzen Sie die Dateien in andere Benutzeroberflächen Kulturen.</span><span class="sxs-lookup"><span data-stu-id="f8e7e-109">Translate the files into other UI cultures.</span></span>
1. <span data-ttu-id="f8e7e-110">Sammeln Sie alle Hilfedateien (neu, geändert und unverändert) für das Modul in jeder Benutzeroberflächen Kultur.</span><span class="sxs-lookup"><span data-stu-id="f8e7e-110">Collect all help files (new, changed, and unchanged) for the module in each UI culture.</span></span>
1. <span data-ttu-id="f8e7e-111">Überprüfen Sie die Dateien anhand des XML-Schemas.</span><span class="sxs-lookup"><span data-stu-id="f8e7e-111">Validate the files against the XML schema.</span></span>
1. <span data-ttu-id="f8e7e-112">Erstellen Sie die CAB-Dateien für jede Benutzeroberflächen Kultur neu.</span><span class="sxs-lookup"><span data-stu-id="f8e7e-112">Rebuild the CAB files for each UI culture.</span></span>
1. <span data-ttu-id="f8e7e-113">Erhöhen Sie in der helpinfo-XML-Datei die Versionsnummern der CAB-Datei für jede Benutzeroberflächen Kultur.</span><span class="sxs-lookup"><span data-stu-id="f8e7e-113">In the HelpInfo XML file, increment the version numbers of the CAB file for each UI culture.</span></span>
1. <span data-ttu-id="f8e7e-114">Laden Sie die neuen CAB-Dateien an den Speicherort hoch, der durch den Wert des **helpcontenturi** -Elements in der helpinfo-XML-Datei angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="f8e7e-114">Upload the new CAB files to the location that is specified by the value of the **HelpContentUri** element in the HelpInfo XML file.</span></span> <span data-ttu-id="f8e7e-115">Ersetzen Sie die älteren CAB-Dateien durch die neuen CAB-Dateien.</span><span class="sxs-lookup"><span data-stu-id="f8e7e-115">Replace the older CAB files with the new CAB files.</span></span>
1. <span data-ttu-id="f8e7e-116">Laden Sie die aktualisierte helpinfo-XML-Datei an den Speicherort hoch, der durch den **helpinfouri** -Schlüssel im Modul Manifest angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="f8e7e-116">Upload the updated HelpInfo XML file to the location that is specified by the **HelpInfoUri** key in the module manifest.</span></span> <span data-ttu-id="f8e7e-117">Ersetzen Sie die ältere helpinfo-XML-Datei durch die neue Datei.</span><span class="sxs-lookup"><span data-stu-id="f8e7e-117">Replace the older HelpInfo XML file with the new file.</span></span>
