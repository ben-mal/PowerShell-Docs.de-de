---
ms.date: 09/12/2016
ms.topic: reference
title: Testen der aktualisierbaren Hilfe
description: Testen der aktualisierbaren Hilfe
ms.openlocfilehash: 47873089bfa1b918ea9970915e829a22aa7254c5
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667622"
---
# <a name="how-to-test-updatable-help"></a><span data-ttu-id="0390c-103">Testen der aktualisierbaren Hilfe</span><span class="sxs-lookup"><span data-stu-id="0390c-103">How to Test Updatable Help</span></span>

<span data-ttu-id="0390c-104">In diesem Thema werden die Ansätze zum Testen der aktualisierbaren Hilfe für ein Modul beschrieben.</span><span class="sxs-lookup"><span data-stu-id="0390c-104">This topic describes approaches to testing Updatable Help for a module.</span></span>

## <a name="using-verbose-to-detect-errors"></a><span data-ttu-id="0390c-105">Verwenden von Verbose zum Erkennen von Fehlern</span><span class="sxs-lookup"><span data-stu-id="0390c-105">Using Verbose to Detect Errors</span></span>

<span data-ttu-id="0390c-106">Nachdem Sie die helpinfo-XML-Datei und die CAB-Dateien für das Modul hochgeladen haben, testen Sie die Dateien, indem Sie einen [Update-Help-](/powershell/module/Microsoft.PowerShell.Core/Update-Help) Befehl mit dem Parameter **verbose** ausführen</span><span class="sxs-lookup"><span data-stu-id="0390c-106">After uploading the HelpInfo XML file and CAB files for your module, test the files by running an [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) command with the **Verbose** parameter.</span></span> <span data-ttu-id="0390c-107">Der **verbose** -Parameter weist `Update-Help` an, die wichtigen Schritte in seinen Aktionen zu melden, von dem Lesen des **helpinfouri** -Schlüssels im Modul Manifest, um die Dateitypen in der entpackten CAB-Datei zu überprüfen und die Dateien in das sprachspezifische Modul Verzeichnis zu platzieren.</span><span class="sxs-lookup"><span data-stu-id="0390c-107">The **Verbose** parameter directs `Update-Help` to report the critical steps in its actions, from reading the **HelpInfoUri** key in the module manifest to validating the file types in the unpacked CAB file and placing the files in the language-specific module directory.</span></span>

<span data-ttu-id="0390c-108">Wenn alle ausführlichen Meldungen aufgelöst werden, führen Sie einen `Update-Help` Befehl mit dem **Debug** -Parameter aus.</span><span class="sxs-lookup"><span data-stu-id="0390c-108">When all verbose messages are resolved, run an `Update-Help` command with the **Debug** parameter.</span></span>
<span data-ttu-id="0390c-109">Dieser Parameter sollte alle verbleibenden Probleme mit den aktualisierbaren Hilfedateien erkennen.</span><span class="sxs-lookup"><span data-stu-id="0390c-109">This parameter should detect any remaining problems with the Updatable Help files.</span></span>
