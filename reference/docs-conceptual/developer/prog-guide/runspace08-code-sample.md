---
ms.date: 09/13/2016
ms.topic: reference
title: RunSpace08-Codebeispiel
description: RunSpace08-Codebeispiel
ms.openlocfilehash: f8d08e5b6bbd98d0901abe5b05c8b9ee682b8e04
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92654231"
---
# <a name="runspace08-code-sample"></a><span data-ttu-id="4f489-103">RunSpace08-Codebeispiel</span><span class="sxs-lookup"><span data-stu-id="4f489-103">RunSpace08 Code Sample</span></span>

<span data-ttu-id="4f489-104">Im folgenden finden Sie den Quellcode für das Runspace08-Beispiel [, das unter Erstellen einer Konsolenanwendung beschrieben wird, mit der einem Befehl Parameter hinzugefügt](https://msdn.microsoft.com/848b2b46-60f1-4a86-b448-cfc7c0cccfba)werden.</span><span class="sxs-lookup"><span data-stu-id="4f489-104">Here is the source code for the Runspace08 sample described in [Creating a Console Application That Adds Parameters to a Command](https://msdn.microsoft.com/848b2b46-60f1-4a86-b448-cfc7c0cccfba).</span></span>
<span data-ttu-id="4f489-105">In dieser Beispielanwendung wird ein Runspace erstellt, eine Pipeline erstellt, zwei Befehle zur Pipeline hinzugefügt, dem zweiten Befehl werden zwei Parameter hinzugefügt, und anschließend wird die Pipeline ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="4f489-105">This sample application creates a runspace, creates a pipeline, adds two commands to the pipeline, adds two parameters to the second command, and then executes the pipeline.</span></span> <span data-ttu-id="4f489-106">Die Befehle, die der Pipeline hinzugefügt werden, sind die `Get-Process` `Sort-Object` Cmdlets und.</span><span class="sxs-lookup"><span data-stu-id="4f489-106">The commands that are added to the pipeline are the `Get-Process` and `Sort-Object` cmdlets.</span></span>

## <a name="code-sample"></a><span data-ttu-id="4f489-107">Codebeispiel</span><span class="sxs-lookup"><span data-stu-id="4f489-107">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/Runspace08/Runspace08.cs" range="11-86":::

## <a name="see-also"></a><span data-ttu-id="4f489-108">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4f489-108">See Also</span></span>

[<span data-ttu-id="4f489-109">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="4f489-109">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
