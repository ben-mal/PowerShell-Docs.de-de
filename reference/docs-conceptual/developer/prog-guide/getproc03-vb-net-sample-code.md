---
title: GetProc03 (VB.net)-Beispiel Code | Microsoft-Dokumentation
ms.date: 09/12/2016
ms.openlocfilehash: ad8a7b13d30b77acdaa2f5365b9b2da02aaeedce
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87771922"
---
# <a name="getproc03-vbnet-sample-code"></a><span data-ttu-id="7c30a-102">GetProc03-Codebeispiel (VB.NET)</span><span class="sxs-lookup"><span data-stu-id="7c30a-102">GetProc03 (VB.NET) Sample Code</span></span>

<span data-ttu-id="7c30a-103">Der folgende Code zeigt die Implementierung eines `Get-Process` Cmdlets, das Pipeline Eingaben akzeptieren kann.</span><span class="sxs-lookup"><span data-stu-id="7c30a-103">The following code shows the implementation of a `Get-Process` cmdlet that can accept pipelined input.</span></span> <span data-ttu-id="7c30a-104">Diese Implementierung definiert einen `Name` Parameter, der Pipeline Eingaben annimmt, Prozessinformationen vom lokalen Computer auf der Grundlage der angegebenen Namen abruft und dann die Methode " [Write Object" (System. Object, System. Boolean)](/dotnet/api/system.management.automation.cmdlet.writeobject?view=pscore-6.2.0#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_) als Ausgabe Mechanismus zum Senden von Objekten an die Pipeline verwendet.</span><span class="sxs-lookup"><span data-stu-id="7c30a-104">This implementation defines a `Name` parameter that accepts pipeline input, retrieves process information from the local computer based on the supplied names, and then uses the [WriteObject(System.Object,System.Boolean)](/dotnet/api/system.management.automation.cmdlet.writeobject?view=pscore-6.2.0#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_) method as the output mechanism for sending objects to the pipeline.</span></span>

## <a name="code-sample"></a><span data-ttu-id="7c30a-105">Codebeispiel</span><span class="sxs-lookup"><span data-stu-id="7c30a-105">Code Sample</span></span>

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplesgetproc03#getproc03vbAll](Msh_samplesgetproc03#getproc03vbAll)]  -->
