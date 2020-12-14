---
ms.date: 09/13/2016
ms.topic: reference
title: GetProc03-Codebeispiel (C#)
description: GetProc03-Codebeispiel (C#)
ms.openlocfilehash: c81ba04b2b335f4ce992c6b3ed2f019cf6d7d20f
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "93355577"
---
# <a name="getproc03-c-sample-code"></a><span data-ttu-id="116e9-103">GetProc03-Codebeispiel (C#)</span><span class="sxs-lookup"><span data-stu-id="116e9-103">GetProc03 (C#) Sample Code</span></span>

<span data-ttu-id="116e9-104">Der folgende Code zeigt die Implementierung eines `Get-Process` Cmdlets, das Pipeline Eingaben akzeptieren kann.</span><span class="sxs-lookup"><span data-stu-id="116e9-104">The following code shows the implementation of a `Get-Process` cmdlet that can accept pipelined input.</span></span> <span data-ttu-id="116e9-105">Diese Implementierung definiert einen `Name` Parameter, der Pipeline Eingaben annimmt, Prozessinformationen vom lokalen Computer auf der Grundlage der angegebenen Namen abruft und dann die Methode " [Write Object" (System. Object, System. Boolean)](/dotnet/api/system.management.automation.cmdlet.writeobject#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_) als Ausgabe Mechanismus zum Senden von Objekten an die Pipeline verwendet.</span><span class="sxs-lookup"><span data-stu-id="116e9-105">This implementation defines a `Name` parameter that accepts pipeline input, retrieves process information from the local computer based on the supplied names, and then uses the [WriteObject(System.Object,System.Boolean)](/dotnet/api/system.management.automation.cmdlet.writeobject#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_) method as the output mechanism for sending objects to the pipeline.</span></span>

> [!NOTE]
> <span data-ttu-id="116e9-106">Sie können die c#-Quelldatei (getprov03.cs) für dieses Get-Proc-Cmdlet mit dem Microsoft Windows Software Development Kit für Windows Vista und .NET Framework 3,0-Laufzeitkomponenten herunterladen.</span><span class="sxs-lookup"><span data-stu-id="116e9-106">You can download the C# source file (getprov03.cs) for this Get-Proc cmdlet using the Microsoft Windows Software Development Kit for Windows Vista and .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="116e9-107">Anweisungen zum Herunterladen finden Sie unter [Installieren von Windows PowerShell und Herunterladen des Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="116e9-107">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
> <span data-ttu-id="116e9-108">Die heruntergeladenen Quelldateien sind im **\<PowerShell Samples>** Verzeichnis verfügbar.</span><span class="sxs-lookup"><span data-stu-id="116e9-108">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="116e9-109">Codebeispiel</span><span class="sxs-lookup"><span data-stu-id="116e9-109">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/GetProcessSample03/GetProcessSample03.cs" range="11-78":::

## <a name="see-also"></a><span data-ttu-id="116e9-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="116e9-110">See Also</span></span>

[<span data-ttu-id="116e9-111">Windows PowerShell-Programmiererhandbuch</span><span class="sxs-lookup"><span data-stu-id="116e9-111">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="116e9-112">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="116e9-112">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
