---
ms.date: 08/28/2019
ms.topic: reference
title: Importieren von Cmdlets mit Modulen
description: Importieren von Cmdlets mit Modulen
ms.openlocfilehash: 485a4be4d2accaf050a6536e7f92a0673f62a30b
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92657291"
---
# <a name="how-to-import-cmdlets-using-modules"></a><span data-ttu-id="3396c-103">Importieren von Cmdlets mit Modulen</span><span class="sxs-lookup"><span data-stu-id="3396c-103">How to Import Cmdlets Using Modules</span></span>

<span data-ttu-id="3396c-104">In diesem Artikel wird beschrieben, wie Sie Cmdlets mithilfe eines binären Moduls in eine PowerShell-Sitzung importieren.</span><span class="sxs-lookup"><span data-stu-id="3396c-104">This article describes how to import cmdlets to a PowerShell session by using a binary module.</span></span>

> [!NOTE]
> <span data-ttu-id="3396c-105">Die Member von Modulen können Cmdlets, Anbieter, Funktionen, Variablen, Aliase und vieles mehr enthalten.</span><span class="sxs-lookup"><span data-stu-id="3396c-105">The members of modules can include cmdlets, providers, functions, variables, aliases, and much more.</span></span> <span data-ttu-id="3396c-106">Snap-Ins können nur Cmdlets und Anbieter enthalten.</span><span class="sxs-lookup"><span data-stu-id="3396c-106">Snap-ins can contain only cmdlets and providers.</span></span>

## <a name="how-to-load-cmdlets-using-a-module"></a><span data-ttu-id="3396c-107">Vorgehensweise beim Laden von Cmdlets mithilfe eines Moduls</span><span class="sxs-lookup"><span data-stu-id="3396c-107">How to load cmdlets using a module</span></span>

1. <span data-ttu-id="3396c-108">Erstellen Sie einen Modul Ordner, der denselben Namen hat wie die Assemblydatei, in der die Cmdlets implementiert sind.</span><span class="sxs-lookup"><span data-stu-id="3396c-108">Create a module folder that has the same name as the assembly file in which the cmdlets are implemented.</span></span> <span data-ttu-id="3396c-109">In diesem Verfahren wird der Modul Ordner im Windows-Ordner erstellt `system32` .</span><span class="sxs-lookup"><span data-stu-id="3396c-109">In this procedure, the module folder is created in the Windows `system32` folder.</span></span>

   `%SystemRoot%\system32\WindowsPowerShell\v1.0\Modules\mymodule`

1. <span data-ttu-id="3396c-110">Stellen Sie sicher, dass die `PSModulePath` Umgebungsvariable den Pfad zum neuen Modul Ordner enthält.</span><span class="sxs-lookup"><span data-stu-id="3396c-110">Make sure that the `PSModulePath` environment variable includes the path to your new module folder.</span></span> <span data-ttu-id="3396c-111">Standardmäßig ist der Systemordner bereits der `PSModulePath` Umgebungsvariablen hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="3396c-111">By default, the system folder is already added to the `PSModulePath` environment variable.</span></span> <span data-ttu-id="3396c-112">Geben Sie zum Anzeigen von Folgendes ein `PSModulePath` : `$env:PSModulePath` .</span><span class="sxs-lookup"><span data-stu-id="3396c-112">To view the `PSModulePath`, type: `$env:PSModulePath`.</span></span>

1. <span data-ttu-id="3396c-113">Kopieren Sie die Cmdlet-Assembly in den Modul Ordner.</span><span class="sxs-lookup"><span data-stu-id="3396c-113">Copy the cmdlet assembly into the module folder.</span></span>

1. <span data-ttu-id="3396c-114">Fügen Sie im Stamm Ordner des Moduls eine Modul Manifest-Datei ( `.psd1` ) hinzu.</span><span class="sxs-lookup"><span data-stu-id="3396c-114">Add a module manifest file (`.psd1`) in the module's root folder.</span></span> <span data-ttu-id="3396c-115">PowerShell verwendet das Modul Manifest, um das Modul zu importieren.</span><span class="sxs-lookup"><span data-stu-id="3396c-115">PowerShell uses the module manifest to import your module.</span></span> <span data-ttu-id="3396c-116">Weitere Informationen finden Sie unter Gewusst [wie: Schreiben eines PowerShell-Modul Manifests](../module/how-to-write-a-powershell-module-manifest.md).</span><span class="sxs-lookup"><span data-stu-id="3396c-116">For more information, see [How to Write a PowerShell Module Manifest](../module/how-to-write-a-powershell-module-manifest.md).</span></span>

1. <span data-ttu-id="3396c-117">Führen Sie den folgenden Befehl aus, um der Sitzung die Cmdlets hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="3396c-117">Run the following command to add the cmdlets to the session:</span></span>

   `Import-Module [Module_Name]`

   <span data-ttu-id="3396c-118">Mithilfe dieses Verfahrens können Sie die Cmdlets testen.</span><span class="sxs-lookup"><span data-stu-id="3396c-118">This procedure can be used to test your cmdlets.</span></span> <span data-ttu-id="3396c-119">Der Sitzung werden alle Cmdlets in der Assembly hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="3396c-119">It adds all the cmdlets in the assembly to the session.</span></span> <span data-ttu-id="3396c-120">Weitere Informationen zu Modulen finden Sie unter [Schreiben eines Windows PowerShell-Moduls](../module/writing-a-windows-powershell-module.md).</span><span class="sxs-lookup"><span data-stu-id="3396c-120">For more information about modules, see [Writing a Windows PowerShell Module](../module/writing-a-windows-powershell-module.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="3396c-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3396c-121">See also</span></span>

[<span data-ttu-id="3396c-122">Schreiben eines PowerShell-Binärmoduls</span><span class="sxs-lookup"><span data-stu-id="3396c-122">How to Write a PowerShell Module Manifest</span></span>](../module/how-to-write-a-powershell-module-manifest.md)

[<span data-ttu-id="3396c-123">Importieren eines PowerShell-Moduls</span><span class="sxs-lookup"><span data-stu-id="3396c-123">Importing a PowerShell Module</span></span>](../module/importing-a-powershell-module.md)

[<span data-ttu-id="3396c-124">Import-Module</span><span class="sxs-lookup"><span data-stu-id="3396c-124">Import-Module</span></span>](/powershell/module/Microsoft.PowerShell.Core/Import-Module)

[<span data-ttu-id="3396c-125">Installieren von Modulen</span><span class="sxs-lookup"><span data-stu-id="3396c-125">Installing Modules</span></span>](../module/installing-a-powershell-module.md)

[<span data-ttu-id="3396c-126">Ändern des Installationspfads PSModulePath</span><span class="sxs-lookup"><span data-stu-id="3396c-126">Modifying the PSModulePath Installation Path</span></span>](../module/modifying-the-psmodulepath-installation-path.md)

[<span data-ttu-id="3396c-127">Schreiben eines Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="3396c-127">Writing a Windows PowerShell Cmdlet</span></span>](../cmdlet/cmdlet-overview.md)
