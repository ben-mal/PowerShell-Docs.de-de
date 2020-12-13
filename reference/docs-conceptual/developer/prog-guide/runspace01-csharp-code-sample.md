---
ms.date: 09/13/2016
ms.topic: reference
title: Runspace01-Codebeispiel (C#)
description: Runspace01-Codebeispiel (C#)
ms.openlocfilehash: e6121c144e1a4c1a1d9460d01119f44ee5835821
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92657144"
---
# <a name="runspace01-c-code-sample"></a><span data-ttu-id="d5a56-103">Runspace01-Codebeispiel (C#)</span><span class="sxs-lookup"><span data-stu-id="d5a56-103">Runspace01 (C#) Code Sample</span></span>

<span data-ttu-id="d5a56-104">Im folgenden finden Sie die Codebeispiele für den Runspace [, der unter Erstellen einer Konsolenanwendung beschrieben wird, die einen angegebenen Befehl ausführt](/dotnet/csharp/programming-guide/inside-a-program/hello-world-your-first-program).</span><span class="sxs-lookup"><span data-stu-id="d5a56-104">Here are the code samples for the runspace described in [Creating a Console Application That Runs a Specified Command](/dotnet/csharp/programming-guide/inside-a-program/hello-world-your-first-program).</span></span>
<span data-ttu-id="d5a56-105">Hierzu ruft die Anwendung einen Runspace auf und ruft dann einen Befehl auf.</span><span class="sxs-lookup"><span data-stu-id="d5a56-105">To do this, the application invokes a runspace, and then invokes a command.</span></span> <span data-ttu-id="d5a56-106">(Beachten Sie, dass diese Anwendung keine Informationen zur Runspace-Konfiguration angibt und keine Pipeline explizit erstellt).</span><span class="sxs-lookup"><span data-stu-id="d5a56-106">(Note that this application does not specify runspace configuration information, nor does it explicitly create a pipeline).</span></span> <span data-ttu-id="d5a56-107">Der Befehl, der aufgerufen wird, ist das `Get-Process` Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d5a56-107">The command that is invoked is the `Get-Process` cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="d5a56-108">Sie können die c#-Quelldatei (runspace01.cs) für diesen Runspace mithilfe der Laufzeitkomponenten Microsoft Windows Software Development Kit für Windows Vista und Microsoft .NET Framework 3,0 herunterladen.</span><span class="sxs-lookup"><span data-stu-id="d5a56-108">You can download the C# source file (runspace01.cs) for this runspace using the Microsoft Windows Software Development Kit for Windows Vista and Microsoft .NET Framework 3.0 Runtime Components.</span></span>
> <span data-ttu-id="d5a56-109">Anweisungen zum Herunterladen finden Sie unter [Installieren von Windows PowerShell und Herunterladen des Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="d5a56-109">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
> <span data-ttu-id="d5a56-110">Die heruntergeladenen Quelldateien sind im **\<PowerShell Samples>** Verzeichnis verfügbar.</span><span class="sxs-lookup"><span data-stu-id="d5a56-110">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="d5a56-111">Codebeispiel</span><span class="sxs-lookup"><span data-stu-id="d5a56-111">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/Runspace01/Runspace01.cs" range="11-62":::

## <a name="see-also"></a><span data-ttu-id="d5a56-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d5a56-112">See Also</span></span>

[<span data-ttu-id="d5a56-113">Windows PowerShell-Programmiererhandbuch</span><span class="sxs-lookup"><span data-stu-id="d5a56-113">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="d5a56-114">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="d5a56-114">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
