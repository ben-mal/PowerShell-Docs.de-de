---
title: GetProc04 (VB.net)-Beispiel Code | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 63fbbb2d6bef4634bf72d4b0f9e429de9ed9deca
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87771871"
---
# <a name="getproc04-vbnet-sample-code"></a><span data-ttu-id="03bd0-102">GetProc04-Codebeispiel (VB.NET)</span><span class="sxs-lookup"><span data-stu-id="03bd0-102">GetProc04 (VB.NET) Sample Code</span></span>

<span data-ttu-id="03bd0-103">Der folgende Code zeigt die Implementierung eines `Get-Process` Cmdlets, das nicht abschließende Fehler meldet.</span><span class="sxs-lookup"><span data-stu-id="03bd0-103">The following code shows the implementation of a `Get-Process` cmdlet that reports nonterminating errors.</span></span> <span data-ttu-id="03bd0-104">Diese Implementierung ruft die [System. Management. Automation. Cmdlet. Write error](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) -Methode auf, um nicht abschließende Fehler zu melden.</span><span class="sxs-lookup"><span data-stu-id="03bd0-104">This implementation calls the [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) method to report nonterminating errors.</span></span>

> [!NOTE]
> <span data-ttu-id="03bd0-105">Sie können die c#-Quelldatei (getprov04.cs) für dieses Get-proc-Cmdlet mit dem Microsoft Windows Software Development Kit für Windows Vista und .NET Framework 3,0-Laufzeitkomponenten herunterladen.</span><span class="sxs-lookup"><span data-stu-id="03bd0-105">You can download the C# source file (getprov04.cs) for this Get-Proc cmdlet using the Microsoft Windows Software Development Kit for Windows Vista and .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="03bd0-106">Anweisungen zum Herunterladen finden Sie unter [Installieren von Windows PowerShell und Herunterladen des Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="03bd0-106">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
>
> <span data-ttu-id="03bd0-107">Die heruntergeladenen Quelldateien sind im **\<PowerShell Samples>** Verzeichnis verfügbar.</span><span class="sxs-lookup"><span data-stu-id="03bd0-107">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="03bd0-108">Codebeispiel</span><span class="sxs-lookup"><span data-stu-id="03bd0-108">Code Sample</span></span>

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplesgetproc04#GetProc04vball](Msh_samplesgetproc04#GetProc04vball)]  -->

## <a name="see-also"></a><span data-ttu-id="03bd0-109">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="03bd0-109">See Also</span></span>

[<span data-ttu-id="03bd0-110">Windows PowerShell-Programmiererhandbuch</span><span class="sxs-lookup"><span data-stu-id="03bd0-110">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="03bd0-111">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="03bd0-111">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
