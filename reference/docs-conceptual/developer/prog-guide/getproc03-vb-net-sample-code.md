---
ms.date: 09/12/2016
ms.topic: reference
title: GetProc03-Codebeispiel (VB.NET)
description: GetProc03-Codebeispiel (VB.NET)
ms.openlocfilehash: fc70496178c85e101b380e68aacd64c8d1f350e9
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "93355560"
---
# <a name="getproc03-vbnet-sample-code"></a><span data-ttu-id="6b5c8-103">GetProc03-Codebeispiel (VB.NET)</span><span class="sxs-lookup"><span data-stu-id="6b5c8-103">GetProc03 (VB.NET) Sample Code</span></span>

<span data-ttu-id="6b5c8-104">Der folgende Code zeigt die Implementierung eines `Get-Process` Cmdlets, das Pipeline Eingaben akzeptieren kann.</span><span class="sxs-lookup"><span data-stu-id="6b5c8-104">The following code shows the implementation of a `Get-Process` cmdlet that can accept pipelined input.</span></span> <span data-ttu-id="6b5c8-105">Diese Implementierung definiert einen `Name` Parameter, der Pipeline Eingaben annimmt, Prozessinformationen vom lokalen Computer auf der Grundlage der angegebenen Namen abruft und dann die Methode " [Write Object" (System. Object, System. Boolean)](/dotnet/api/system.management.automation.cmdlet.writeobject#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_) als Ausgabe Mechanismus zum Senden von Objekten an die Pipeline verwendet.</span><span class="sxs-lookup"><span data-stu-id="6b5c8-105">This implementation defines a `Name` parameter that accepts pipeline input, retrieves process information from the local computer based on the supplied names, and then uses the [WriteObject(System.Object,System.Boolean)](/dotnet/api/system.management.automation.cmdlet.writeobject#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_) method as the output mechanism for sending objects to the pipeline.</span></span>

## <a name="code-sample"></a><span data-ttu-id="6b5c8-106">Codebeispiel</span><span class="sxs-lookup"><span data-stu-id="6b5c8-106">Code Sample</span></span>

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplesgetproc03#getproc03vbAll](Msh_samplesgetproc03#getproc03vbAll)]  -->
