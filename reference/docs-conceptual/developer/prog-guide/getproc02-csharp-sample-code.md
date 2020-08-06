---
title: GetProc02 (c#)-Beispiel Code | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: d9afa8fff23d99661987c067e8082a9294c12717
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787154"
---
# <a name="getproc02-c-sample-code"></a><span data-ttu-id="a852a-102">GetProc02-Codebeispiel (C#)</span><span class="sxs-lookup"><span data-stu-id="a852a-102">GetProc02 (C#) Sample Code</span></span>

<span data-ttu-id="a852a-103">Der folgende Code zeigt die Implementierung eines `Get-Process` Cmdlets, das Befehlszeilen Eingaben akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="a852a-103">The following code shows the implementation of a `Get-Process` cmdlet that accepts command-line input.</span></span> <span data-ttu-id="a852a-104">Beachten Sie, dass diese Implementierung einen `Name` Parameter definiert, um Befehlszeilen Eingaben zuzulassen, und die Methode " [Write Object" (System. Object, System. Boolean)](/dotnet/api/system.management.automation.cmdlet.writeobject?view=pscore-6.2.0#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_) als Ausgabe Mechanismus zum Senden von Ausgabe Objekten an die Pipeline verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a852a-104">Notice that this implementation defines a `Name` parameter to allow command-line input, and it uses the [WriteObject(System.Object,System.Boolean)](/dotnet/api/system.management.automation.cmdlet.writeobject?view=pscore-6.2.0#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_) method as the output mechanism for sending output objects to the pipeline.</span></span>

## <a name="code-sample"></a><span data-ttu-id="a852a-105">Codebeispiel</span><span class="sxs-lookup"><span data-stu-id="a852a-105">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/GetProcessSample02/GetProcessSample02.cs" range="11-76":::

## <a name="see-also"></a><span data-ttu-id="a852a-106">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a852a-106">See Also</span></span>

[<span data-ttu-id="a852a-107">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="a852a-107">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
