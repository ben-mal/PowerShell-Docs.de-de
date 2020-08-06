---
title: Runspace01 (c#)-Code Beispiel | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 418162731b4a98989642e1c61c655fdb0f002698
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787054"
---
# <a name="runspace01-c-code-sample"></a><span data-ttu-id="5d36c-102">Runspace01-Codebeispiel (C#)</span><span class="sxs-lookup"><span data-stu-id="5d36c-102">Runspace01 (C#) Code Sample</span></span>

<span data-ttu-id="5d36c-103">Im folgenden finden Sie die Codebeispiele für den Runspace [, der unter Erstellen einer Konsolenanwendung beschrieben wird, die einen angegebenen Befehl ausführt](/dotnet/csharp/programming-guide/inside-a-program/hello-world-your-first-program).</span><span class="sxs-lookup"><span data-stu-id="5d36c-103">Here are the code samples for the runspace described in [Creating a Console Application That Runs a Specified Command](/dotnet/csharp/programming-guide/inside-a-program/hello-world-your-first-program).</span></span>
<span data-ttu-id="5d36c-104">Hierzu ruft die Anwendung einen Runspace auf und ruft dann einen Befehl auf.</span><span class="sxs-lookup"><span data-stu-id="5d36c-104">To do this, the application invokes a runspace, and then invokes a command.</span></span> <span data-ttu-id="5d36c-105">(Beachten Sie, dass diese Anwendung keine Informationen zur Runspace-Konfiguration angibt und keine Pipeline explizit erstellt).</span><span class="sxs-lookup"><span data-stu-id="5d36c-105">(Note that this application does not specify runspace configuration information, nor does it explicitly create a pipeline).</span></span> <span data-ttu-id="5d36c-106">Der Befehl, der aufgerufen wird, ist das `Get-Process` Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="5d36c-106">The command that is invoked is the `Get-Process` cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="5d36c-107">Sie können die c#-Quelldatei (runspace01.cs) für diesen Runspace mithilfe der Laufzeitkomponenten Microsoft Windows Software Development Kit für Windows Vista und Microsoft .NET Framework 3,0 herunterladen.</span><span class="sxs-lookup"><span data-stu-id="5d36c-107">You can download the C# source file (runspace01.cs) for this runspace using the Microsoft Windows Software Development Kit for Windows Vista and Microsoft .NET Framework 3.0 Runtime Components.</span></span>
> <span data-ttu-id="5d36c-108">Anweisungen zum Herunterladen finden Sie unter [Installieren von Windows PowerShell und Herunterladen des Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="5d36c-108">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
> <span data-ttu-id="5d36c-109">Die heruntergeladenen Quelldateien sind im **\<PowerShell Samples>** Verzeichnis verfügbar.</span><span class="sxs-lookup"><span data-stu-id="5d36c-109">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="5d36c-110">Codebeispiel</span><span class="sxs-lookup"><span data-stu-id="5d36c-110">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/Runspace01/Runspace01.cs" range="11-62":::

## <a name="see-also"></a><span data-ttu-id="5d36c-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5d36c-111">See Also</span></span>

[<span data-ttu-id="5d36c-112">Windows PowerShell-Programmiererhandbuch</span><span class="sxs-lookup"><span data-stu-id="5d36c-112">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="5d36c-113">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="5d36c-113">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
