---
title: RunSpace07-Code Beispiel | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 615bb237d26bf3a314ea7fb21e983ba2b000d105
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784706"
---
# <a name="runspace07-code-sample"></a><span data-ttu-id="a52fa-102">RunSpace07-Codebeispiel</span><span class="sxs-lookup"><span data-stu-id="a52fa-102">RunSpace07 Code Sample</span></span>

<span data-ttu-id="a52fa-103">Im folgenden finden Sie den Quellcode für das Runspace07-Beispiel [, das unter Erstellen einer Konsolenanwendung beschrieben wird, mit der einer Pipeline Befehle hinzugefügt](https://msdn.microsoft.com/01eb7808-e97b-4905-80be-9e2fa38c262e)werden.</span><span class="sxs-lookup"><span data-stu-id="a52fa-103">Here is the source code for the Runspace07 sample described in [Creating a Console Application That Adds Commands to a Pipeline](https://msdn.microsoft.com/01eb7808-e97b-4905-80be-9e2fa38c262e).</span></span>
<span data-ttu-id="a52fa-104">Diese Beispielanwendung erstellt einen Runspace, erstellt eine Pipeline, fügt der Pipeline zwei Befehle hinzu und führt dann die Pipeline aus.</span><span class="sxs-lookup"><span data-stu-id="a52fa-104">This sample application creates a runspace, creates a pipeline, adds two commands to the pipeline, and then executes the pipeline.</span></span> <span data-ttu-id="a52fa-105">Die Befehle, die der Pipeline hinzugefügt werden, sind die `Get-Process` `Measure-Object` Cmdlets und.</span><span class="sxs-lookup"><span data-stu-id="a52fa-105">The commands added to the pipeline are the `Get-Process` and `Measure-Object` cmdlets.</span></span>

> [!NOTE]
> <span data-ttu-id="a52fa-106">Sie können die c#-Quelldatei (runspace07.cs) unter Verwendung der Laufzeitkomponenten Microsoft Windows Software Development Kit für Windows Vista und Microsoft .NET Framework 3,0 herunterladen.</span><span class="sxs-lookup"><span data-stu-id="a52fa-106">You can download the C# source file (runspace07.cs) using the Microsoft Windows Software Development Kit for Windows Vista and Microsoft .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="a52fa-107">Anweisungen zum Herunterladen finden Sie unter [Installieren von Windows PowerShell und Herunterladen des Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="a52fa-107">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
> <span data-ttu-id="a52fa-108">Die heruntergeladenen Quelldateien sind im **\<PowerShell Samples>** Verzeichnis verfügbar.</span><span class="sxs-lookup"><span data-stu-id="a52fa-108">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="a52fa-109">Codebeispiel</span><span class="sxs-lookup"><span data-stu-id="a52fa-109">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/Runspace07/Runspace07.cs" range="11-108":::

## <a name="see-also"></a><span data-ttu-id="a52fa-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a52fa-110">See Also</span></span>

[<span data-ttu-id="a52fa-111">Windows PowerShell-Programmiererhandbuch</span><span class="sxs-lookup"><span data-stu-id="a52fa-111">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="a52fa-112">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="a52fa-112">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
