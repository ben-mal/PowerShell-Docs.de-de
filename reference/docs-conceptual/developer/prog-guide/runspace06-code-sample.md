---
ms.date: 09/13/2016
ms.topic: reference
title: RunSpace06-Codebeispiel
description: RunSpace06-Codebeispiel
ms.openlocfilehash: 627fa2be51721dd8bfdd63fabdd2e6f286d593be
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667475"
---
# <a name="runspace06-code-sample"></a><span data-ttu-id="f6e38-103">RunSpace06-Codebeispiel</span><span class="sxs-lookup"><span data-stu-id="f6e38-103">RunSpace06 Code Sample</span></span>

<span data-ttu-id="f6e38-104">Im folgenden finden Sie den Quellcode für das Runspace06-Beispiel, das unter [Konfigurieren eines Runspace mithilfe eines Windows PowerShell-Snap-Ins](https://msdn.microsoft.com/a7289ee8-9732-49ee-91c7-d533e9538b83)beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="f6e38-104">Here is the source code for the Runspace06 sample described in [Configuring a Runspace Using a Windows PowerShell Snap-in](https://msdn.microsoft.com/a7289ee8-9732-49ee-91c7-d533e9538b83).</span></span>
<span data-ttu-id="f6e38-105">Diese Beispielanwendung erstellt einen Runspace auf Grundlage eines Windows PowerShell-Snap-Ins, das dann verwendet wird, um eine Pipeline mit einem einzigen Befehl auszuführen.</span><span class="sxs-lookup"><span data-stu-id="f6e38-105">This sample application creates a runspace based on a Windows PowerShell snap-in, which is then used to run a pipeline with a single command.</span></span> <span data-ttu-id="f6e38-106">Zu diesem Zweck erstellt die Anwendung die Runspace-Konfigurationsinformationen, erstellt einen Runspace, erstellt eine Pipeline mit einem einzigen Befehl und führt dann die Pipeline aus.</span><span class="sxs-lookup"><span data-stu-id="f6e38-106">To do this, the application creates the runspace configuration information, creates a runspace, creates a pipeline with a single command, and then executes the pipeline.</span></span>

> [!NOTE]
> <span data-ttu-id="f6e38-107">Sie können die c#-Quelldatei (runspace06.cs) mit dem Windows Software Development Kit für Windows Vista und Microsoft .NET Framework 3,0-Laufzeitkomponenten herunterladen.</span><span class="sxs-lookup"><span data-stu-id="f6e38-107">You can download the C# source file (runspace06.cs) by using the Windows Software Development Kit for Windows Vista and Microsoft .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="f6e38-108">Anweisungen zum Herunterladen finden Sie unter [Installieren von Windows PowerShell und Herunterladen des Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="f6e38-108">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
> <span data-ttu-id="f6e38-109">Die heruntergeladenen Quelldateien sind im **\<PowerShell Samples>** Verzeichnis verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f6e38-109">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="f6e38-110">Codebeispiel</span><span class="sxs-lookup"><span data-stu-id="f6e38-110">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/Runspace06/Runspace06.cs" range="11-85":::

## <a name="see-also"></a><span data-ttu-id="f6e38-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f6e38-111">See Also</span></span>

[<span data-ttu-id="f6e38-112">Windows PowerShell-Programmiererhandbuch</span><span class="sxs-lookup"><span data-stu-id="f6e38-112">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="f6e38-113">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="f6e38-113">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
