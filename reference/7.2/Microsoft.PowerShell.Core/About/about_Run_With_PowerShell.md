---
description: Erläutert, wie Sie das Feature "mit PowerShell ausführen" verwenden, um ein Skript von einem Dateisystem Laufwerk auszuführen.
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_run_with_powershell?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Run_With_PowerShell
ms.openlocfilehash: 7070fa2bc8bb30e83f59e3d1193faa3a8495f109
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599644"
---
# <a name="about-run-with-powershell"></a><span data-ttu-id="672e8-103">Informationen zum Ausführen mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="672e8-103">About Run With PowerShell</span></span>

## <a name="short-description"></a><span data-ttu-id="672e8-104">KURZE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="672e8-104">SHORT DESCRIPTION</span></span>
<span data-ttu-id="672e8-105">Erläutert, wie Sie die Funktion "mit PowerShell ausführen" verwenden, um ein Skript von einem Dateisystem Laufwerk auszuführen.</span><span class="sxs-lookup"><span data-stu-id="672e8-105">Explains how to use the "Run with PowerShell" feature to run a script from a file system drive.</span></span>

## <a name="long-description"></a><span data-ttu-id="672e8-106">LANGE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="672e8-106">LONG DESCRIPTION</span></span>

<span data-ttu-id="672e8-107">Ab Windows PowerShell 3,0 können Sie die Funktion "mit PowerShell ausführen" verwenden, um Skripts aus dem Datei-Explorer in Windows 8 und Windows Server 2012 und aus Windows-Explorer in früheren Versionen von Windows auszuführen.</span><span class="sxs-lookup"><span data-stu-id="672e8-107">Beginning in Windows PowerShell 3.0, you can use the "Run with PowerShell" feature to run scripts from File Explorer in Windows 8 and Windows Server 2012 and from Windows Explorer in earlier versions of Windows.</span></span>

<span data-ttu-id="672e8-108">Die Funktion "mit PowerShell ausführen" dient zum Ausführen von Skripts, die nicht über erforderliche Parameter verfügen und keine Ausgabe an die Eingabeaufforderung zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="672e8-108">The "Run with PowerShell" feature is designed to run scripts that do not have required parameters and do not return output to the command prompt.</span></span>

<span data-ttu-id="672e8-109">Wenn Sie die Funktion "mit PowerShell ausführen" verwenden, wird das PowerShell-Konsolenfenster nur kurz angezeigt, wenn überhaupt.</span><span class="sxs-lookup"><span data-stu-id="672e8-109">When you use the "Run with PowerShell" feature, the PowerShell console window appears only briefly, if at all.</span></span> <span data-ttu-id="672e8-110">Es ist nicht möglich, mit ihm zu interagieren.</span><span class="sxs-lookup"><span data-stu-id="672e8-110">You cannot interact with it.</span></span>

<span data-ttu-id="672e8-111">So verwenden Sie die Funktion "mit PowerShell ausführen":</span><span class="sxs-lookup"><span data-stu-id="672e8-111">To use the "Run with PowerShell" feature:</span></span>

<span data-ttu-id="672e8-112">Klicken Sie im Datei-Explorer (oder Windows-Explorer) mit der rechten Maustaste auf den Namen der Skriptdatei, und wählen Sie dann die Option mit PowerShell ausführen aus.</span><span class="sxs-lookup"><span data-stu-id="672e8-112">In File Explorer (or Windows Explorer), right-click the script file name and then select "Run with PowerShell".</span></span>

<span data-ttu-id="672e8-113">Die Funktion "mit PowerShell ausführen" startet eine PowerShell-Sitzung mit der Ausführungs Richtlinie "Bypass", führt das Skript aus und schließt die Sitzung.</span><span class="sxs-lookup"><span data-stu-id="672e8-113">The "Run with PowerShell" feature starts a PowerShell session that has an execution policy of Bypass, runs the script, and closes the session.</span></span>

<span data-ttu-id="672e8-114">Er führt einen Befehl aus, der das folgende Format aufweist:</span><span class="sxs-lookup"><span data-stu-id="672e8-114">It runs a command that has the following format:</span></span>

```
PowerShell.exe -File <FileName> -ExecutionPolicy Bypass
```

<span data-ttu-id="672e8-115">"Mit PowerShell ausführen" legt die Umgehungs Ausführungs Richtlinie nur für die Sitzung (die aktuelle Instanz des PowerShell-Prozesses) fest, in der das Skript ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="672e8-115">"Run with PowerShell" sets the Bypass execution policy only for the session (the current instance of the PowerShell process) in which the script runs.</span></span>
<span data-ttu-id="672e8-116">Diese Funktion ändert nicht die Ausführungs Richtlinie für den Computer oder den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="672e8-116">This feature does not change the execution policy for the computer or the user.</span></span>

<span data-ttu-id="672e8-117">Die Funktion "mit PowerShell ausführen" ist nur durch die AllSigned-Ausführungs Richtlinie betroffen.</span><span class="sxs-lookup"><span data-stu-id="672e8-117">The "Run with PowerShell" feature is affected only by the AllSigned execution policy.</span></span> <span data-ttu-id="672e8-118">Wenn die AllSigned-Ausführungs Richtlinie für den Computer oder den Benutzer wirksam ist, führt "Run with PowerShell" nur signierte Skripts aus.</span><span class="sxs-lookup"><span data-stu-id="672e8-118">If the AllSigned execution policy is effective for the computer or the user, "Run with PowerShell" runs only signed scripts.</span></span> <span data-ttu-id="672e8-119">"Run with PowerShell" ist von keiner anderen Ausführungs Richtlinie betroffen.</span><span class="sxs-lookup"><span data-stu-id="672e8-119">"Run with PowerShell" is not affected by any other execution policy.</span></span> <span data-ttu-id="672e8-120">Weitere Informationen finden Sie unter [about_Execution_Policies](about_Execution_Policies.md).</span><span class="sxs-lookup"><span data-stu-id="672e8-120">For more information, see [about_Execution_Policies](about_Execution_Policies.md).</span></span>

<span data-ttu-id="672e8-121">Hinweis zur Problembehandlung: Wenn Sie mit PowerShell ausführen, werden Sie möglicherweise zur Bestätigung der Änderung der Ausführungs Richtlinie aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="672e8-121">Troubleshooting Note: Run with PowerShell command might prompt you to confirm the execution policy change.</span></span>

## <a name="see-also"></a><span data-ttu-id="672e8-122">SIEHE AUCH</span><span class="sxs-lookup"><span data-stu-id="672e8-122">SEE ALSO</span></span>

[<span data-ttu-id="672e8-123">about_Execution_Policies</span><span class="sxs-lookup"><span data-stu-id="672e8-123">about_Execution_Policies</span></span>](about_Execution_Policies.md)

[<span data-ttu-id="672e8-124">about_Group_Policy_Settings</span><span class="sxs-lookup"><span data-stu-id="672e8-124">about_Group_Policy_Settings</span></span>](about_Group_Policy_Settings.md)

[<span data-ttu-id="672e8-125">about_Scripts</span><span class="sxs-lookup"><span data-stu-id="672e8-125">about_Scripts</span></span>](about_Scripts.md)

