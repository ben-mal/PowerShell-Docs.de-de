---
ms.date: 09/13/2016
ms.topic: reference
title: GetProc01-Codebeispiel (VB.NET)
description: GetProc01-Codebeispiel (VB.NET)
ms.openlocfilehash: c042b926615e4c88004d50841f25795ceec9aa2d
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92654458"
---
# <a name="getproc01-vbnet-sample-code"></a><span data-ttu-id="c1e53-103">GetProc01-Codebeispiel (VB.NET)</span><span class="sxs-lookup"><span data-stu-id="c1e53-103">GetProc01 (VB.NET) Sample Code</span></span>

<span data-ttu-id="c1e53-104">Der folgende Code zeigt die Implementierung des GetProc01-Beispiel-Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="c1e53-104">The following code shows the implementation of the GetProc01 sample cmdlet.</span></span> <span data-ttu-id="c1e53-105">Beachten Sie, dass das Cmdlet vereinfacht wird, indem Sie die tatsächliche Prozess Abruf Funktion an die [System. Diagnostics. Process. GetProcesses \*](/dotnet/api/System.Diagnostics.Process.GetProcesses) -Methode überlassen.</span><span class="sxs-lookup"><span data-stu-id="c1e53-105">Notice that the cmdlet is simplified by leaving the actual work of process retrieval to the [System.Diagnostics.Process.Getprocesses\*](/dotnet/api/System.Diagnostics.Process.GetProcesses) method.</span></span>

> [!NOTE]
> <span data-ttu-id="c1e53-106">Sie können die c#-Quelldatei (getproc01.cs) für dieses Get-Proc-Cmdlet mit dem Microsoft Windows Software Development Kit für Windows Vista und .NET Framework 3,0-Laufzeitkomponenten herunterladen.</span><span class="sxs-lookup"><span data-stu-id="c1e53-106">You can download the C# source file (getproc01.cs) for this Get-Proc cmdlet using the Microsoft Windows Software Development Kit for Windows Vista and .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="c1e53-107">Anweisungen zum Herunterladen finden Sie unter [Installieren von Windows PowerShell und Herunterladen des Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="c1e53-107">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
>
> <span data-ttu-id="c1e53-108">Die heruntergeladenen Quelldateien sind im **\<PowerShell Samples>** Verzeichnis verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c1e53-108">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="c1e53-109">Codebeispiel</span><span class="sxs-lookup"><span data-stu-id="c1e53-109">Code Sample</span></span>

<!-- TODO!!!: review snippet reference  [!CODE [msh_samplesgetproc01#getproc01vball](msh_samplesgetproc01#getproc01vball)]  -->

## <a name="see-also"></a><span data-ttu-id="c1e53-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c1e53-110">See Also</span></span>

[<span data-ttu-id="c1e53-111">Windows PowerShell-Programmiererhandbuch</span><span class="sxs-lookup"><span data-stu-id="c1e53-111">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="c1e53-112">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="c1e53-112">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
