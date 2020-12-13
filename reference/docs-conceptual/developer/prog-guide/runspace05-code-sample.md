---
ms.date: 09/13/2016
ms.topic: reference
title: RunSpace05-Codebeispiel
description: RunSpace05-Codebeispiel
ms.openlocfilehash: f128e09522bdb05cba2c160bce4944c829a5c108
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92654218"
---
# <a name="runspace05-code-sample"></a><span data-ttu-id="532be-103">RunSpace05-Codebeispiel</span><span class="sxs-lookup"><span data-stu-id="532be-103">RunSpace05 Code Sample</span></span>

<span data-ttu-id="532be-104">Im folgenden finden Sie den Quellcode für das Runspace05-Beispiel, das unter [Konfigurieren eines Runspace mithilfe von runspaceconfiguration](https://msdn.microsoft.com/42681d19-2d05-4975-befd-afb1990e79b2)beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="532be-104">Here is the source code for the Runspace05 sample that is described in [Configuring a Runspace Using RunspaceConfiguration](https://msdn.microsoft.com/42681d19-2d05-4975-befd-afb1990e79b2).</span></span>
<span data-ttu-id="532be-105">Dieses Beispiel zeigt, wie Sie die Runspace-Konfigurationsinformationen erstellen, einen Runspace erstellen, eine Pipeline mit einem einzelnen Befehl erstellen und dann die Pipeline ausführen.</span><span class="sxs-lookup"><span data-stu-id="532be-105">This sample shows how to create the runspace configuration information, create a runspace, create a pipeline with a single command, and then execute the pipeline.</span></span> <span data-ttu-id="532be-106">Der Befehl, der ausgeführt wird, ist das `Get-Process` Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="532be-106">The command that is executed is the `Get-Process` cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="532be-107">Sie können die c#-Quelldatei (runspace05.cs) herunterladen, indem Sie die Laufzeitkomponenten Microsoft Windows Software Development Kit für Windows Vista und Microsoft .NET Framework 3,0 verwenden.</span><span class="sxs-lookup"><span data-stu-id="532be-107">You can download the C# source file (runspace05.cs) by using the Microsoft Windows Software Development Kit for Windows Vista and Microsoft .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="532be-108">Anweisungen zum Herunterladen finden Sie unter [Installieren von Windows PowerShell und Herunterladen des Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="532be-108">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
> <span data-ttu-id="532be-109">Die heruntergeladenen Quelldateien sind im **\<PowerShell Samples>** Verzeichnis verfügbar.</span><span class="sxs-lookup"><span data-stu-id="532be-109">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="532be-110">Codebeispiel</span><span class="sxs-lookup"><span data-stu-id="532be-110">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/Runspace05/Runspace05.cs" range="11-86":::

## <a name="see-also"></a><span data-ttu-id="532be-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="532be-111">See Also</span></span>

[<span data-ttu-id="532be-112">Windows PowerShell-Programmiererhandbuch</span><span class="sxs-lookup"><span data-stu-id="532be-112">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="532be-113">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="532be-113">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
