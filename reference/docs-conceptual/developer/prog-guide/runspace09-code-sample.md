---
title: RunSpace09-Code Beispiel | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: fc5d8d4d182cca6bfc42d63c68a14a7a5e5f9c97
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784672"
---
# <a name="runspace09-code-sample"></a><span data-ttu-id="315c2-102">RunSpace09-Codebeispiel</span><span class="sxs-lookup"><span data-stu-id="315c2-102">RunSpace09 Code Sample</span></span>

<span data-ttu-id="315c2-103">Im folgenden finden Sie den Quellcode für das Runspace09-Beispiel [, das unter Erstellen einer Konsolenanwendung beschrieben wird, die eine Pipeline asynchron](https://msdn.microsoft.com/198c1c94-2a06-457e-93ce-c0d910618e47)aufruft.</span><span class="sxs-lookup"><span data-stu-id="315c2-103">Here is the source code for the Runspace09 sample described in [Creating a Console Application That Invokes a Pipeline Asynchronously](https://msdn.microsoft.com/198c1c94-2a06-457e-93ce-c0d910618e47).</span></span>
<span data-ttu-id="315c2-104">Diese Beispielanwendung erstellt und öffnet einen Runspace, erstellt eine Pipeline und ruft Sie asynchron auf und verwendet dann Pipeline Ereignisse, um das Skript asynchron zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="315c2-104">This sample application creates and opens a runspace, creates and asynchronously invokes a pipeline, and then uses pipeline events to process the script asynchronously.</span></span> <span data-ttu-id="315c2-105">Das Skript, das von dieser Anwendung ausgeführt wird, erstellt die ganzen Zahlen 1 bis 10 in Intervallen von 0,5 Sekunden (500 ms).</span><span class="sxs-lookup"><span data-stu-id="315c2-105">The script that is run by this application creates the integers 1 through 10 in 0.5-second intervals (500 ms).</span></span>

## <a name="code-sample"></a><span data-ttu-id="315c2-106">Codebeispiel</span><span class="sxs-lookup"><span data-stu-id="315c2-106">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/Runspace09/Runspace09.cs" range="11-113":::

## <a name="see-also"></a><span data-ttu-id="315c2-107">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="315c2-107">See Also</span></span>

[<span data-ttu-id="315c2-108">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="315c2-108">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
