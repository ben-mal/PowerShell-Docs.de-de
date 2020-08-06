---
title: RunSpace08-Code Beispiel | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 67172a0f8d6daf2f5b9965d1a18f7698daddbe1a
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784689"
---
# <a name="runspace08-code-sample"></a><span data-ttu-id="39fdd-102">RunSpace08-Codebeispiel</span><span class="sxs-lookup"><span data-stu-id="39fdd-102">RunSpace08 Code Sample</span></span>

<span data-ttu-id="39fdd-103">Im folgenden finden Sie den Quellcode für das Runspace08-Beispiel [, das unter Erstellen einer Konsolenanwendung beschrieben wird, mit der einem Befehl Parameter hinzugefügt](https://msdn.microsoft.com/848b2b46-60f1-4a86-b448-cfc7c0cccfba)werden.</span><span class="sxs-lookup"><span data-stu-id="39fdd-103">Here is the source code for the Runspace08 sample described in [Creating a Console Application That Adds Parameters to a Command](https://msdn.microsoft.com/848b2b46-60f1-4a86-b448-cfc7c0cccfba).</span></span>
<span data-ttu-id="39fdd-104">In dieser Beispielanwendung wird ein Runspace erstellt, eine Pipeline erstellt, zwei Befehle zur Pipeline hinzugefügt, dem zweiten Befehl werden zwei Parameter hinzugefügt, und anschließend wird die Pipeline ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="39fdd-104">This sample application creates a runspace, creates a pipeline, adds two commands to the pipeline, adds two parameters to the second command, and then executes the pipeline.</span></span> <span data-ttu-id="39fdd-105">Die Befehle, die der Pipeline hinzugefügt werden, sind die `Get-Process` `Sort-Object` Cmdlets und.</span><span class="sxs-lookup"><span data-stu-id="39fdd-105">The commands that are added to the pipeline are the `Get-Process` and `Sort-Object` cmdlets.</span></span>

## <a name="code-sample"></a><span data-ttu-id="39fdd-106">Codebeispiel</span><span class="sxs-lookup"><span data-stu-id="39fdd-106">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/Runspace08/Runspace08.cs" range="11-86":::

## <a name="see-also"></a><span data-ttu-id="39fdd-107">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="39fdd-107">See Also</span></span>

[<span data-ttu-id="39fdd-108">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="39fdd-108">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
