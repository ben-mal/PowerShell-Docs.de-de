---
title: RunSpace03 (c#)-Code Beispiel | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: df34652f60ed85b13739a04485cf6622cf924872
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784791"
---
# <a name="runspace03-c-code-sample"></a><span data-ttu-id="a1b18-102">Runspace03-Codebeispiel (C#)</span><span class="sxs-lookup"><span data-stu-id="a1b18-102">RunSpace03 (C#) Code Sample</span></span>

<span data-ttu-id="a1b18-103">Hier ist der c#-Quellcode für die Konsolenanwendung, die unter "Erstellen einer Konsolenanwendung, die ein bestimmtes Skript ausführt" beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="a1b18-103">Here is the C# source code for the console application described in "Creating a Console Application That Runs a Specified Script".</span></span> <span data-ttu-id="a1b18-104">In diesem Beispiel wird die [System. Management. Automation. runspaceinvoke](/dotnet/api/System.Management.Automation.RunspaceInvoke) -Klasse verwendet, um ein Skript auszuführen, das Prozessinformationen mithilfe der Liste der Prozessnamen abruft, die an das Skript übermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="a1b18-104">This sample uses the [System.Management.Automation.Runspaceinvoke](/dotnet/api/System.Management.Automation.RunspaceInvoke) class to execute a script that retrieves process information by using the list of process names passed into the script.</span></span> <span data-ttu-id="a1b18-105">Es zeigt, wie Eingabe Objekte an ein Skript übergeben werden und wie Fehler Objekte sowie die Ausgabe Objekte abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="a1b18-105">It shows how to pass input objects to a script and how to retrieve error objects as well as the output objects.</span></span>

> [!NOTE]
> <span data-ttu-id="a1b18-106">Sie können die c#-Quelldatei (runspace03.cs) für dieses Beispiel mithilfe der Laufzeitkomponenten Microsoft Windows Software Development Kit für Windows Vista und Microsoft .NET Framework 3,0 herunterladen.</span><span class="sxs-lookup"><span data-stu-id="a1b18-106">You can download the C# source file (runspace03.cs) for this sample using the Microsoft Windows Software Development Kit for Windows Vista and Microsoft .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="a1b18-107">Anweisungen zum Herunterladen finden Sie unter [Installieren von Windows PowerShell und Herunterladen des Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="a1b18-107">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
> <span data-ttu-id="a1b18-108">Die heruntergeladenen Quelldateien sind im **\<PowerShell Samples>** Verzeichnis verfügbar.</span><span class="sxs-lookup"><span data-stu-id="a1b18-108">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="a1b18-109">Codebeispiel</span><span class="sxs-lookup"><span data-stu-id="a1b18-109">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/Runspace03/Runspace03.cs" range="11-88":::

## <a name="see-also"></a><span data-ttu-id="a1b18-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a1b18-110">See Also</span></span>

[<span data-ttu-id="a1b18-111">Windows PowerShell-Programmiererhandbuch</span><span class="sxs-lookup"><span data-stu-id="a1b18-111">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="a1b18-112">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="a1b18-112">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
