---
title: RunSpace05-Code Beispiel | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 31a73f965a6e38dceec740a2f7d4adead3e2a3f9
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784740"
---
# <a name="runspace05-code-sample"></a><span data-ttu-id="5143e-102">RunSpace05-Codebeispiel</span><span class="sxs-lookup"><span data-stu-id="5143e-102">RunSpace05 Code Sample</span></span>

<span data-ttu-id="5143e-103">Im folgenden finden Sie den Quellcode für das Runspace05-Beispiel, das unter [Konfigurieren eines Runspace mithilfe von runspaceconfiguration](https://msdn.microsoft.com/42681d19-2d05-4975-befd-afb1990e79b2)beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="5143e-103">Here is the source code for the Runspace05 sample that is described in [Configuring a Runspace Using RunspaceConfiguration](https://msdn.microsoft.com/42681d19-2d05-4975-befd-afb1990e79b2).</span></span>
<span data-ttu-id="5143e-104">Dieses Beispiel zeigt, wie Sie die Runspace-Konfigurationsinformationen erstellen, einen Runspace erstellen, eine Pipeline mit einem einzelnen Befehl erstellen und dann die Pipeline ausführen.</span><span class="sxs-lookup"><span data-stu-id="5143e-104">This sample shows how to create the runspace configuration information, create a runspace, create a pipeline with a single command, and then execute the pipeline.</span></span> <span data-ttu-id="5143e-105">Der Befehl, der ausgeführt wird, ist das `Get-Process` Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="5143e-105">The command that is executed is the `Get-Process` cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="5143e-106">Sie können die c#-Quelldatei (runspace05.cs) herunterladen, indem Sie die Laufzeitkomponenten Microsoft Windows Software Development Kit für Windows Vista und Microsoft .NET Framework 3,0 verwenden.</span><span class="sxs-lookup"><span data-stu-id="5143e-106">You can download the C# source file (runspace05.cs) by using the Microsoft Windows Software Development Kit for Windows Vista and Microsoft .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="5143e-107">Anweisungen zum Herunterladen finden Sie unter [Installieren von Windows PowerShell und Herunterladen des Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="5143e-107">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
> <span data-ttu-id="5143e-108">Die heruntergeladenen Quelldateien sind im **\<PowerShell Samples>** Verzeichnis verfügbar.</span><span class="sxs-lookup"><span data-stu-id="5143e-108">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="5143e-109">Codebeispiel</span><span class="sxs-lookup"><span data-stu-id="5143e-109">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/Runspace05/Runspace05.cs" range="11-86":::

## <a name="see-also"></a><span data-ttu-id="5143e-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5143e-110">See Also</span></span>

[<span data-ttu-id="5143e-111">Windows PowerShell-Programmiererhandbuch</span><span class="sxs-lookup"><span data-stu-id="5143e-111">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="5143e-112">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="5143e-112">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
