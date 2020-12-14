---
ms.date: 09/13/2016
ms.topic: reference
title: GetProc02-Codebeispiel (C#)
description: GetProc02-Codebeispiel (C#)
ms.openlocfilehash: 17fd0d0c0829ed21ef955fd2e62e9ee089d62190
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "93355611"
---
# <a name="getproc02-c-sample-code"></a><span data-ttu-id="69148-103">GetProc02-Codebeispiel (C#)</span><span class="sxs-lookup"><span data-stu-id="69148-103">GetProc02 (C#) Sample Code</span></span>

<span data-ttu-id="69148-104">Der folgende Code zeigt die Implementierung eines `Get-Process` Cmdlets, das Befehlszeilen Eingaben akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="69148-104">The following code shows the implementation of a `Get-Process` cmdlet that accepts command-line input.</span></span> <span data-ttu-id="69148-105">Beachten Sie, dass diese Implementierung einen `Name` Parameter definiert, um Befehlszeilen Eingaben zuzulassen, und die Methode " [Write Object" (System. Object, System. Boolean)](/dotnet/api/system.management.automation.cmdlet.writeobject#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_) als Ausgabe Mechanismus zum Senden von Ausgabe Objekten an die Pipeline verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="69148-105">Notice that this implementation defines a `Name` parameter to allow command-line input, and it uses the [WriteObject(System.Object,System.Boolean)](/dotnet/api/system.management.automation.cmdlet.writeobject#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_) method as the output mechanism for sending output objects to the pipeline.</span></span>

## <a name="code-sample"></a><span data-ttu-id="69148-106">Codebeispiel</span><span class="sxs-lookup"><span data-stu-id="69148-106">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/GetProcessSample02/GetProcessSample02.cs" range="11-76":::

## <a name="see-also"></a><span data-ttu-id="69148-107">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="69148-107">See Also</span></span>

[<span data-ttu-id="69148-108">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="69148-108">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
