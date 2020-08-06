---
title: GetProc04 (c#)-Beispiel Code | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: dd3965ee504641b1b629ba203090ee14c670da43
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87771888"
---
# <a name="getproc04-c-sample-code"></a><span data-ttu-id="817e6-102">GetProc04-Codebeispiel (C#)</span><span class="sxs-lookup"><span data-stu-id="817e6-102">GetProc04 (C#) Sample Code</span></span>

<span data-ttu-id="817e6-103">Der folgende Code zeigt die Implementierung eines `Get-Process` Cmdlets, das nicht abschließende Fehler meldet.</span><span class="sxs-lookup"><span data-stu-id="817e6-103">The following code shows the implementation of a `Get-Process` cmdlet that reports nonterminating errors.</span></span> <span data-ttu-id="817e6-104">Diese Implementierung ruft die [System. Management. Automation. Cmdlet. Write error](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) -Methode auf, um nicht abschließende Fehler zu melden.</span><span class="sxs-lookup"><span data-stu-id="817e6-104">This implementation calls the [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) method to report nonterminating errors.</span></span>

> [!NOTE]
> <span data-ttu-id="817e6-105">Sie können die c#-Quelldatei (getprov04.cs) für dieses Get-proc-Cmdlet mit dem Microsoft Windows Software Development Kit für Windows Vista und .NET Framework 3,0-Laufzeitkomponenten herunterladen.</span><span class="sxs-lookup"><span data-stu-id="817e6-105">You can download the C# source file (getprov04.cs) for this Get-Proc cmdlet using the Microsoft Windows Software Development Kit for Windows Vista and .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="817e6-106">Anweisungen zum Herunterladen finden Sie unter [Installieren von Windows PowerShell und Herunterladen des Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="817e6-106">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
> <span data-ttu-id="817e6-107">Die heruntergeladenen Quelldateien sind im **\<PowerShell Samples>** Verzeichnis verfügbar.</span><span class="sxs-lookup"><span data-stu-id="817e6-107">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="817e6-108">Codebeispiel</span><span class="sxs-lookup"><span data-stu-id="817e6-108">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/GetProcessSample04/GetProcessSample04.cs" range="11-98":::

## <a name="see-also"></a><span data-ttu-id="817e6-109">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="817e6-109">See Also</span></span>

[<span data-ttu-id="817e6-110">Windows PowerShell-Programmiererhandbuch</span><span class="sxs-lookup"><span data-stu-id="817e6-110">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="817e6-111">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="817e6-111">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
