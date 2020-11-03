---
description: Erläutert, wie Sie die Funktion "mit PowerShell ausführen" verwenden, um ein Skript von einem Dateisystem Laufwerk auszuführen.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_run_with_powershell?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Run_With_PowerShell
ms.openlocfilehash: e08e762bf6017907de4f508438733c973121fc77
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93221220"
---
# <a name="about-run-with-powershell"></a><span data-ttu-id="73291-104">Informationen zum Ausführen mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="73291-104">About Run With PowerShell</span></span>

## <a name="short-description"></a><span data-ttu-id="73291-105">KURZE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="73291-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="73291-106">Erläutert, wie Sie die Funktion "mit PowerShell ausführen" verwenden, um ein Skript von einem Dateisystem Laufwerk auszuführen.</span><span class="sxs-lookup"><span data-stu-id="73291-106">Explains how to use the "Run with PowerShell" feature to run a script from a file system drive.</span></span>

## <a name="long-description"></a><span data-ttu-id="73291-107">LANGE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="73291-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="73291-108">Ab Windows PowerShell 3,0 können Sie die Funktion "mit PowerShell ausführen" verwenden, um Skripts aus dem Datei-Explorer in Windows 8 und Windows Server 2012 und aus Windows-Explorer in früheren Versionen von Windows auszuführen.</span><span class="sxs-lookup"><span data-stu-id="73291-108">Beginning in Windows PowerShell 3.0, you can use the "Run with PowerShell" feature to run scripts from File Explorer in Windows 8 and Windows Server 2012 and from Windows Explorer in earlier versions of Windows.</span></span>

<span data-ttu-id="73291-109">Die Funktion "mit PowerShell ausführen" dient zum Ausführen von Skripts, die nicht über erforderliche Parameter verfügen und keine Ausgabe an die Eingabeaufforderung zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="73291-109">The "Run with PowerShell" feature is designed to run scripts that do not have required parameters and do not return output to the command prompt.</span></span>

<span data-ttu-id="73291-110">Wenn Sie die Funktion "mit PowerShell ausführen" verwenden, wird das PowerShell-Konsolenfenster nur kurz angezeigt, wenn überhaupt.</span><span class="sxs-lookup"><span data-stu-id="73291-110">When you use the "Run with PowerShell" feature, the PowerShell console window appears only briefly, if at all.</span></span> <span data-ttu-id="73291-111">Es ist nicht möglich, mit ihm zu interagieren.</span><span class="sxs-lookup"><span data-stu-id="73291-111">You cannot interact with it.</span></span>

<span data-ttu-id="73291-112">So verwenden Sie die Funktion "mit PowerShell ausführen":</span><span class="sxs-lookup"><span data-stu-id="73291-112">To use the "Run with PowerShell" feature:</span></span>

<span data-ttu-id="73291-113">Klicken Sie im Datei-Explorer (oder Windows-Explorer) mit der rechten Maustaste auf den Namen der Skriptdatei, und wählen Sie dann die Option mit PowerShell ausführen aus.</span><span class="sxs-lookup"><span data-stu-id="73291-113">In File Explorer (or Windows Explorer), right-click the script file name and then select "Run with PowerShell".</span></span>

<span data-ttu-id="73291-114">Die Funktion "mit PowerShell ausführen" startet eine PowerShell-Sitzung mit der Ausführungs Richtlinie "Bypass", führt das Skript aus und schließt die Sitzung.</span><span class="sxs-lookup"><span data-stu-id="73291-114">The "Run with PowerShell" feature starts a PowerShell session that has an execution policy of Bypass, runs the script, and closes the session.</span></span>

<span data-ttu-id="73291-115">Er führt einen Befehl aus, der das folgende Format aufweist:</span><span class="sxs-lookup"><span data-stu-id="73291-115">It runs a command that has the following format:</span></span>

```
PowerShell.exe -File <FileName> -ExecutionPolicy Bypass
```

<span data-ttu-id="73291-116">"Mit PowerShell ausführen" legt die Umgehungs Ausführungs Richtlinie nur für die Sitzung (die aktuelle Instanz des PowerShell-Prozesses) fest, in der das Skript ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="73291-116">"Run with PowerShell" sets the Bypass execution policy only for the session (the current instance of the PowerShell process) in which the script runs.</span></span>
<span data-ttu-id="73291-117">Diese Funktion ändert nicht die Ausführungs Richtlinie für den Computer oder den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="73291-117">This feature does not change the execution policy for the computer or the user.</span></span>

<span data-ttu-id="73291-118">Die Funktion "mit PowerShell ausführen" ist nur durch die AllSigned-Ausführungs Richtlinie betroffen.</span><span class="sxs-lookup"><span data-stu-id="73291-118">The "Run with PowerShell" feature is affected only by the AllSigned execution policy.</span></span> <span data-ttu-id="73291-119">Wenn die AllSigned-Ausführungs Richtlinie für den Computer oder den Benutzer wirksam ist, führt "Run with PowerShell" nur signierte Skripts aus.</span><span class="sxs-lookup"><span data-stu-id="73291-119">If the AllSigned execution policy is effective for the computer or the user, "Run with PowerShell" runs only signed scripts.</span></span> <span data-ttu-id="73291-120">"Run with PowerShell" ist von keiner anderen Ausführungs Richtlinie betroffen.</span><span class="sxs-lookup"><span data-stu-id="73291-120">"Run with PowerShell" is not affected by any other execution policy.</span></span> <span data-ttu-id="73291-121">Weitere Informationen finden Sie unter [about_Execution_Policies](about_Execution_Policies.md).</span><span class="sxs-lookup"><span data-stu-id="73291-121">For more information, see [about_Execution_Policies](about_Execution_Policies.md).</span></span>

<span data-ttu-id="73291-122">Hinweis zur Problembehandlung: Wenn Sie mit PowerShell ausführen, werden Sie möglicherweise zur Bestätigung der Änderung der Ausführungs Richtlinie aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="73291-122">Troubleshooting Note: Run with PowerShell command might prompt you to confirm the execution policy change.</span></span>

## <a name="see-also"></a><span data-ttu-id="73291-123">SIEHE AUCH</span><span class="sxs-lookup"><span data-stu-id="73291-123">SEE ALSO</span></span>

[<span data-ttu-id="73291-124">about_Execution_Policies</span><span class="sxs-lookup"><span data-stu-id="73291-124">about_Execution_Policies</span></span>](about_Execution_Policies.md)

[<span data-ttu-id="73291-125">about_Group_Policy_Settings</span><span class="sxs-lookup"><span data-stu-id="73291-125">about_Group_Policy_Settings</span></span>](about_Group_Policy_Settings.md)

[<span data-ttu-id="73291-126">about_Scripts</span><span class="sxs-lookup"><span data-stu-id="73291-126">about_Scripts</span></span>](about_Scripts.md)
