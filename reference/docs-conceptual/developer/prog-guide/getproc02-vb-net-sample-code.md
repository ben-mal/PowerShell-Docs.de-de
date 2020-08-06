---
title: GetProc02 (VB.net)-Beispiel Code | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 98261f2d6678e24bb8e8df6d2c8a405b25203364
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787171"
---
# <a name="getproc02-vbnet-sample-code"></a><span data-ttu-id="9c69c-102">GetProc02-Codebeispiel (VB.NET)</span><span class="sxs-lookup"><span data-stu-id="9c69c-102">GetProc02 (VB.NET) Sample Code</span></span>

<span data-ttu-id="9c69c-103">Der folgende Code zeigt die Implementierung eines `Get-Process` Cmdlets, das Befehlszeilen Eingaben akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="9c69c-103">The following code shows the implementation of a `Get-Process` cmdlet that accepts command-line input.</span></span> <span data-ttu-id="9c69c-104">Beachten Sie, dass diese Implementierung einen `Name` Parameter definiert, um Befehlszeilen Eingaben zuzulassen, und die Methode " [Write Object" (System. Object, System. Boolean)](/dotnet/api/system.management.automation.cmdlet.writeobject?view=pscore-6.2.0#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_) als Ausgabe Mechanismus zum Senden von Ausgabe Objekten an die Pipeline verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="9c69c-104">Notice that this implementation defines a `Name` parameter to allow command-line input, and it uses the [WriteObject(System.Object,System.Boolean)](/dotnet/api/system.management.automation.cmdlet.writeobject?view=pscore-6.2.0#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_) method as the output mechanism for sending output objects to the pipeline.</span></span>

## <a name="code-sample"></a><span data-ttu-id="9c69c-105">Codebeispiel</span><span class="sxs-lookup"><span data-stu-id="9c69c-105">Code Sample</span></span>

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplesgetproc02#getproc02vball](Msh_samplesgetproc02#getproc02vball)]  -->

## <a name="see-also"></a><span data-ttu-id="9c69c-106">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9c69c-106">See Also</span></span>

[<span data-ttu-id="9c69c-107">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="9c69c-107">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
